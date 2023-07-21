<template>
  <div class="home">
    <asciinema-player
      theme="tango"
      startAt="0:00"
      poster="0:00"
      :speed="1"
      :fontSize="12"
      autoplay
      :src="data"
    ></asciinema-player>
    <button @click="setSrc">setSrc</button>
    <button @click="setSrc1">setSrc1</button>
  </div>
</template>
<script>
import AsciinemaPlayer from "@/components/asciinema-player.vue";
import cast from "./record.cast"; // 本地加载 loading local file
export default {
  data() {
    return {
      data: cast
    };
  },
  components: {
    AsciinemaPlayer
  },
  methods: {
    setSrc() {
      // load from third service
      // this.data = "/cast/just-demo-record.cast";
      // 设置静态文件代理地址
      this.data = "https://e61id1-bucket-demo.oss.laf.run/demo.cast";

    },
    setSrc1() {
      this.data = "https://e61id1-bucket-demo.oss.laf.run/record.cast";
    }
  },
  mounted() {
    // console.log(process.env);
  }
};
</script>
<style scoped>
/* @import url("./css/asciinema-player.css"); */
</style>
