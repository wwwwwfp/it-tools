<script setup lang="ts">
import { BrandGithub, BrandTwitter, InfoCircle, Moon, Sun } from '@vicons/tabler';
import { useStyleStore } from '@/stores/style.store';

const styleStore = useStyleStore();
const { isDarkTheme } = toRefs(styleStore);
</script>

<template>
  <c-tooltip :tooltip="$t('home.nav.blog')" position="bottom">
    <c-button
      circle
      variant="text"
      href="https://blog.5iwork.com"
      target="_blank"
      rel="noopener noreferrer"
      :aria-label="$t('home.nav.blog')"
    >
      <div>Blog</div>
    </c-button>
  </c-tooltip>

  <c-tooltip :tooltip="$t('home.nav.running')" position="bottom">
    <c-button
      circle
      variant="text"
      href="https://run.5iwork.com"
      rel="noopener"
      target="_blank"
      :aria-label="$t('home.nav.running')"
    >
    <div>Run</div>
    </c-button>
  </c-tooltip>


  <c-tooltip :tooltip="isDarkTheme ? $t('home.nav.lightMode') : $t('home.nav.darkMode')" position="bottom">
    <c-button circle variant="text" :aria-label="$t('home.nav.mode')" @click="() => styleStore.toggleDark()">
      <n-icon v-if="isDarkTheme" size="25" :component="Sun" />
      <n-icon v-else size="25" :component="Moon" />
    </c-button>
  </c-tooltip>
</template>

<style lang="less" scoped>
.n-button {
  &:not(:last-child) {
    margin-right: 5px;
  }
}
</style>
