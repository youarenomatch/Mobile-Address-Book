<template>
  <div id="app">
    <mt-header title="标题过长会隐藏后面的内容啊哈哈哈哈" fixed>
      <mt-button icon="back" slot='left'>返回</mt-button>
      <mt-button icon="more" slot="right"></mt-button>
    </mt-header>
    <mt-index-list>
  <!-- <mt-index-section index="A">
    <mt-cell title="Aaron"></mt-cell>
    <mt-cell title="Alden"></mt-cell>
    <mt-cell title="Austin"></mt-cell>
  </mt-index-section>
  <mt-index-section index="B">
    <mt-cell title="Baldwin"></mt-cell>
    <mt-cell title="Braden"></mt-cell>
  </mt-index-section> -->
  <mt-index-section v-for="(item,index) in userDate" :key="index" :index="item.index">
    <mt-cell v-for="(user,index) in item.users" :key="index" :title="user.name" @click.native="telAlert(user.tel)"></mt-cell>
    </mt-index-section>
</mt-index-list>
  </div>
</template>

<script>

  import { MessageBox } from 'mint-ui';

var userDate=[
  {
    "index":"A","users":[
      {
        "name":"a1","tel":"1301111111"
      },
      {
        "name":"a2","tel":"130222222"
      },
      {
        "name":"a3","tel":"1301444444"
      }
    ]
  },
  {
    "index":"B","users":[
      {
        "name":"b1","tel":"1301111111"
      },
      {
        "name":"b2","tel":"130222222"
      },
      {
        "name":"b3","tel":"1301444444"
      }
    ]
  },
  {
    "index":"C","users":[
      {
        "name":"c1","tel":"1301111111"
      },
      {
        "name":"c2","tel":"130222222"
      },
      {
        "name":"c3","tel":"1301444444"
      }
    ]
  },
]
export default {
  name: 'App',
  data(){
    return {
      userDate:userDate
    }
  },
  methods:{
    telAlert:function (tel) {
      MessageBox({
        title: '呼叫',
        message: tel,
        showCancelButton: true
      });
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
</style>
