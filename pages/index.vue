<!-- eslint-disable -->
<template>
  <div>
    <div class="flex justify-center">
      <h2>Draggable example</h2>
    </div>
    <div class="flex justify-center">
      <button
        @click="addNewForm"
        class="border border-red-300 mt-5 pl-5 pr-5 rounded-lg w-[500px]"
      >
        Add
      </button>
    </div>
    <div class="flex justify-center">
      <draggable v-model="inputValue" class="bigger-area" handle=".handle">
        <!-- <div
          v-for="text in exampleList"
          :key="text"
          class="drag-item flex flex-justify-betweeen"
          @dragend="log('a')"
        >
          {{ text }}
        </div> -->
        <!-- eslint-disable -->

        <div v-for="(text, index) in inputValue">
          <!-- <div class="border border-stone-900">
            <input
              class="border border-stone-900 mt-2 w-[500px] h-[50px]"
              :key="index"
              v-model="text.name"
              @dragend="log('a')"
            />
          </div> -->

          <!-- show number of index in the right side of input  -->
          <div class="flex flex-justify-between" :key="index">
            <input
              class="border border-stone-900 mt-2 w-[500px] h-[50px]"
              v-model="text.name"
              @dragend="log('a')"
            />

            <div
              class="border border-stone-900 mt-2 w-[50px] h-[50px] handle"
              @dragend="log('a')"
            >
              {{ index + 1 }}
            </div>
          </div>
        </div>
      </draggable>
    </div>

    <div class="flex justify-center">
      <button
        class="border border-red-300 mt-5 pl-5 pr-5 rounded-lg w-[500px]"
        @click="handleSubmit"
      >
        submit
      </button>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: "Drag",
  data() {
    return {
      // exampleList: ["Item 1", "Item 2", "Item 3", "Item 4", "Item 5"],
      inputValue: [
        {
          id: 1,
          name: "",
        },
        {
          id: 2,
          name: "",
        },
        {
          id: 3,
          name: "",
        },
        {
          id: 4,
          name: "",
        },
        {
          id: 5,
          name: "",
        },
      ],
    };
  },

  methods: {
    // log: function (...e) {
    //   console.log(...e);
    // },
    // addItem: function () {
    //   this.exampleList.push("Hello_" + parseInt(Math.random() * 100000000));
    // },
    handleSubmit() {
      console.log(this.inputValue);
    },

    addNewForm() {
      this.inputValue.push({
        id: this.inputValue.length + 1,
        name: "",
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
