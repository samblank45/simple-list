<template>
  <div class="quotes-index">
    <div class="container">
      <div v-for="quote in quotes">
        <h1>Title</h1>  
        {{quote.context}}  
        <h3>actor</h3> 
        {{quote.source}} 
        <h3>quote</h3> 
        {{quote.quote}}
        <h3>theme</h3>
        {{quote.theme}}
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
// @ is an alias to /src

export default {
  data: function () {
    return {
      quotes: [],
    };
  },
  created: function () {
    fetch(
      "https://gist.githubusercontent.com/benchprep/dffc3bffa9704626aa8832a3b4de5b27/raw/quotes.json"
    )
      .then((response) => response.json())
      .then((data) => (this.quotes = data));
  },
};
</script>
