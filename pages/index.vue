<script setup lang="ts">
useHead({
  title: 'ToApps — Download Our Apps',
  meta: [
    {
      name: 'description',
      content: 'Download Water Sort: Magic Puzzle and 2048.',
    },
  ],
})

const games = [
  {
    name: 'Water Sort: Magic Puzzle',
    iconPng: '/water-sort-magic-puzzle.png',
    iconWebpSrcset: '/icons/water-sort-magic-puzzle-88.webp 88w, /icons/water-sort-magic-puzzle-176.webp 176w, /icons/water-sort-magic-puzzle-264.webp 264w',
  },
  {
    name: '2048',
    iconPng: '/2048.png',
    iconWebpSrcset: '/icons/2048-88.webp 88w, /icons/2048-176.webp 176w, /icons/2048-264.webp 264w',
  },
]
</script>

<template>
  <main class="relative flex min-h-dvh items-center overflow-hidden bg-[#f7f7f8] px-5 py-16 sm:px-8">
    <div
      aria-hidden="true"
      class="pointer-events-none absolute left-1/2 top-0 h-80 w-[36rem] -translate-x-1/2 rounded-full bg-[radial-gradient(ellipse_at_center,_rgba(255,255,255,0.96)_0%,_rgba(255,255,255,0)_70%)]"
    />

    <section class="relative mx-auto w-full max-w-[620px]">
      <div class="mb-11 text-center sm:mb-14">
        <p class="mb-5 text-sm font-semibold tracking-[0.18em] text-violet-600 uppercase">
          ToApps
        </p>
        <h1 class="text-balance text-[clamp(2.65rem,9vw,4.65rem)] font-bold leading-[0.98] tracking-[-0.065em] text-[#1c1c20]">
          Download Our Apps
        </h1>
        <p class="mx-auto mt-6 max-w-md text-pretty text-lg leading-relaxed text-[#76767d] sm:text-xl">
          Pick a game — we'll send you to the right store.
        </p>
      </div>

      <!-- Replace the #app-store links with the corresponding App Store URLs when they are ready. -->
      <div class="space-y-5 sm:space-y-6">
        <a
          v-for="(game, index) in games"
          :key="game.name"
          href="#app-store"
          class="group flex min-h-32 items-center gap-5 rounded-[28px] border border-white/80 bg-white px-6 py-5 shadow-[0_3px_4px_rgba(18,18,23,0.02),0_12px_28px_rgba(18,18,23,0.07)] transition duration-300 ease-out hover:-translate-y-1 hover:shadow-[0_5px_8px_rgba(18,18,23,0.04),0_18px_34px_rgba(18,18,23,0.1)] focus-visible:outline-3 focus-visible:outline-offset-4 focus-visible:outline-violet-500 sm:min-h-36 sm:gap-6 sm:px-8"
        >
          <picture class="block size-[76px] shrink-0 sm:size-[88px]">
            <source
              :srcset="game.iconWebpSrcset"
              sizes="(min-width: 640px) 88px, 76px"
              type="image/webp"
            >
            <img
              :src="game.iconPng"
              :alt="`${game.name} icon`"
              width="88"
              height="88"
              :loading="index === 0 ? 'eager' : 'lazy'"
              :fetchpriority="index === 0 ? 'high' : 'low'"
              decoding="async"
              class="size-full rounded-[20px] object-cover shadow-[0_8px_18px_rgba(24,24,27,0.16)] sm:rounded-[23px]"
            >
          </picture>
          <span class="min-w-0 flex-1">
            <span class="block text-pretty text-[1.4rem] font-semibold leading-tight tracking-[-0.035em] text-[#202025] sm:text-[1.75rem]">
              {{ game.name }}
            </span>
            <span class="mt-2 block text-sm font-medium text-[#898990] sm:text-base">
              Tap to open in the App Store
            </span>
          </span>
          <svg
            aria-hidden="true"
            class="size-6 shrink-0 text-[#8a8a91] transition duration-300 group-hover:translate-x-1 group-hover:text-violet-600 sm:size-7"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
          >
            <path d="m9 18 6-6-6-6" />
          </svg>
        </a>
      </div>

      <p
        id="app-store"
        class="mx-auto mt-6 max-w-sm text-center text-sm leading-relaxed text-[#96969d]"
      >
        Available soon on the App Store.
      </p>
    </section>
  </main>
</template>
