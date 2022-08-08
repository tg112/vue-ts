<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('zelda')">change name</button>
    <button @click="changeAge(30)">change name</button>
  </div>
</template>

<script lang="ts">
type Age = string | number;

import { defineComponent, reactive, ref, toRefs } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    const state = reactive({
      name: "Link",
      age: 25 as Age,
    });
    return { ...toRefs(state) };
    // const name = ref("Link");
    // const age = ref<Age>(25);
    // return {
    //   name,
    //   age,
    // };
  },
  methods: {
    changeName(name: string) {
      this.name = name;
      return name;
    },
    changeAge(age: Age) {
      this.age = age;
      return age;
    },
  },
});
</script>

<style></style>
