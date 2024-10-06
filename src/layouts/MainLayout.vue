<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item to="/" exact>
          <q-item-section avatar>
            <q-icon name="home"/>
          </q-item-section>

          <q-item-section>
            Inicio
          </q-item-section>
        </q-item>

        <q-expansion-item
          expand-separator
          icon="group"
          label="Administración"
          caption="Settings"
        >
          <q-card>
            <q-card-section>
              <q-item to="/usuarios">
                <q-item-section avatar>
                  <q-icon name="group"/>
                </q-item-section>

                <q-item-section>
                  Usuarios
                </q-item-section>
              </q-item>
              <q-item to="/grupos">
                <q-item-section avatar>
                  <q-icon name="shield"/>
                </q-item-section>

                <q-item-section>
                  Roles
                </q-item-section>
              </q-item>
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          icon="android"
          label="General"
          caption="Settings"
        >
          <q-card>
            <q-card-section>
              <q-item to="/usuarios">
                <q-item-section avatar>
                  <q-icon name="group"/>
                </q-item-section>

                <q-item-section>
                  Otros
                </q-item-section>
              </q-item>


            </q-card-section>
          </q-card>
        </q-expansion-item>


      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import {ref} from 'vue'

defineOptions({
  name: 'MainLayout'
})

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
