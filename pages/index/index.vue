<template>
  <view class="content">
    <button type="default" @click="openPicker()">打开col-picker组件</button>
    <ydl-col-picker
      ref="colPicker"
      :range="dataList"
      :checkValue="checkValue"
      :multiple="true"
      rangeKey="name"
      @confirm="confirmPicker"
    ></ydl-col-picker>
  </view>
</template>
  
  <script>
export default {
  data() {
    return {
      dataList: [
        {
          id: 1,
          name: "前端",
          children: [
            {
              id: 11,
              name: "Vue",
            },
            {
              id: 12,
              name: "React",
            },
          ],
        },
        {
          id: 2,
          name: "后端",
          children: [
            {
              id: 21,
              name: "Node",
            },
            {
              id: 22,
              name: "PHP",
            },
          ],
        },
        {
          id: 3,
          name: "运维",
          children: [
            {
              id: 31,
              name: "Linux",
            },
            {
              id: 32,
              name: "Docker",
            },
            {
              id: 33,
              name: "K8S",
            },
          ],
        },
        {
          id: 4,
          name: "测试",
          children: [
            {
              id: 41,
              name: "JMeter",
            },
            {
              id: 42,
              name: "Selenium",
            },
          ],
        },
        {
          id: 5,
          name: "设计",
          children: [
            {
              id: 51,
              name: "PS",
            },
            {
              id: 52,
              name: "UI",
            },
            {
              id: 53,
              name: "UE",
            },
          ],
        },
        {
          id: 6,
          name: "网络",
          children: [
            {
              id: 61,
              name: "HTTP",
            },
            {
              id: 62,
              name: "HTTPS",
            },
          ],
        },
        {
          id: 7,
          name: "硬件",
          children: [
            {
              id: 71,
              name: "Arduino",
            },
            {
              id: 72,
              name: "Raspberry",
            },
          ],
        },
      ],
      checkValue: {
        1: [12],
        3: [31, 33],
      },
    };
  },
  onLoad(options) {},
  methods: {
    openPicker() {
      this.$refs.colPicker.open();
    },
    confirmPicker(e) {
      console.log(e);
      this.checkValue = e;
    },
  },
};
</script>
  
  <style scoped></style>
  