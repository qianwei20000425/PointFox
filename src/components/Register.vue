<template>
  <div id="loginWrapper">
    <div id="loginConnect">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>用户注册</span>
          <el-button style="float: right; padding: 3px 0" type="text">忘记密码</el-button>
        </div>
        <div id="loginContentBody">
            <el-input id="newusername" v-model="newUser.newusername" clearable></el-input>
            <el-input id="newpassword" v-model="newUser.newpassword" show-password clearable></el-input>
        </div>
        <div id="loginSubmit">
            <el-button id="systemSubmit" @click="registerSystem">注册</el-button>
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
import Axios from 'axios'
export default {
  name:'register',
    data(){
        return{
            newUser:{
                newusernmae:"",
                newpassword:""
            }
        }
    },
    methods: {
      registerSystem(){
        Axios.get('http://localhost:3000/register',{
            params:this.newUser
        }).then(function(response){

          alert(response)
        })
      }
    },
};
</script>

<style>
    #loginWrapper{
        /* background-color: thistle; */
        height: 100%;
    }
    #loginConnect{
        width: 400px;
        margin: 0 auto;
        padding-top: 100px;
    }
    #systemSubmit{
        display: block;
        margin: 0 auto;
        background-color: #0a9588;
        color: white;
        border-color: #0a9588;
    }
    #newpassword{
      margin-top: 5px;
      margin-bottom: 8px;
    }

</style>