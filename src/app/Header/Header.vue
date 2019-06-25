<template>
  <v-toolbar
    color="vTyoobRed"
    dense
    fixed
    dark
    clipped-left
    :height="64"
    app
  >
    <v-toolbar-side-icon @click="toggleDrawer"/>
    <router-link class="hidden-sm-and-down"
      @click.native="sendLogoClickGA"
      aria-label="home" 
      :to="{name: 'home'}">
      <img 
        class="logo mr-2" 
        alt="Youtube Logo"
        src="/img/full-logo-white.png">
    </router-link>
<!--mobile-->

    <v-layout 
      row 
      justify-center>
      <v-flex class="hidden-md-and-up">
        <v-form 
          @submit.prevent="searchVideos">
          <v-combobox
            ref="searchBox"
            :menu-props="{
              transition: 'slide-y-transition'
            }"
            clearable
            class="mx-3"
            no-filter
            :loading="searching"
            :items="searchSuggestions"
            :append-icon="null"
            :search-input.sync="query"
            v-model="searchSelectedValue"
            @input="searchVideos"
            dark
            flat
            full-width
            prepend-inner-icon="search"
            hide-no-data
            hide-details
            :label="$t('searchHeaderPlaceholder')"
            solo-inverted
          />
        </v-form>

      </v-flex>
    </v-layout>

<!--mobile-->
    <v-layout 
      row 
      justify-center>
      <v-flex class="hidden-sm-md-and-down">
        <v-form 
          @submit.prevent="searchVideos">
          <v-combobox
            ref="searchBox"
            :menu-props="{
              transition: 'slide-y-transition'
            }"
            clearable
            class="mx-3"
            no-filter
            :loading="searching"
            :items="searchSuggestions"
            :append-icon="null"
            :search-input.sync="query"
            v-model="searchSelectedValue"
            @input="searchVideos"
            dark
            flat
            full-width
            prepend-inner-icon="search"
            hide-no-data
            hide-details
            :label="$t('searchHeaderPlaceholder')"
            solo-inverted
          />
        </v-form>

      </v-flex>
    </v-layout>
  

<v-spacer></v-spacer>
    <v-btn icon>
      <v-icon>more_vert</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<style scoped>
.logo {
  height: 28px;
  margin-top: 8px;
}
</style>






<script>
import Header from "./Header.ts";
export default Header;
</script>
