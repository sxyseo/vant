# SubmitBar 提交订单栏

### 引入

``` javascript
import Vue from 'vue';
import { SubmitBar } from 'vant';

Vue.use(SubmitBar);
```

## 代码演示

### 基础用法

```html
<van-submit-bar
  :price="3050"
  button-text="提交订单"
  @submit="onSubmit"
/>
```

### 禁用状态

禁用状态下不会触发`submit`事件

```html
<van-submit-bar
  disabled
  :price="3050"
  button-text="提交订单"
  tip="你的收货地址不支持同城送, 我们已为你推荐快递"
  tip-icon="info-o"
  @submit="onSubmit"
/>
```

### 加载状态

加载状态下不会触发`submit`事件

```html
<van-submit-bar
  loading
  :price="3050"
  button-text="提交订单"
  @submit="onSubmit"
/>
```

### 高级用法

通过插槽插入自定义内容

```html
<van-submit-bar
  :price="3050"
  button-text="提交订单"
  @submit="onSubmit"
>
  <van-checkbox v-model="checked">全选</van-checkbox>
  <span slot="tip">
    你的收货地址不支持同城送, <span>修改地址</span>
  </span>
</van-submit-bar>
```

## API

### Props

| 参数 | 说明 | 类型 | 默认值 |
|------|------|------|------|
| price | 价格（单位分） | *number* | - |
| label | 价格左侧文案 | *string* | `合计：` |
| suffix-label | 价格右侧文案 | *string* | - |
| text-align `v2.3.0` | 价格文案对齐方向，可选值为 `right` `left` | *string* | `right` |
| button-text | 按钮文字 | *string* | - |
| button-type | 按钮类型 | *string* | `danger` |
| tip | 提示文案 |  *string* | - |
| tip-icon | 左侧图标名称或图片链接，可选值见 [Icon 组件](#/zh-CN/icon) |  *string* | - |
| disabled | 是否禁用按钮 | *boolean* | `false` |
| loading | 是否显示加载中的按钮 |  *boolean* | `false` |
| currency | 货币符号 | *string* | `¥` |
| decimal-length | 价格小数点后位数 | *number* | `2` |
| safe-area-inset-bottom | 是否开启底部安全区适配，[详细说明](#/zh-CN/quickstart#di-bu-an-quan-qu-gua-pei) | *boolean* | `false` |

### Events

| 事件名 | 说明 | 回调参数 |
|------|------|------|
| submit | 按钮点击事件回调 | - |

### Slots

| 名称 | 说明 |
|------|------|
| default | 自定义订单栏左侧内容 |
| top | 自定义订单栏上方内容 |
| tip | 提示文案中的额外操作和说明 |
