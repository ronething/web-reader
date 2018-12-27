<template>
  <div class="ebook">
    <div class="read-wrapper">
      <div id="read"></div>
    </div>
  </div>
</template>

<script>
import Epub from "epubjs";
const DOWNLOAD_URL = "/static/docker_practice.epub";
export default {
  props: [],
  data() {
    return {};
  },
  computed: {},
  created() {},
  mounted() {
    this.showEpub();
  },
  watch: {},
  methods: {
    showEpub() {
      this.book = new Epub(DOWNLOAD_URL);
      this.rendition = this.book.renderTo("read", {
        width: window.innerWidth,
        height: window.innerHeight
      });
      this.rendition.display();
    }
  },
  components: {}
};
</script>

<style lang='scss' scoped>
@import "assets/styles/global";
</style>
