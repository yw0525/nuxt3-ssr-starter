<template>
  <h3>Hi,</h3>
  <div>{{ name }}!</div>
</template>

<script setup lang="ts">
import { useUserStore } from '~/stores/user';

const route = useRoute();
const user = useUserStore();
const name = route.params.id;

watchEffect(() => {
  user.setNewName(route.params.id as string);
});
</script>
