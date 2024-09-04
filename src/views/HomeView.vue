<script setup lang="ts">
import { ref } from 'vue'

const step = ref({
  min: 10,
  max: 20
})

const model = ref({ from: '2020/07/08', to: '2020/07/17' })

const alert = ref(false)
const value = ref(false)
const first = ref(false)
const third = ref(false)
const text = ref('')
const knobValue = ref(80)

const onItemClick = () => {
  console.log('ok')
}
</script>

<template>
  <q-toolbar class="bg-red-10 text-white">
    <q-btn flat round dense icon="assignment_ind" />
    <q-toolbar-title>Quasar Demo</q-toolbar-title>
    <q-btn flat round dense icon="apps" class="q-mr-xs" />
    <q-btn flat round dense icon="more_vert" />
  </q-toolbar>

  <q-toggle v-model="value" color="red" label="On Right" keep-color /><br />
  <q-toggle v-model="first" icon="mail" color="green" /><br />
  <q-toggle v-model="third" checked-icon="check" color="green" unchecked-icon="clear" /><br />

  <q-knob show-value class="text-red q-ma-md" v-model="knobValue" size="50px" color="red" />

  <div class="q-pa-md q-gutter-sm">
    <br />

    <div style="display: flex; flex-direction: column; margin-bottom: 6px; width: 26rem">
      <q-range v-model="step" :min="0" :max="45" :step="5" label color="deep-orange" />
      <q-date v-model="model" range color="blue" />
      <q-input v-model="text" label="Standard" />
      <q-input v-model="text" label="Autogrow" autogrow />
      <q-input v-model="text" label="Autogrow" filled />
      <q-input v-model="text" label="Autogrow" outlined />
    </div>

    <q-btn color="primary" label="Primary" :flat="false" :ripple="true" />
    <q-btn color="secondary" label="Secondary" :flat="false" :ripple="true" />
    <q-btn outline label="Goldenrod" color="primary" :ripple="true" />
    <q-btn round color="primary" icon="shopping_cart" />

    <br />
    <q-btn round color="deep-orange" icon="edit_location" />
    <q-btn round color="deep-orange" icon="edit_location" size="xs" />
    <q-btn round color="deep-orange" icon="edit_location" size="sm" />
    <q-btn round color="deep-orange" icon="edit_location" size="md" />
    <q-btn round color="deep-orange" icon="edit_location" size="lg" />
    <q-btn round color="deep-orange" icon="edit_location" size="xl" />
    <q-btn round color="deep-orange" icon="edit_location" size="30px" />

    <br />

    <q-btn round>
      <q-avatar size="42px">
        <img src="https://cdn.quasar.dev/img/avatar2.jpg" />
      </q-avatar>
    </q-btn>

    <q-btn class="glossy" rounded color="green" label="Glossy Rounded" />
    <q-btn rounded color="green" label="Glossy Rounded" />

    <br />

    <q-btn-dropdown color="primary" label="Settings" dropdown-icon="*">
      <q-list>
        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Photos</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Videos</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Articles</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-btn-dropdown>

    <br />

    <q-card
      class="my-card"
      :flat="true"
      :bordered="true"
      :square="false"
      :style="{ width: '30%', color: '#666' }"
    >
      <q-card-section>
        Join the global community of developers Hosted by Vercel and leaders at Next.js Conf for a
        day of education, innovation, and fun as we build a better web With next.js together.
      </q-card-section>
    </q-card>

    <q-card
      class="my-card"
      :flat="true"
      :bordered="true"
      :dark="true"
      :square="false"
      :style="{
        width: '30%',
        color: '#fff',
        background: '#0f172a',
        borderRadius: '6px'
      }"
    >
      <q-card-section>
        Join the global community of developers Hosted by Vercel and leaders at Next.js Conf for a
        day of education, innovation, and fun as we build a better web With next.js together.
      </q-card-section>
    </q-card>

    <q-card class="my-card" :style="{ width: '20%' }">
      <img src="https://cdn.quasar.dev/img/mountains.jpg" />

      <q-card-section>
        <div class="text-h6">Our Changing Planet</div>
        <div class="text-subtitle2">
          Join the global community of developers Hosted by Vercel and leaders at Next.js Conf for a
          day of education, innovation, and fun as we build a better web With next.js together.
        </div>
      </q-card-section>
    </q-card>

    <q-chip color="deep-orange" text-color="white" icon="directions"> Get directions </q-chip>
    <q-chip color="deep-orange" text-color="white" icon="directions" size="xs">
      Get directions
    </q-chip>
    <q-chip color="deep-orange" text-color="white" icon="directions" size="sm">
      Get directions
    </q-chip>

    <br />

    <q-btn label="Alert" color="primary" @click="alert = true" />

    <q-dialog v-model="alert" :transition-duration="0">
      <q-card>
        <q-card-section>
          <div class="text-h6">Alert</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate
          voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam
          exercitationem aut, natus minima, porro labore.
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>
