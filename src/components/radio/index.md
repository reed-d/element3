# Radio 单选框

在一组备选项中进行单选

## 基础用法

由于选项默认可见，不宜过多，若选项过多，建议使用 Select 选择器。

:::demo

```html
<el-radio v-model="radio" label="1">备选项</el-radio>
<el-radio v-model="radio" label="2">备选项</el-radio>

<script setup>
  import { ref } from 'vue'
  const radio = ref('2')
</script>
```

:::


## 禁用状态

单选框不可用的状态。

只要在el-radio元素中设置disabled属性即可，它接受一个Boolean，true为禁用。
:::demo

```html
<el-radio disabled v-model="radio" label="禁用">备选项</el-radio>
<el-radio disabled v-model="radio" label="选中且禁用">备选项</el-radio>

<script setup>
  import { ref } from 'vue'
  const radio = ref('选中且禁用')
</script>
```

:::


## 单选框组

适用于在多个互斥的选项中选择的场景

:::demo

```html
<el-radio-group v-model="radio">
  <el-radio :label="3">备选项</el-radio>
  <el-radio :label="6">备选项</el-radio>
  <el-radio :label="9">备选项</el-radio>
</el-radio-group>

<script setup>
  import { ref } from 'vue'
  const radio = ref(6)
</script>
```

:::


## 按钮样式

按钮样式的单选组合。

只需要把el-radio元素换成el-radio-button元素即可，此外，Element 还提供了size属性。
:::demo

```html
<div>
  <el-radio-group v-model="radio1">
    <el-radio-button label="上海"></el-radio-button>
    <el-radio-button label="北京"></el-radio-button>
    <el-radio-button label="广州"></el-radio-button>
    <el-radio-button label="深圳"></el-radio-button>
  </el-radio-group>
</div>
<div style="margin-top: 20px">
  <el-radio-group v-model="radio2" size="medium">
    <el-radio-button label="上海"></el-radio-button>
    <el-radio-button label="北京"></el-radio-button>
    <el-radio-button label="广州"></el-radio-button>
    <el-radio-button label="深圳"></el-radio-button>
  </el-radio-group>
</div>
<div style="margin-top: 20px">
  <el-radio-group v-model="radio3" size="small">
    <el-radio-button label="上海"></el-radio-button>
    <el-radio-button label="北京" disabled></el-radio-button>
    <el-radio-button label="广州"></el-radio-button>
    <el-radio-button label="深圳"></el-radio-button>
  </el-radio-group>
</div>
<div style="margin-top: 20px">
  <el-radio-group v-model="radio4" disabled size="mini">
    <el-radio-button label="上海"></el-radio-button>
    <el-radio-button label="北京"></el-radio-button>
    <el-radio-button label="广州"></el-radio-button>
    <el-radio-button label="深圳"></el-radio-button>
  </el-radio-group>
</div>

<script setup>
  import { ref } from 'vue'
  const radio1 = ref('上海')
  const radio2 = ref('上海')
  const radio3 = ref('上海')
  const radio4 = ref('上海')
</script>
```

:::


## 带有边框

设置border属性可以渲染为带有边框的单选框。

:::demo

```html
<div>
  <el-radio v-model="radio1" label="1" border>备选项1</el-radio>
  <el-radio v-model="radio1" label="2" border>备选项2</el-radio>
</div>
<div style="margin-top: 20px">
  <el-radio v-model="radio2" label="1" border size="medium">备选项1</el-radio>
  <el-radio v-model="radio2" label="2" border size="medium">备选项2</el-radio>
</div>
<div style="margin-top: 20px">
  <el-radio-group v-model="radio3" size="small">
    <el-radio label="1" border>备选项1</el-radio>
    <el-radio label="2" border disabled>备选项2</el-radio>
  </el-radio-group>
</div>
<div style="margin-top: 20px">
  <el-radio-group v-model="radio4" size="mini" disabled>
    <el-radio label="1" border>备选项1</el-radio>
    <el-radio label="2" border>备选项2</el-radio>
  </el-radio-group>
</div>

<script setup>
  import { ref } from 'vue'
  const radio1 = ref('1')
  const radio2 = ref('1')
  const radio3 = ref('1')
  const radio4 = ref('1')
</script>
```

:::


## Radio Attributes

属性 | 说明 | 类型 | 可选值 | 默认值
-- | -- | -- | -- | --
`modelValue / v-model` | 绑定值 | `string` \/ `number` \/ `boolean` | — | —
`label` | Radio 的 value | `string` \/ `number` \/ `boolean` | — | —
`disabled` | 是否禁用 | `boolean` | — | `false`
`border` | 是否显示边框 | `boolean` | — | `false`
`size` | Radio 的尺寸，仅在 border 为真时有效 | `string` | `medium` \/ `small ` \/ `mini` | —
`name` | 原生 name 属性 | `string` | — | —


## Radio Events

事件名称 | 说明 | 回调参数
-- | -- | -- 
`change` | 绑定值变化时触发的事件 | 选中的 Radio label 值


## Radio-group Attributes

参数 | 说明 | 类型 | 可选值 | 默认值
-- | -- | -- | -- | --
`modelValue / v-model` | 绑定值 | `string` \/ `number` \/ `boolean` | — | —
`size` | 单选框组尺寸，仅对按钮形式的 Radio 或带有边框的 Radio 有效 | `string` | `medium` \/ `small ` \/ `mini` | —
`disabled` | 是否禁用 | `boolean` | — | `false`
`text-color` | 按钮形式的 Radio 激活时的文本颜色 | `string` | — | `#ffffff`
`fill` | 按钮形式的 Radio 激活时的填充色和边框色 | `string` | — | `#409EFF`


## Radio-group Events

事件名称 | 说明 | 回调参数
-- | -- | -- 
`change` | 绑定值变化时触发的事件 | 选中的 Radio label 值


## Radio-button Attributes

参数 | 说明 | 类型 | 可选值 | 默认值
-- | -- | -- | -- | --
`label` | Radio 的 value | `string` \/ `number` | — | —
`disabled` | 是否禁用 | `boolean` | — | `false`
`name` | 原生 name 属性 | `string` | — | —

