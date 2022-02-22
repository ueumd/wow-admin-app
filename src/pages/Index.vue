<script setup lang="ts">
import { log } from 'console';
import { getCurrentInstance } from 'vue';
const {proxy} = getCurrentInstance()
const { t, locale } = useI18n();
const { isDark, toggleDark } = useDarks();

onMounted(() => {
    console.log(proxy.$api())
}) 

const toggleLocale = () => {
  locale.value = locale.value === "zh-CN" ? "en" : "zh-CN";
};


</script>

<template>
  <div class="box">
    <div>You can you up，no can no BB</div>
    <div class="cursor-pointer m-6" @click="toggleDark()">
      light: {{ isDark }} click me!!
    </div>

    <div class="cursor-pointer m-6" @click="toggleLocale()">
      language: {{ t("index") }} click me!!
    </div>
  </div>
</template>