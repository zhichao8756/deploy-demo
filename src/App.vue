<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
// import HelloWorld from './components/HelloWorld.vue'
import { BubbleMessage, FoldMessage, MessageBox, ProgressBox, Rate, Spinner } from 'js-dynamic-island'
function sleep(time) {
  return new Promise((resolve, reject) =>
      setTimeout(resolve, time))
}
function testBubble() {
  BubbleMessage({
    user: 'zack',
    message: 'ot take to heart every thing you hear. do not take to heart every thing you hear. do not spend all; Whenever you find your wrongdoing',
    avatar: 'https://joeschmoe.io/api/v1/random',
    type: 'success'
  })
}
function testFold() {
  FoldMessage({
    message: 'ot take to heart every thing you hear. do not take to heart every thing you hear. do not spend all; Whenever you find your wrongdoing',
    type: 'success'
  })
}
function testMessage() {
  MessageBox({
    title: 'This is a title',
    content: 'ot take to heart every thing you hear. do not take to heart every thing you hear. do not spend all; Whenever you find your wrongdoing'
  }).then(() => {
    console.log('confirm')
  }).catch(() => {
    console.log('cancel')
  })
}
function progress() {
  ProgressBox({
    loadingTime: 3000
  }).then(() => {
    console.log('done')
  })
}
function like() {
  Rate({
    title: '点个赞吧~'
  })
}
async function loading() {
  Spinner.show('加载中')
  await sleep(3000)
  Spinner.done()
}
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <div class="container">
    <div @click="testBubble">
      <div class="icon-container" style="background: #7FE271"></div>
      <span class="text-container">气泡信息</span>
    </div>
    <div @click="testFold">
      <div class="icon-container" ></div>
      <span class="text-container">折叠信息</span>
    </div>
    <div @click="testMessage">
      <div class="icon-container" style="background: #ABAAB1">
      </div>
      <span class="text-container">弹框信息</span>
    </div>

    <div @click="progress">
      <div class="icon-container" style="background: #7D4891">

      </div>
      <span class="text-container">进度提示</span>
    </div>

    <div @click="like">
      <div class="icon-container" style="background: #FB8B0F">
      </div>
      <span class="text-container">点个赞吧</span>

    </div>

    <div @click="loading">
      <div class="icon-container" >
      </div>
      <span class="text-container">加载组件</span>

    </div>


<!--    <button >气泡信息</button>
    <button >折叠信息</button>
    <button @click="testMessage">弹框信息</button>
    <button @click="progress">进度提示</button>
    <button @click="like">点个赞吧~</button>
    <button @click="loading">加载组件~</button>-->
  </div>

</template>
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.container {
  display: flex;
  width: 300px;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.icon-container {
  margin: 20px 12px;
  width: 60px;
  height: 60px;
  border-radius: 20%;
  background-color: #ececec;
  position: relative;
}
.text-container {
  color: white;
  text-align: center;
  margin: 0;
  padding: 0;
  font-weight: 300;
}
</style>
