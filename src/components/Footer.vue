<template lang="pug">
  v-card.elevation-24
    v-footer(color="basic" padless)
      v-row(justify="center" no-gutters)
        v-btn(v-for="link in links" :key="link" :href="link.href" color="white" icon)
          v-icon {{link.icon}}
      v-col.my-n5.text-center.font-weight-bold(color="secondary" cols="12") 
        v-btn.text-center.white--text.font-weight-bold(text='Primary' 
                                                       to='./about' color='white' large
                                                       @click="viewForm"
                                                       ) Contact Us
      v-col.pt-0.pb-1.text-center.white--text.font-weight-bold(color="secondary" cols="12") {{ new Date().getFullYear() }} — Devlup Labs
</template>
<script>
export default {
  data() {
    return {
      links: [
        { icon: "mdi-gmail", href: "mailto:opensourceiitj@gmail.com" },
        { icon: "mdi-facebook", href: "https://www.facebook.com/devluplabs/" },
        {
          icon: "mdi-instagram",
          href: "https://www.instagram.com/devluplabs/"
        },
        { icon: "mdi-github", href: "https://github.com/devlup-labs" },
        {
          icon: "mdi-linkedin",
          href: "https://www.linkedin.com/company/devlup-labs/"
        }
      ],
      clicked: false
    };
  },
  methods: {
    scrollForm: function() {
      if (this.clicked) {
        window.scrollTo(0, document.body.scrollHeight);
        setInterval(() => {
          this.clicked = false;
        }, 200);
      }
    },
    viewForm: function() {
      this.clicked = true;
      setInterval(() => {
        this.scrollForm();
      }, 200);
    }
  }
};
</script>
