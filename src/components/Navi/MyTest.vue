<template>
    <el-container>
        <el-header style="width:100%;background-color: #636363; overflow: hidden">网站首页</el-header>
        <el-container>
            <el-aside width="200px">
                <div>
                    <el-menu default-active="1" class="el-menu-vertical-demo" style="min-height:800px" @select="handleSelect">
                        <el-menu-item index="1"><i class="el-icon-message"></i>导航一</el-menu-item>
                        <el-menu-item index="2"><i class="el-icon-menu"></i>导航二</el-menu-item>
                        <el-menu-item index="3"><i class="el-icon-setting"></i>导航三</el-menu-item>
                    </el-menu>
                </div>
            </el-aside>
            <el-main>
                <div style="margin-top:10px">
                    <router-view></router-view>
                </div>
            </el-main>
        </el-container>
    </el-container>
</template>

<script type="text/ecmascript-6">
    export default {
        data(){
            return {
                searchCriteria: '',
                breadcrumbItems: ['导航一'],
            }
        },

        methods:{
            handleIconClick(ev) {
                console.log(ev);
            },

            handleSelect(key, keyPath){
                switch(key){
                    case '1':
                        this.$router.push('/Page1');
                        this.breadcrumbItems  = ['导航一']
                        break;
                    case '2':
                        this.$router.push('/Page2')
                        this.breadcrumbItems  = ['导航二']
                        break;
                    case '3':
                        this.$router.push('/Page3')
                        this.breadcrumbItems  = ['导航三']
                        break;
                }
            },

        },
    }
</script>