<style scoped>
  a {
    color: inherit;
  }
  .layout {
    border: 1px solid #d7dde4;
    background: #f5f7f9;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
  }
  .ivu-layout, .layout {
    height: 100%;
  }

  .layout-logo {
    width: 100px;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    float: left;
    position: relative;
    top: 15px;
    left: 20px;
  }

  .layout-nav {
    width: 440px;
    margin: 0 auto;
    margin-right: 20px;
  }
  .layout-nav a {
    color: white;
  }
</style>
<template>
  <div class="layout">
    <Layout>
      <Header>
        <Menu mode="horizontal" theme="dark" active-name="1">
          <div class="layout-logo"></div>
          <div class="layout-nav">
            <router-link to="/">
              <MenuItem name="1">
                <Icon type="ios-navigate"></Icon>
                首页
              </MenuItem>
            </router-link>
            <router-link to="/manger">
              <MenuItem name="2">
                <Icon type="ios-keypad"></Icon>
                平台管理
              </MenuItem>
            </router-link>
            <router-link to="/open">
              <MenuItem name="3">
                <Icon type="ios-analytics"></Icon>
                文档中心
              </MenuItem>
            </router-link>
            <router-link to="/user">
              <MenuItem name="4">
                <Icon type="ios-paper"></Icon>
                个人中心
              </MenuItem>
            </router-link>
          </div>
        </Menu>
      </Header>
      <Layout>
        <Sider hide-trigger :style="{background: '#fff', textAlign: 'left'}">
          <Menu active-name="1-2" theme="light" width="auto" :open-names="['1']">
            <Submenu name="1">
              <template slot="title">
                <Icon type="ios-navigate"></Icon>
                组件
              </template>
              <router-link to="/"><MenuItem name="1-1">From表单</MenuItem></router-link>
              <router-link to="/"><MenuItem name="1-2">Card卡片</MenuItem></router-link>
              <router-link to="/"><MenuItem name="1-3">Layer布局</MenuItem></router-link>
            </Submenu>
            <router-link to="/access/index">
              <MenuItem name="2-1">
                <Icon type="ios-keypad"></Icon>
                权限管理
              </MenuItem>
            </router-link>
            <Submenu name="3">
              <template slot="title">
                <Icon type="ios-analytics"></Icon>
                文章管理
              </template>
              <router-link to="/"><MenuItem name="3-1">文章发布</MenuItem></router-link>
              <router-link to="/"><MenuItem name="3-2">工作流</MenuItem></router-link>
            </Submenu>
            <Submenu name="4">
              <template slot="title">
                <Icon type="flash-off"></Icon>
                错误页面
              </template>
              <router-link to="/404"><MenuItem name="4-1">404找不到页面</MenuItem></router-link>
              <router-link to="/403"><MenuItem name="4-2">403无杼限页面</MenuItem></router-link>
              <router-link to="/500"><MenuItem name="4-3">500服务异常</MenuItem></router-link>
            </Submenu>
          </Menu>
        </Sider>
        <Layout :style="{padding: '0 24px 24px'}">
          <Breadcrumb :style="{margin: '24px 0', textAlign: 'left'}">
            <BreadcrumbItem>Home</BreadcrumbItem>
            <BreadcrumbItem>Components</BreadcrumbItem>
            <BreadcrumbItem>Layout</BreadcrumbItem>
          </Breadcrumb>
          <Content :style="{padding: '24px', minHeight: '280px', background: '#fff'}">
            <router-view/>
          </Content>
        </Layout>
      </Layout>
    </Layout>
  </div>
</template>
<script>
export default {
  name: 'MainFrame'
}
</script>
