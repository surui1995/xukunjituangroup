<template>
  <navbar>
    <button class="navbar-toggler mobile-sidebar-toggler d-lg-none" type="button" @click="mobileSidebarToggle">&#9776;</button>
    <!--<a class="navbar-brand" ></a>-->
    <p class="" style="color:white;float:left;margin-left: 10px;
    margin-top: 0px;
    font-size: 18px;">卡地之家后台管理系统</p>
    <!-- <div id="timo" >
    <a href="javascript:void(0)" style="float: left;margin-left: -143px; margin-top: 133px;" >
           <span slot="button">
          <img src="static/img/avatars/6.jpg" class="img-avatar" alt="o" style="width: 80px;
    height: 80px;
    float: left;">
          <span class="d-md-down-none" style="float: left;
    margin-top: 89px;
    margin-left: -61px;">admin</span>
          </span>
        </a>
    </div>     -->
    
    <ul class="nav navbar-nav d-md-down-none">
      <li class="nav-item">
        <a class="nav-link navbar-toggler sidebar-toggler" id="lol" @click="sidebarMinimize">&#9776;</a>
      </li>
     
    </ul>
    <ul class="nav navbar-nav d-md-down-none">
      <li class="nav-item">
        <Input v-model="value4" icon="ios-search" placeholder="搜索" style="width: 200px"></Input>         
      </li>
     
    </ul>

    <!--<ul class="nav navbar-nav d-md-down-none">    
       <li class="nav-item header-item">
          <router-link tag="div" to='/'  style="height:55px;" class="nav-link">
            <p><Icon type="compose" size='30' color="#2d8cf0"></Icon></p>
            <p  style="color:white"> 留言管理 </p>
        </router-link> 
      </li>
        <li class="nav-item header-item">       
        <router-link tag="div" to='/home1'  style="height:55px;" class="nav-link">
            <p><Icon type="stats-bars" size='30' color="#2d8cf0"></Icon></p>
            <p  style="color:white"> 浏览排行 </p>
        </router-link> 
      </li>
   <li class="nav-item header-item">    
        <Dropdown>
      <router-link tag="div" to='/'  style="height:55px;" class="nav-link">
            <p><Icon type="android-cloud" size='30' color="#2d8cf0"></Icon></p>
            <p  style="color:white"> 云服务器 </p>
        </router-link>
        <DropdownMenu slot="list">
            <DropdownItem>Linux</DropdownItem>
            <DropdownItem>Mac OS X</DropdownItem>
            <DropdownItem>Windows</DropdownItem>
            
            <DropdownItem>Core OS</DropdownItem>
        </DropdownMenu>
    </Dropdown>
      </li>
        <li class="nav-item header-item">
         <router-link tag="div" to='/home1'  style="height:55px;" class="nav-link">
            <p><Icon type="trophy" size='30' color="#2d8cf0"></Icon></p>
            <p  style="color:white"> 销量排行 </p>
        </router-link> 
      </li>     
    </ul>
    -->


    <ul class="nav navbar-nav ml-auto" style="position: initial;">
      
      <li class="nav-item d-md-down-none">
        <a class="nav-link" ><Icon type="android-notifications" size="20"></Icon><span class="badge badge-pill badge-danger">5</span></a>
      </li>


      <Dropdown class="nav-item">
        <a href="javascript:void(0)">
           <span slot="button">
          <img src="static/img/avatars/6.jpg" class="img-avatar" alt="o">
          <span class="d-md-down-none" style="margin-left:10px;">admin</span>
          </span>
        </a>
        <Dropdown-menu slot="list">
            <Dropdown-item>
              <p class="dropdown-itemp"><Icon type="alert"></Icon>更新<span class="badge badge-info">2</span></p>

            
            </Dropdown-item>
            <Dropdown-item>
              <p class="dropdown-itemp"><Icon type="chatbox-working"></Icon>消息<span class="badge badge-success">42</span></p>

            </Dropdown-item>
             <Dropdown-item>
              <p class="dropdown-itemp">  <Icon type="chatbox-working"></Icon>消息<span class="badge badge-danger">42</span></p>

           </Dropdown-item>
              <Dropdown-item divided>
              <p class="dropdown-itemp"><Icon type="android-contact"></Icon> 轮廓</p>

              </Dropdown-item>
            <Dropdown-item >
              <p class="dropdown-itemp"><Icon type="android-settings"></Icon> 设置</p>
              </Dropdown-item>

                 <Dropdown-item > <a href="" @click="Logout"  ><p  class="dropdown-itemp"><Icon type="power"></Icon>退出</p></a></Dropdown-item>

        </Dropdown-menu>
    </Dropdown>

 
      <li class="nav-item d-md-down-none">
        <a class="nav-link navbar-toggler aside-menu-toggler"  @click="asideToggle">&#9776;</a>
      </li>
    </ul>
  </navbar>
</template>
<script type="text/javascript" src="http://www.sz886.com/js/jquery-1.9.1.min.js"></script>
 <script type="text/javascript"> 
$(document).ready(function(e) { 
    $("#lol").click(function(){
         if(!$("#timo").is(":visible")){
          $("#timo").hide(); 
         }else{ 
          $("#timo").show(); 
        }
    });      
});
</script>
<script>

import navbar from './Navbar'

export default {
  name: 'header',
  components: {
    navbar,
    
  },
  methods: {
    Logout(e){
         e.preventDefault();
         this.$store.dispatch('LogOut').then(() => {
                this.$router.push({ path: '/login' });
              }).catch(err => {
                this.$message.error(err);
              });
    },
    click () {
      // do nothing
    },
    sidebarToggle (e) {
      e.preventDefault()
      document.body.classList.toggle('sidebar-hidden')
    },
    sidebarMinimize (e) {
      e.preventDefault()

      document.body.classList.toggle('sidebar-minimized')
    },
    mobileSidebarToggle (e) {
      e.preventDefault()

      document.body.classList.toggle('sidebar-mobile-show')
    },
    asideToggle (e) {
      e.preventDefault()
      document.body.classList.toggle('aside-menu-hidden')
    }
  }
}
</script>

<style type="text/css" scoped>
  .dropdown-itemp{
    text-align: left;
    font-size: 15px;
    padding: 10px;
  }
 .header-item .ivu-dropdown-item{
  padding: 15px;
}
  .header-item{
    width: 130px;
    /*background-color: #20a8d8;*/
    /*background-color: white;*/

    height: 55px;
    
    
  }
  .header-item a{
        color:white !important;

  }

</style>
