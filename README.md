# 才华横溢 案例教学 3

## 第一步：构建 recipe_box 的专案项目

```
mkdir workspace
cd workspace
rails new recipe_box
cd recipe_box
git init
git add .
git commit -m "initial commit"
```
## 第二步：查看 recipe_box 的专案项目

```
rails s
atom .
```
![image](https://ws3.sinaimg.cn/large/006tNc79gy1fpc3frx4n4j31kw0x51kx.jpg)
![image](https://ws3.sinaimg.cn/large/006tNc79gy1fpc35p7vdvj31kw0zjtf6.jpg)

## 第三步：构建一个 haml 分支(https://rubygems.org/)
```
git checkout -b haml

Gemfile:
gem 'haml', '~> 5.0', '>= 5.0.4'

bundle install
rails s

rails g controller recipe

config/routes.rb
resources :recipes
root "recipe#index"
rails s
```
### app/controllers/recipe_controller.rb
```
  def index
end
```

### app/views/recipe/index.html.haml
```
%h1 欢迎来到才华横溢职业技能大学
```

![image](https://ws1.sinaimg.cn/large/006tNc79gy1fpc4ekqgx6j311s0gm75q.jpg)

第四步：构建一个 分支
git checkout -b recipe_controller
### app/controllers/recipe_controller.rb
```
before_action :find_recipe, only: [:show,:edit,:update,:destroy]

    def index
    end

    def show
    end

    def new
      @recipe = Recipe.new
    end

    def create
      @recipe = Recipe.new(recipe_params)
    end

    private

    def recipe_params
      params.require(:recipe).permit(:title,:description)
    end

    def find_recipe
      @recipe = Recipe.find(params[:id])
    end
end
```

>rails g model Recipe title:string description:text user_id:integer
>rake db:migrate

```
Gemfile:(https://rubygems.org/)
gem 'simple_form', '~> 3.5', '>= 3.5.1'
bundle install
rails s
rake routes
深入路由（routes）
```

https://rails-practice.com/content/Chapter_2/2.3.html
