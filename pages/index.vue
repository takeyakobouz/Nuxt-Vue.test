<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <div class="text-center">
        <logo />
        <vuetify-logo />
      </div>
      <v-card>
        <v-card-title class="headline">
          Welcome to the Vuetify + Nuxt.js template
        </v-card-title>
        <v-card-text>

          <div id="app">
            <h1 class="title">
              アプリ名
            </h1>
            <input type="text" v-model="newItem">
            <form v-on:submit.prevent>
              <button v-on:click="addItem">add</button>
            </form>
            <li v-for="todo in todos">
              {{ todo.item }}
            </li>
            <h2 class="subtitle">
              アプリ名
            </h2>
          </div>

          <hr class="my-4"/>

          <v-spacer />
          <a href="https://github.com/takeyakobouz/Nuxt-Vue.test" target="_blank">
            <v-btn color="success">GITHUB</v-btn>
          </a>
          <v-btn color="primary" nuxt to="/inspire">Continue</v-btn>

        </v-card-text>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data() {
    return {
      newItem: '',
      todos: []
    }
  },
  methods: {
    addItem: function(event) {
      var todo = {
        item: this.newItem
      };
    this.todos.push(todo)
    }
  }
}
</script>
