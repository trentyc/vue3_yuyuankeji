<script setup lang="ts">
import { reactive, computed } from "vue";
import { RouterView } from "vue-router";
import { ElConfigProvider } from "element-plus";
import { useGlobalStore } from "@/stores/modules/global";

const globalStore = useGlobalStore();

// element assemblySize
const assemblySize = computed(() => globalStore.assemblySize);

// element button config
const buttonConfig = reactive({ autoInsertSpace: false });
</script>

<template>
  <el-config-provider :size="assemblySize" :button="buttonConfig">
    <RouterView />
  </el-config-provider>
</template>

<style scoped lang="scss"></style>
