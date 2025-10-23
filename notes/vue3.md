# Vue3

## 新特性

- 引入RFC机制
- 响应式系统优化 Proxy替代defineProperty

  - 支持数组索引和对象属性的动态添加/删除
  - 更好的性能表现
  - 减少内存占用
- 全部模块使用TypeScript重构
- Composition API 组合语法

  - OptionAPI 一个功能的代码零散的分布在data，methods等配置内
  - CompostionAPI 每个功能模块都维护在一起
- 新的组件支持

  - Vue3内置了Fragment、Teleport和Suspense三个新组件
    - Fragment: Vue3组件不再要求有一个唯一的根节点，清除了很多无用的占位div
    - Teleport: 允许组件渲染在别的元素内，主要开发弹框窗口组件时特别有用
    - Suspense: 异步组件，更方便开发有异步请求的组件
- 工程化提升

  - 新一代工程化工具 Vite更快的开发服务器

    - 冷启动速度提升10-100倍
    - 热更新速度更快
    - 更好的开发体验
  - 构建优化，更小的包体积，支持Tree-shaking，按需引入，减小最终包大小
- 更好的状态管理

Teleport（传送门）

```vue
<!-- 弹窗组件可以渲染到 body 下 -->
<template>
  <div>
    <button @click="showModal = true">打开弹窗</button>
    <Teleport to="body">
      <Modal v-if="showModal" @close="showModal = false" />
    </Teleport>
  </div>
</template>
```

Suspense（异步组件）

```vue
<template>
  <Suspense>
    <template #default>
      <AsyncComponent />
    </template>
    <template #fallback>
      <Loading />
    </template>
  </Suspense>
</template>
```

## 业务收益

* 性能提升: 20-30% 的性能提升
* 开发效率: 更好的开发体验
* 功能增强：新组件和API支持更多业务场景
* 维护成本: 更好的代码结构，降低长期维护成本
* 用户体验: 更流畅的交互和更快的加载速

## 升级

- @vue/compat
