<template>
    <div>
        <h2> Welcome to Vue </h2>
        <p>{{ info }}</p>
    </div>
</template>

<script>
import axios from 'axios';

export default {
name: 'app',
          data () {
              return {
info: null
              }
          },
          mounted () {
              axios
                  .get('https://api.coindesk.com/v1/bpi/currentprice.json')
                  .then(response => (this.info = response))
          }
}
</script>
