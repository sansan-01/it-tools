<script setup lang="ts">
import { NIcon } from 'naive-ui';
import { ActivityHeartbeat, BrandGithub, Compass, Moon, Sun } from '@vicons/tabler';
import { useStyleStore } from '@/stores/style.store';

const styleStore = useStyleStore();
const { t } = useI18n();
</script>

<template>
  <div flex items-center justify-center gap-2>
    <c-tooltip :tooltip="t('navbar.status_page')" position="bottom">
      <c-button
        circle
        variant="text"
        tag="a"
        href="https://status.zhou.su"
        target="_blank"
        rel="noopener noreferrer"
        :aria-label="t('navbar.status_page')"
      >
        <NIcon size="25" :component="ActivityHeartbeat" />
      </c-button>
    </c-tooltip>

    <c-tooltip :tooltip="t('navbar.navigation_home')" position="bottom">
      <c-button
        circle
        variant="text"
        tag="a"
        href="https://zhou.su"
        target="_blank"
        rel="noopener noreferrer"
        :aria-label="t('navbar.navigation_home')"
      >
        <NIcon size="25" :component="Compass" />
      </c-button>
    </c-tooltip>

    <c-tooltip :tooltip="t('home.toggleTheme')" position="bottom">
      <c-button
        circle
        variant="text"
        :aria-label="t('home.toggleTheme')"
        @click="styleStore.toggleDark()"
      >
        <NIcon size="25" :component="styleStore.isDarkTheme ? Sun : Moon" />
      </c-button>
    </c-tooltip>

    <c-tooltip :tooltip="t('home.github')" position="bottom">
      <c-button
        circle
        variant="text"
        tag="a"
        href="https://github.com/CorentinTh/it-tools"
        target="_blank"
        rel="noopener noreferrer"
        :aria-label="t('home.github')"
      >
        <NIcon size="25" :component="BrandGithub" />
      </c-button>
    </c-tooltip>
  </div>
</template>
