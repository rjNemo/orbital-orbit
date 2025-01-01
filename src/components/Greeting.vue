<script setup lang="ts">
import { computed, ref } from "vue";

const props = defineProps<{ messages: string[] }>();
const greeting = ref(props.messages[0]);
const randomMessage = () => {
  greeting.value =
    props.messages[Math.floor(Math.random() * props.messages.length)];
};
</script>

<template>
  <div>
    <h3>{{ greeting }}! Thanks for stopping by!</h3>
    <button @click="randomMessage">New greeting</button>
  </div>
</template>
