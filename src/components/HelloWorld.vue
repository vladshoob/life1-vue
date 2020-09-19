<template>
  <div class="hello">
    <h1>"Life" in Vue</h1>
    <input type="number" v-model="columns">
    <input type="number" v-model="rows">
    <input type="number" v-model="iterations" disabled>

    <div id="life">
      <table>
        <tr v-for="rowNumber in rows" :key="rowNumber">
            <td class="cell"
                v-for="columnNumber in columns"
                :key="columnNumber"
                @click=inhabit(columnNumber, rowNumber)>
              {{rowNumber + '.' + columnNumber}}
            </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      columns: 5,
      rows: 5,
      iterations: 0,
      population: [],
    }
  },
  methods: {
    inhabit: function (column, row) {
      this.population[column][row] = true;
    }
  }
}
</script>

<style>
  #life table {
    margin-top: 25px;
    border-spacing: 0px;
  }

  #life .cell {
    width: 40px;
    height: 40px;
    border: 1px black solid;
  }
</style>