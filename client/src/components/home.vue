<template>
  <v-container>
      
    <v-row justify="center" align="center">
        <div class="font">
    <v-col cols="20" >
        <v-flex mb-4>
      <h1>username : {{user.id}}</h1>
      <h1>เข้าสู่ระบบในฐานะ : {{user.job}}</h1>
        </v-flex>
      </v-col>
        <v-col cols="20" >
         <v-row justify="center">
                <v-col cols="20">
               <img class="btlinhome" src="../assets/1.png" v-on:click="goPostPatient" 
                    style="width:500px;height:200px;"
                 />                                
                </v-col>
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/2.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/3.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>               
              </v-row>

               <v-row justify="center">
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/4.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/5.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/6.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>               
              </v-row>

               <v-row justify="center">
                <v-col cols="20">
                 <img class="btlinhome" src="../assets/7.png" v-on:click="redirect_to_login" 
                    style="width:500px;height:200px;"
                 />
                </v-col>
            </v-row>


        </v-col>
        </div>
      </v-row>

    
     
            

  </v-container>
</template>



<script>
import http from "../http-common";
export default {
  name: "home",
  data() {
    return {
      Patient: {
        
      },
      valid: false,
      customerCheck: false,
      customerName: "",
      user:{}
      //+this.$route.params.id
    };
  },
  methods: {
    /* eslint-disable no-console */
     getUser() {
      http
        .get("/User/"+this.$route.params.id)
        .then(response => {
          this.user = response.data;
          console.log(response.data);
        })
        .catch(e => {
          console.log(e);
        });
    },
  
    goPostPatient(){
        this.$router.push("/patient/" + this.$route.params.id);
        window.location.reload()
    }
 
   
  },
  mounted() {
    this.getUser();
    
  }
};
</script>
<style>
    .btlinhome{
        box-shadow: 10px 10px 5px grey;
        
    }

</style>