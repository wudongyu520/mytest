<script setup>
import { ref } from 'vue'
const dark = ref(false)
const projects = [
  { tag: 'VUE 3', title: 'Dashboard Lab', text: '一个用于探索组件、数据可视化与交互体验的小型实验室。' },
  { tag: 'AI', title: 'Agent Playground', text: '把 AI 能力接入日常开发流程，尝试更自然的人机协作。' },
  { tag: 'WEB', title: 'Personal Notes', text: '记录前端、JavaScript 与各种奇奇怪怪的技术想法。' }
]
</script>

<template>
  <div class="site" :class="{ dark }">
    <nav class="nav shell">
      <a class="logo" href="#">DY<span>.</span></a>
      <div class="links"><a href="#about">关于</a><a href="#projects">项目</a><a href="#contact">联系</a></div>
      <button class="theme" @click="dark = !dark" :aria-label="dark ? '切换亮色' : '切换暗色'">{{ dark ? '☀' : '☾' }}</button>
    </nav>

    <main>
      <section class="hero shell">
        <div class="eyebrow"><i></i> AVAILABLE FOR NEW IDEAS</div>
        <h1>你好，我是<span>东宇</span>。<br />一个喜欢把想法做出来的人。</h1>
        <p class="lead">前端开发者 · Vue 3 · JavaScript · AI 探索者<br />这是一个纯 Vue 3 的测试门户，简单、漂亮，顺便证明一下代码能跑。</p>
        <div class="actions"><a class="primary" href="#projects">看看作品 ↓</a><a class="secondary" href="#about">了解更多</a></div>
        <div class="orb orb-a"></div><div class="orb orb-b"></div>
      </section>

      <section id="about" class="about shell">
        <div><p class="label">01 / ABOUT</p><h2>保持好奇，<br /><em>持续构建。</em></h2></div>
        <p class="about-copy">我喜欢研究 Web 技术，也喜欢折腾新工具。相比把技术当成终点，我更在意它能不能真正解决问题。这个页面没有后端、没有 UI 库，只有 Vue 3 + CSS + 一点点想象力。</p>
      </section>

      <section id="projects" class="projects shell">
        <div class="section-head"><div><p class="label">02 / PROJECTS</p><h2>一些小东西</h2></div><span>03 ITEMS</span></div>
        <div class="cards"><article v-for="(p, i) in projects" :key="p.title" class="card"><div class="card-top"><span>{{ p.tag }}</span><b>0{{ i + 1 }}</b></div><h3>{{ p.title }}</h3><p>{{ p.text }}</p><a href="#">Explore ↗</a></article></div>
      </section>

      <section id="contact" class="contact shell">
        <p class="label">03 / CONTACT</p><h2>有趣的想法，<br /><span>可以聊聊。</span></h2><a class="mail" href="mailto:hello@example.com">hello@example.com ↗</a>
      </section>
    </main>
    <footer class="shell"><span>© 2026 Dongyu</span><span>Built with Vue 3</span></footer>
  </div>
</template>
