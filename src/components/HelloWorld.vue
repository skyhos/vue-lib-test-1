<template>
  <div class="main-container">
    <custom-title :msg="random" />
    <button @click="changeMsg">Say!</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import CustomTitle from './CustomTitle.vue';

export default defineComponent({
  name: 'HelloWorld',
  components: {
    CustomTitle,
  },
  setup() {
    const randomWords: string[] = ['You', 'are', 'my', 'sunshine'];
    const random = ref<string>('Welcome!');
    const changeMsg = () => {
      const idx = Math.floor(Math.random() * 4);
      random.value = randomWords[idx];
    };
    return {
      random,
      changeMsg,
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
