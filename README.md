# alibb - 阿里巴巴国际站批量管理系统

## 项目概述

阿里巴巴国际站批量管理系统（alibb）是一个基于Laravel框架开发的Web应用，用于帮助用户高效管理阿里巴巴国际站的产品、订单和客户信息。系统提供了批量操作功能，大幅提高了跨境电商卖家的工作效率。

## 功能模块

### 用户管理
- 用户注册与登录
- 用户角色与权限管理
- 用户信息管理

### 产品管理
- 产品信息批量导入与导出
- 产品属性管理
- 产品价格区间设置
- 产品图片管理

### 订单管理
- 订单批量处理
- 订单状态跟踪
- 订单数据统计

### 系统管理
- 菜单管理
- 角色权限配置
- 系统日志

## 技术栈

### 后端
- PHP >= 5.5.9
- Laravel 5.1.x
- MySQL 数据库

### 前端
- HTML/CSS/JavaScript
- jQuery
- Bootstrap

### 第三方集成
- 阿里巴巴国际站API集成
  - APP_KEY 和 APP_SECRET 配置
  - 产品同步功能

## 安装部署

### 系统要求
- PHP >= 5.5.9
- OpenSSL PHP 扩展
- PDO PHP 扩展
- Mbstring PHP 扩展
- Tokenizer PHP 扩展
- MySQL 数据库

### 安装步骤

1. 克隆代码库
```bash
git clone [仓库地址] alibb
cd alibb
```

2. 安装依赖
```bash
composer install
```

3. 配置环境
```bash
cp .env.example .env
# 编辑.env文件，配置数据库连接信息
```

4. 生成应用密钥
```bash
php artisan key:generate
```

5. 数据库迁移
```bash
php artisan migrate
```

6. 数据填充（可选）
```bash
php artisan db:seed
```

## 使用说明

### 阿里巴巴API配置

在 `app/Helper/define.php` 文件中配置阿里巴巴国际站API信息：
```php
define("APP_KEY", '你的APP_KEY');
define("APP_SECRET", '你的APP_SECRET');
define("REDIRECT_URL", '你的回调地址');
```

### 系统登录

- 默认管理员账号：admin
- 默认密码：sys2015（可在 `app/Helper/define.php` 中修改）

### 权限配置

1. 登录系统后，进入「菜单管理」创建系统菜单
2. 在「角色管理」中创建角色并分配菜单权限
3. 在「用户管理」中为用户分配角色

### 产品管理

1. 通过API同步阿里巴巴国际站产品
2. 批量编辑产品信息
3. 设置产品价格区间

## 开发说明

### 目录结构

- `app/` - 应用核心代码
  - `Http/Controllers/` - 控制器
  - `Models/` - 数据模型
  - `Helper/` - 辅助函数和常量定义
- `config/` - 配置文件
- `database/` - 数据库迁移和填充
- `public/` - 公共资源文件
- `resources/views/` - 视图文件

### 路由说明

- 后台路由：`app/Http/routes_admin.php`
- API路由：`app/Http/routes_api.php`

## 联系与支持

如有问题或建议，请联系系统管理员。

## 许可协议

本项目遵循 [MIT 许可协议](LICENSE)。
