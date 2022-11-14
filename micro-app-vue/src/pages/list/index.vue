<template>
  <section>
    <a-card title="Vue 微应用列表页">
      <a-table rowKey="_id" :dataSource="data">
        <a-table-column title="菜名" dataIndex="name" />
        <a-table-column title="价格" dataIndex="price" :customRender="(text) => `￥ ${text}`" />
      </a-table>
    </a-card>
  </section>
</template>

<script>

export default {
  name: "List",

  data() {
    return {
      data: [],
    }
  },
  
  methods: {
    fetchVegetable () {
      const vegetableList = [
        {name: '空心菜', price: 5},
        {name: '大白菜', price: 15}
      ] 
      this.data = vegetableList;
    }
  },

  created() {
    this.fetchVegetable();
  }
}
</script>