<template>
  <div class="cart">
    <!-- 导航 -->
    <nav-bar class="nav-bar">
      <div slot="center">购物车({{Length}})</div>
    </nav-bar>

    <!-- 商品的列表 -->
    <cart-list />

    <!-- 底部汇总 -->
    <cart-bottom-bar />
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'

import CartList from './childComps/CartList'
import CartBottomBar from './childComps/CartBottomBar'

import {mapGetters} from 'vuex'
  export default {
    name: 'Cart',
    components: {
      NavBar,
      CartList,     
      CartBottomBar
    },
    computed: {
      // 两种语法
      // 第一种，数组，直接原来函数的名字
      // ...mapGetters(['cartLength'])

      // 第二种，对象，另取名字
      ...mapGetters({
        Length: 'cartLength'
      })
    },
  }
</script>
<style scoped>
  .cart{
    height: 100vh;
    overflow: hidden;
  }
  .nav-bar{
    background-color: var(--color-tint);
    color: #fff;
    /* font-weight: 700; */
  }
</style>