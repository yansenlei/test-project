<template>
  <div id="app">
    <mavon-editor v-model="value" ref="md"/>
    <router-view/>
  </div>
</template>

<script>
import { mavonEditor } from 'mavon-editor'
require('mavon-editor/dist/css/index.css')
import markdownItChart from 'markdown-it-chart'
export default {
  name: 'App',
  data () {
    return {}
  },
  components: {
    'mavon-editor': mavonEditor
  },
  mounted () {
    this.$refs.md.s_markdown.use(markdownItChart)
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
