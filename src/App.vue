<template>
  <div id="app">
    <!-- <el-button-group></el-button-group> -->
    <el-button icon="edit"  @click='doDefaultTap' size='large' :disabled='true'>默认按钮</el-button>
    <el-button :loading='true' type='primary' >主要按钮</el-button>
    <el-button type='text'>文字按钮</el-button>  
    <div>
      <el-button-group>
        <el-button icon="arrow-left" type="primary">上一页</el-button>
        <el-button type="primary">下一页<i class="el-icon-arrow-right el-icon--right"></i></el-button>
      </el-button-group>        
    </div> 
    <div>
      <el-button-group>
        <el-button icon="edit" type="primary"></el-button>
        <el-button icon="share" type="primary"></el-button>
        <el-button icon="delete" type="primary"></el-button> 
      </el-button-group>
    </div>  
    <div>
      <el-button type="text" @click="dialogVisible=true">点击打开Dialog</el-button>
      <el-dialog class="el-dialog__wrapper" title="提示" :visible.sync="dialogVisible">
        <span>这是一段信息</span>
        <span slot="footer" class="dialog-footer">
          <el-button @click="dialogVisible=false">取消</el-button>
          <el-button type="primary" @click="dialogVisible=false">确定</el-button>
        </span>
      </el-dialog>
    </div>     
    <!-- <router-view></router-view> -->
    <div>
    <span class="demonstration">默认Hover指示器处罚</span>
    <el-carousel :interval='1000' :initialIndex="2" height="150px">
      <el-carousel-item v-for="item in 4" :key="item">
        <h3>{{item}}</h3>
      </el-carousel-item>
    </el-carousel>
  </div>
  </div>
</template>

<script>
import ElDialog from './components/ElDialog.vue'
import ElButton from './components/ElButton.vue'
import ElButtonGroup from './components/ElButtonGroup.vue'
import ElCarousel from './components/ElCarousel.vue'
import ElCarouselItem from './components/ElCarouselItem.vue'
export default {
  name: 'app',
  data() {
    return {
      dialogVisible: false
    }
  },
  components: {
    'el-button': ElButton,
    'el-button-group':ElButtonGroup,
    'el-dialog':ElDialog,
    'el-carousel': ElCarousel,
    'el-carousel-item':ElCarouselItem
  },
  methods: {
    doDefaultTap(evt) {
      console.log('doDefaultTap')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: .75;
  line-height: 150px;
  margin: 0;
  text-align: center;
}
.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}
.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}
</style>
