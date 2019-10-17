<template>
    <div style="width: 100%; display: flex; justify-content: center; height: 100vh; align-items: center"
         v-on:keyup.enter="al">
        <img alt="" src="/static/images/red.svg" style="height: 100%" v-if="state === 0">
        <img alt="" src="/static/images/yellow.svg" style="height: 100%" v-if="state === 1">
        <img alt="" src="/static/images/green.svg" style="height: 100%" v-if="state === 2">
    </div>
</template>

<script>
    export default {
      name: 'TrafficLight',
      data: function () {
        return {
          state: 0
        }
      },
      methods: {
        al: function () {
          alert()
          console.log()
        }
      },
      mounted () {
        console.log(window)

        window.addEventListener('keyup', (e) => {
          if (this.state === 2) {
            this.state = 0
            return 1
          } else {
            setTimeout(() => {
              this.state = 1
              setTimeout(() => {
                this.state = 2
              }, 1000)
            }, 1000)
          }
        }, true)
  }
    }
</script>

<style scoped>

</style>