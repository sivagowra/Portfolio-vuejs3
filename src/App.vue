<template>
  <div class="bg-[#111827] min-h-screen">
    <!-- Wrap components in Suspense to handle loading -->
    <Suspense>
      <template #default>
        <!-- Wrap all Components inside a single root element -->
        <div>
          <!-- Sticky NavBar at the top -->
          <div class="sticky top-0 left-0 right-0 z-10 bg-[#111827]">
            <NavBar />
          </div>
          <div class="pt-[80px]">
            <!-- Other sections will follow after the Navbar -->
            <HeroSection />
            <ServicesSection />
            <AboutSection />
            <ExperienceAndSkills />
            <LatestProjSection />
            <ContactSection />
            <Footer />
            <BackToTop />
          </div>
        </div>
      </template>
      <template #fallback>
        <div class="flex justify-center items-center min-h-screen">
          <loadingSpinner />
        </div>
      </template>
    </Suspense>
  </div>
</template>

<script setup>
  import { defineAsyncComponent } from 'vue';
  // Import Components Asynchronously
  const NavBar = defineAsyncComponent(() => import('@/components/NavBar.vue'));
  const HeroSection = defineAsyncComponent(() => import('@/components/HeroSection.vue'));
  const ServicesSection = defineAsyncComponent(() => import('@/components/ServicesSection.vue'));
  const AboutSection = defineAsyncComponent(() => import('@/components/AboutSection.vue'));
  const TestimonialsSection = defineAsyncComponent(() => import('@/components/TestimonialsSection.vue'));
  const LatestProjSection = defineAsyncComponent(() => import('@/components/LatestProjSection.vue'));
  const ExperienceAndSkills = defineAsyncComponent(() => import('@/components/ExperienceAndSkills.vue'));
  const ContactSection = defineAsyncComponent(() => import('@/components/ContactSection.vue'));
  const Footer = defineAsyncComponent(() => import('@/components/Footer.vue'));
  const BackToTop = defineAsyncComponent(() => import('@/components/BackToTop.vue'));
  import loadingSpinner from './components/loadingSpinner.vue';
</script>

<style>
  * {
    scrollbar-width: thin;
    scrollbar-color: #111827 #f1f1f1;
  }

  /* Sticky NavBar */
  .sticky {
    position: sticky;
    top: 0;
    left: 0;
    right: 0;
    z-index: 20;
    background-color: #ed7409;
    box-shadow: 0 2px 4px rgba(234, 228, 228, 0.1);
  
    
  }

  /* Add padding to the body content below the navbar */

</style>
