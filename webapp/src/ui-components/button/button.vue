<template>
  <button
    :type="type"
    class="rounded-md inline-flex justify-center bg-indigo-500 text-white px-3 py-2 hover:bg-indigo-700 disabled:opacity-50"
    :class="classes"
  >
    <slot></slot>
  </button>
</template>
<script lang="ts">
import { defineComponent, computed } from "vue";

export default defineComponent({
  props: {
    full: Boolean,
    submit: Boolean,
  },
  setup(props) {
    const classes = computed(() => {
      return {
        "w-full": props.full
      }
    });

    const type = computed(() => {
      return props.submit ? "submit" : "button";
    })

    return {
      classes,
      type,
    };
  }
});
</script>