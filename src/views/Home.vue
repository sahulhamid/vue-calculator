<template>
  <div class="calculator">
    <input type="text" v-model="display" />
    <div>
      <button v-on:click="displayValue('1')">1</button>
      <button v-on:click="displayValue('2')">2</button>
      <button v-on:click="displayValue('3')">3</button>
      <button v-on:click="displayValue('+')">+</button>
    </div>
    <div>
      <button v-on:click="displayValue('4')">4</button>
      <button v-on:click="displayValue('5')">5</button>
      <button v-on:click="displayValue('6')">6</button>
      <button v-on:click="displayValue('-')">-</button>
    </div>
    <div>
      <button v-on:click="displayValue('7')">7</button>
      <button v-on:click="displayValue('8')">8</button>
      <button v-on:click="displayValue('9')">9</button>
      <button v-on:click="displayValue('*')">*</button>
    </div>
    <button v-on:click="allClear">ac</button>
    <button v-on:click="displayValue('0')">0</button>
    <button v-on:click="calculateValue">=</button>
    <button v-on:click="displayValue('/')">/</button>
  </div>
</template>
  

<script>
import { ref } from "vue";

export default {
  setup() {
    const display = ref("");

    const displayValue = (val) => {
      display.value += val;
    };

    const calculateValue = () => {
      display.value = eval(display.value);
    };

    const allClear = () => {
      display.value = "";
    };
    return { display, displayValue, calculateValue, allClear };
  },
};
</script>

<style>
.calculator {
  background-color: white;
  max-width: 380px;
  padding: 10px;
  margin: 70px auto;
  border-radius: 10px;
  box-shadow: 4px 4px rgb(34, 33, 33);
}

input {
  display: block;
  margin: 10px auto;
  padding: 10px;
  border: none;
  border: 2px solid rgb(14, 226, 198);
  border-radius: 10px;
  background-color: rgb(253, 43, 201);
  color: white;
  font-size: 20px;
}
button {
  border: none;
  background: none;
  border: 2px solid rgb(14, 226, 198);
  border-radius: 10px;
  background-color: rgb(253, 43, 201);
  color: white;
  font-size: 18px;
  padding: 20px;
  margin: 10px;
}
</style>

