# MySite

一个基于 Django 6.1.1 的 Web 应用项目。

## 项目结构

```
e:\mysite\
├── manage.py                 # Django 管理脚本
├── db.sqlite3                # SQLite 数据库文件（备用）
├── mysite/                   # 项目配置文件
│   ├── settings.py           # Django 设置
│   ├── urls.py               # 根 URL 配置
│   ├── wsgi.py               # WSGI 入口
│   └── asgi.py               # ASGI 入口
└── app01/                    # 主应用
    ├── models.py             # 数据模型
    ├── views.py              # 视图函数
    ├── templates/            # HTML 模板
    └── static/               # 静态文件
```

## 技术栈

- **框架**: Django 6.1.1
- **数据库**: MySQL 5.7+
- **Python**: 3.x

## 数据模型

### UserInfo（用户信息）
| 字段 | 类型 | 说明 |
|------|------|------|
| name | CharField | 用户名 |
| password | CharField | 密码 |
| age | IntegerField | 年龄 |

### Department（部门）
| 字段 | 类型 | 说明 |
|------|------|------|
| title | CharField | 部门名称 |

## 功能列表

| 路由 | 功能 | 说明 |
|------|------|------|
| `/index/` | 首页 | 欢迎页面 |
| `/user/list/` | 用户列表 | 显示用户列表页面 |
| `/user/add/` | 添加用户 | 用户添加页面 |
| `/tpl/` | 模板示例 | Django 模板语法演示 |
| `/weather/` | 天气查询 | 调用 Open-Meteo API 获取天气数据 |
| `/something/` | 请求演示 | 处理 GET/POST 请求示例 |
| `/login/` | 登录 | 用户登录功能（用户名: root，密码: 123） |
| `/orm/` | ORM 操作 | 数据库增删改查演示 |
| `/info/list/` | 信息列表 | 用户信息列表（支持增删改查） |
| `/info/add/` | 添加信息 | 添加用户信息 |
| `/info/delete/` | 删除信息 | 删除指定用户 |

## 快速开始

### 1. 安装依赖

```bash
pip install django
pip install mysqlclient
```

### 2. 配置数据库

确保 MySQL 中已创建 `mysite3` 数据库：

```sql
CREATE DATABASE mysite3 CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

如需修改数据库配置，编辑 `mysite/settings.py` 中的 DATABASES 配置。

### 3. 数据库迁移

```bash
python manage.py makemigrations
python manage.py migrate
```

### 4. 启动服务器

```bash
python manage.py runserver
```

访问 `http://127.0.0.1:8000/`

## 注意事项

- DEBUG 模式已开启，请勿在生产环境使用
- 数据库密码等敏感信息存储在 `settings.py` 中，建议使用环境变量或配置文件管理
- 部分功能（如 ORM 操作页面）会直接操作数据库，执行后数据会被修改
