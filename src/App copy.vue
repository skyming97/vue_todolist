<template>
  <div id="app">
    <a-input placeholder="请输入任务" class="my_ipt" />
    <a-button type="primary">添加事项</a-button>

    <a-list bordered :dataSource="list" class="dt_list">
      <a-list-item slot="renderItem" slot-scope="item">
        <!-- 复选框 -->
        <a-checkbox>{{item.info}}</a-checkbox>
        <!-- 删除链接 -->
        <a slot="actions">删除</a>
      </a-list-item>

      <!-- footer区域 -->
      <div slot="footer" class="footer">
        <!-- 未完成的任务个数 -->
        <span>0条剩余</span>
        <!-- 操作按钮 -->
        <a-button-group>
          <a-button type="primary">全部</a-button>
          <a-button>未完成</a-button>
          <a-button>已完成</a-button>
        </a-button-group>
        <!-- 把已经完成的任务清空 -->
        <a>清除已完成</a>
      </div>
    </a-list>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      list: [
        {
          id: 0,
          info: 'Racing car sprays burning fuel into crowd.',
          done: false
        },
        { id: 1, info: 'Japanese princess to wed commoner.', done: false },
        {
          id: 2,
          info: 'Australian walks 100km after outback crash.',
          done: false
        },
        { id: 3, info: 'Man charged over missing wedding girl.', done: false },
        { id: 4, info: 'Los Angeles battles huge wildfires.', done: false }
      ]
    }
  }
}
</script>

<style scoped>
#app {
  padding: 10px;
}

.my_ipt {
  width: 500px;
  margin-right: 10px;
}

.dt_list {
  width: 500px;
  margin-top: 10px;
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
