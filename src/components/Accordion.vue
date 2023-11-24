<template>
  <div id="faq" class="bg-[#134241]">
    <div class="mx-auto px-6 py-24 sm:py-10 lg:px-8 lg:pt-20 lg:pb-20">
      <div class="mx-auto max-w-4xl divide-y divide-white/10">
        <h1 class="text-4xl font-bold leading-10 tracking-tight text-white">Questions Fréquemment Posées</h1>
        <dl class="mt-10 space-y-6 divide-y divide-white/10">
          <Disclosure as="div" v-for="faq in faqs" :key="faq.question" class="pt-6" v-slot="{ open }">
            <dt>
              <DisclosureButton class="flex w-full items-start justify-between text-left text-white">
                <span class="text-base font-semibold leading-7">{{ faq.question }}</span>
                <span class="ml-6 flex h-7 items-center">
                  <PlusSmallIcon v-if="!open" class="h-6 w-6" aria-hidden="true" />
                  <MinusSmallIcon v-else class="h-6 w-6" aria-hidden="true" />
                </span>
              </DisclosureButton>
            </dt>
            <DisclosurePanel as="dd" class="mt-2 pr-12">
              <p class="text-base leading-7 text-gray-300">{{ faq.answer }}</p>
            </DisclosurePanel>
          </Disclosure>
        </dl>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { MinusSmallIcon, PlusSmallIcon } from '@heroicons/vue/24/outline'
const faqs = [
  {
    question: "Quand allez-vous lancer votre startup?",
    answer: "Samanhla Garden prévoit de lancer ses activités au Maroc en janvier 2024.",
  },
  {
    question: "Qu'est-ce qui vous différencie des autres?",
    answer: "Samanhla Garden se distingue en créant et installant des murs végétaux naturels au Maroc, contrairement à la plupart de nos concurrents qui utilisent des murs artificiels.",
  },
  {
    question: "Qu'offrons-nous?",
    answer: "Chez Samanhla Garden, nous transformons chaque espace en une oasis agréable pour nos clients. En créant des murs végétaux naturels, nous transformons chaque espace en une œuvre d'art unique. Au-delà de l'attrait esthétique, nos installations offrent une gamme de bénéfices, notamment l'isolation thermique et sonore, la purification de l'air, des économies d'eau et d'espace. Notre objectif est de fournir non seulement un service, mais une expérience qui améliore l'environnement et le bien-être de nos clients.",
  },
  {
    question: "Quelles sont les options de personnalisation?",
    answer: "Notre approche personnalisée chez Samanhla Garden prend en compte l'environnement unique de chaque client, assurant que les plantes sélectionnées prospèrent dans chaque espace. Nous offrons une solution présentée dans un cadre similaire à une œuvre d'art, offrant aux clients la possibilité de personnaliser le cadre pour correspondre à leur style et à leur décor. De plus, nous élaborons une conception et un système sur mesure pour chaque projet, mettant l'accent sur la personnalisation. Cela inclut le choix de l'emplacement idéal, la sélection des plantes appropriées, et le type d'éclairage adapté, garantissant ainsi une solution unique qui répond pleinement aux besoins individuels de nos clients.",
  },
];
</script>