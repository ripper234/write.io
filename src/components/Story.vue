<template>
  <div id='story'>
    <h1 v-if="sharedState.story.title.text" id="story-title">{{sharedState.story.title.text}}</h1>
    <div v-for="contribution in sharedState.story.contributions" v-bind:style="{ color: contribution.color }" v-bind:class="{mine: contribution.playerId === sharedState.playerId, theend: contribution.text === 'The End'}">
      {{contribution.text}}
    </div>
    <h2 class='theend'>{{sharedState.story.theend}}</h2>
  </div>
</template>

<script>
  import store from './store'

  export default {
    name: 'Game',
    components: {},
    data() {
      return {
        sharedState: store.state
      }
    },
    methods: {

    }
  }

</script>

<style lang='less'>
  #story {
    border: 3px black double;
    padding: 5px;
    border-radius: 15px;
    min-width: 320px;
    h1 {
      margin-bottom: 20px;
    }
    .theend {
      margin-top: 20px;
      font-size: 24px;
      text-align: center;
    }
  }
  
  #story-html {
    text-align: left;
    font-family: Georgia, Cambria, "Times New Roman", Times, serif;
    .mine {
      font-weight: bold;
    }
  }
</style>