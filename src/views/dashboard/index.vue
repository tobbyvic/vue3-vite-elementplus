<script lang="ts" setup>
import { ref } from "vue"
import { useUserStore } from "@/store/modules/user"

type CurrentRoleType = "admin" | "editor"

const userStore = useUserStore()
const currentRole = ref<CurrentRoleType>("admin")
if (!userStore.roles.includes("admin")) {
  currentRole.value = "editor"
}
</script>

<template>
  <div>
    <el-empty description="空空如也" />
  </div>
</template>
