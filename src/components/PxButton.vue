<template>
  <button
    @click="buttonClick"
    class="bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white py-2 px-2 border border-green-500 hover:border-transparent rounded"
  >
  <!--El slot es para que cuando se use este componente en la tabla de assets,
  dentro del componente se pueda agregar mas html -->
    <beat-loader :loading="isLoading" :color="'#68d391'" :size="8" />
    <div v-show="!isLoading">
      <slot></slot>
    </div>
  </button>
</template>

<script>
export default {
  name: 'PxButton',

  props: {
    isLoading: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    buttonClick() {
      this.$emit('custom-click')
    }
  }
}
</script>
