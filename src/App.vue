<template>
    <div style="padding-top: 50px; text-align: center">
        <img src="./assets/pien.png?{{ new Date()}}" @load="loaded" style="height: 0; opacity: 0; width: 0" alt="測定用ぴえん"/>
        <img src="./assets/pien-icon.png" style="margin: auto; min-width: 200px; width: 10%" alt="ぴえん"/>
        <h1>あなたのちえんは{{ score }}です</h1>
        <p>少ない方がいいスコアです</p>
    </div>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            onCreated: '',
            onLoaded: '',
            score: 0
        }
    },
    created() {
        this.onCreated = new Date().getTime()
    },
    methods: {
        loaded() {
            this.onLoaded = new Date().getTime()
            this.score = this.onLoaded - this.onCreated
        }
    }
}
</script>
