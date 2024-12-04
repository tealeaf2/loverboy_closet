<script setup>
import { ref } from 'vue';

  const isActive= ref(false)
  function toggle(){
    isActive.value=!isActive.value
  }
</script>
  
<template>
  <div class="container" :class="{active:isActive}">
    <div class="form-box login">
      <form action="">
        <h1>Login</h1>
        <div class="input-box">
          <input type="text" placeholder="Username" required>
          <i class='bx bxs-user'></i>
        </div>
        <div class="input-box">
          <input type="password" placeholder="Password" required>
          <i class='bx bxs-lock-alt'></i>
        </div>
        <div class="forgot-link">
          <a href="#">Forgot password?</a>
        </div>
        <button type="submit" class="btn">Login</button>
      </form>
    </div>
    <div class="form-box register">
      <form action="">
        <h1>Registration</h1>
        <div class="input-box">
          <input type="text" placeholder="Username" required>
          <i class='bx bxs-user'></i>
        </div>
        <div class="input-box">
          <input type="password" placeholder="Password" required>
          <i class='bx bxs-lock-alt'></i>
        </div>
        <div class="input-box">
          <input type="password" placeholder="Confirm" required>
          <i class='bx bxs-lock-alt'></i>
        </div>

        <button type="submit" class="btn">Register</button>
      </form>
    </div>

    <div class="toggle-box">
      <div class="toggle-panel toggle-left">
        <h1>Loverboy!</h1>
        <p>Don't have an account?</p>
        <button @click="toggle" class="btn register-btn">Register</button>
      </div>
      <div class="toggle-panel toggle-right">
        <h1>Loverboy!</h1>
        <p>Already have an account?</p>
        <button @click="toggle" class="btn login-btn">Login</button>
      </div>
    </div>

  </div>

  <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
</template>

<style scoped>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .container{
    position: relative;
    width: 850px;
    height: 550px;
    background: var(--secondary-color);
    border-radius: 30px;
    box-shadow: 0 0 30px rgba(0,0,0,.2);
    overflow: hidden;
  }
  .form-box{
    position: absolute;
    width: 50%;
    height: 100%;
    background: var(--secondary-color);
    right: 0;
    display: flex;
    align-items: center;
    text-align: center;
    color: #333;
    padding: 40px;
    z-index: 1;
    visibility: visible;
    transition: .6s ease-in-out 1.2s, visibility 0s 1s;
  }

  .container.active .form-box{
    right: 50%;

  }
  .container.active .form-box.login{
    visibility: hidden;
  }

  .form-box.register{
    visibility: hidden;
  }
  .container.active .form-box.register{
    visibility: visible;
  }

  form{
    
    width: 100%;

  }
  .container h1{
    font-size: 36px;
    margin: -10px 0;
  }
  .input-box{
    position: relative;
    margin: 30px 0;
  }
  .input-box input{
    width: 100%;
    padding: 13px 50px 13px 20px;
    background: #eee;
    border-radius: 8px;
    border: none;
    outline: none;
    font-size: 16px;
    color: #333;
    font-weight: 500;
  }
  .input-box input::placeholder{
    color: #888;
    font-weight: 400;
  }
  .input-box i{
    position: absolute;
    right: 20px;
    /* tip to place icon at center */
    top: 50%; 
    transform: translateY(-50%);
    font-size: 20px;
    color: #888;
  }
  .forgot-link{
    margin: -15px 0 15px;
  }
  .forgot-link a{
    font-size: 14.5px;
    color: #333;
    text-decoration: none;
  }
  .btn{
    width: 100%;
    height: 48px;
    background: #c07858;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, .1);
    border: none;
    cursor: pointer;
    font-size: 16px;
    color: #fff;
    font-weight: 600;
  }
  .toggle-box{
    position: absolute;
    width: 100%;
    height: 100%;
    /* background: purple; */
  }
  /* .toggle-box *{
    box-shadow: 0 0 5px rgba(0, 0, 0, .1);
  } */
  .toggle-box::before{
    content: '';
    position: absolute;
    left: -250%;
    width: 300%;
    height: 100%;
    background: #c07858;
    z-index: 2;
    border-radius: 150px;
    transition: 1.8s ease-in-out;
  }

  .container.active .toggle-box::before{
    left: 50%;
  }

  .toggle-panel{
    position: absolute;
    width: 50%;
    height: 100%;
    /* background: seagreen; */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #fff;
    z-index: 3;
    transition: .6s ease-in-out;
  }

  .toggle-panel.toggle-left{
    left: 0;
    transition-delay: 1.2s;
  }
  .container.active .toggle-panel.toggle-left{
    left: -50%;
    transition-delay: .6s;
  }

  .toggle-panel.toggle-right{
    right: -50%;
    transition-delay: .6s;
  }

  .container.active .toggle-panel.toggle-right{
    right: 0;
    transition-delay: 1.2s;
  }

  .toggle-panel p{
    margin: 20px;
    font-size: 14.5px;
  }

  .toggle-panel .btn{
    width: 160px;
    height: 46px;
    background: transparent;
    border: 2px solid #fff;
    box-shadow: none;
  }

  .logo{
    position: absolute;
    width: 50%;
    height: 100%;
    left: 0;
    top:0;
    z-index: 2;
    display: flex;
    align-items: center;
    justify-content: center;
    left: 0;
    transition: 1.2s ease-in-out;
  }
  .logo svg{
    width: 9vw;
    transform: translateY(-44%);
  }
  .container.active .logo{
    left: 50%;
  }

</style>
