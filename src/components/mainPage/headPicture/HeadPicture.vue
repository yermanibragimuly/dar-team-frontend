<script setup lang="ts">
import heroVideo from '@/assets/video/hero-video.webm'
</script>

<template>
  <div class="relative w-full overflow-hidden bg-black" style="height: 80vh; min-height: 720px;">
    <!-- Фоновое зацикленное видео -->
    <video
      autoplay
      loop
      muted
      playsinline
      poster="/src/assets/img/dar_team_10_years.webp"
      class="absolute inset-0 w-full h-full object-cover pointer-events-none"
    >
      <source :src="heroVideo" type="video/webm" />
    </video>

    <!-- Общий слой затемнения видео -->
    <div class="absolute inset-0 bg-black/40 pointer-events-none"></div>

    <!-- Мягкая виньетка -->
    <div class="absolute inset-0 pointer-events-none radial-vignette"></div>

    <!-- Мягкий градиент снизу для плавного стыка со следующим блоком -->
    <div class="absolute inset-x-0 bottom-0 h-32 bg-gradient-to-t from-black via-black/60 to-transparent pointer-events-none"></div>

    <!-- Градиент сверху под хедер -->
    <div class="absolute inset-x-0 top-0 h-24 bg-gradient-to-b from-black/70 to-transparent pointer-events-none"></div>

    <!-- Фирменный логотип DAR TEAM по центру -->
    <img 
      src="/src/assets/img/Main_img8.svg" 
      alt="Logo main" 
      class="absolute inset-0 mx-auto my-auto max-w-full h-auto z-10 pointer-events-none px-4 select-none drop-shadow-[0_8px_24px_rgba(0,0,0,0.85)]"
    />
  </div>
</template>

<style scoped>
.radial-vignette {
  background: radial-gradient(
    circle at center,
    rgba(0, 0, 0, 0.2) 0%,
    rgba(0, 0, 0, 0.55) 55%,
    rgba(0, 0, 0, 0.8) 100%
  );
}

video {
  animation: fadeIn 0.8s ease-in-out forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>