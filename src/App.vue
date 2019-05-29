<template>
  <div id="app">
    <optional-tree
      ref="tree"
      :data="data"
      show-checkbox
      node-key="id"
      :check-strictly="true"
      default-expand-all>
    </optional-tree>
    
    <el-button @click="getCheckedKeys">获取</el-button>
  </div>
</template>

<script>
import optionalTree from '@/components/optional-tree/tree';
export default {
  data () {
    return {
      data: [{
        id: 1,
        label: '一级 1',
        children: [{
          id: 11,
          label: '二级 1-1',
          children: [{
            id: 111,
            label: '三级 1-1-1'
          }, {
            id: 112,
            label: '三级 1-1-2'
          }]
        },
        {
          id: 12,
          label: '二级 1-2',
          children: [{
            id: 121,
            label: '二级 1-2-1'
          }, {
            id: 122,
            label: '二级 1-2-2'
          }]
        }]
      }, {
        id: 2,
        label: '一级 2',
        children: [{
          id: 21,
          label: '二级 2-1'
        }, {
          id: 22,
          label: '二级 2-2'
        }]
      }]
    };
  },
  methods: {
    getCheckedKeys () {
      console.log(this.$refs.tree.getCheckedKeys());
    }
  },
  components: {
    optionalTree
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
