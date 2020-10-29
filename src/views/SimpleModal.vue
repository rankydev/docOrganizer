<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>{{ title }}</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding ">
      {{ content }}
      <ion-button @click="closeModal">Close modal</ion-button>
    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonContent, IonHeader, IonTitle, IonToolbar, modalController } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Modal',
  props: {
    title: { type: String, default: 'Super Modal' },
  },
  data() {
    return {
      content: 'This is my cool content',
    }
  },
  components: { IonPage, IonContent, IonHeader, IonTitle, IonToolbar },
  setup() {
    const closeModal = () => {
      modalController.dismiss();
    };
    return {
      closeModal
    }
  }
});
</script>