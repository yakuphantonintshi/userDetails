<template>
<form action="" class="container">
  <input type="text" placeholder="First name" required v-model="firstName">
  <input type="text" placeholder="Last name" required v-model="lastName">
  <input type="text" placeholder="Gender" required v-model="gender" :class="{
    male: lowerCaseGender == 'male', female: lowerCaseGender == 'female'
  }">
  <textarea output readonly ></textarea>
  <button type="button" @click="userInfo">Display</button>


</form>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      firstName:'',
      lastName:'',
      gender:''
    }
  },
  computed: {
    lowerCaseGender(){
      return this.gender.toLowerCase()
    }
  },
  methods: {
    userInfo(){
      document.querySelector('[output]').textContent = `
      First name: ${this.firstName}
      Last name: ${this.lastName}
      Gender: ${this.gender}
      `
    }
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  display: grid;
  gap: .5rem;
  width: 30rem;
  margin-inline: auto;
  & input{
    text-align: center;
  }
}
.male{
  background-color:blue;
}
.female{
  background-color:rgb(249, 21, 150);
}
</style>
