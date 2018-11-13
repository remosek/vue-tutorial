# Vue-torial

## Setup
### Vue CLI v3
```
yarn global add @vue/cli
// OR
npm install @vue/cli -g
```
### Vue Component Generator (vgc)
```
yarn global add vue-generate-component
// OR
npm install vue-generate-component -g
```

## Building an App
### Create project
```
vue create my-app
```

You will be present with setup options `default` and `Manually select features` (if this is your first setup select `Manually select features`)

From the list of options you will require 
* `Babel`, 
* `Router`, 
* `Vuex`,
* `Css Pre-processors` 
* `Linter`

You can optionally include `Progressive Web App (PWA) Support`.

```
? Please pick a preset: Manually select features
? Check the features needed for your project: Babel, Router, Vuex, CSS Pre-processors, Linter
? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS
? Pick a linter / formatter config: Basic
? Pick additional lint features: Lint on save
? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? In dedicated config files
? Save this as a preset for future projects? Yes
```

You will finally be asked `Save this as a preset for future projects?` I'd recommend `Y` to save having to go through the manual setup every project.

You might get asked if you want to use `yarn` or `npm` this is entriely your personal preference, I recommend `yarn` as it is much faster at running installs.

Let it install and that's you're basic Vue app setup. To make things easier it is highly recommended to install `vuetify` as long as the project designs follow `Material Design` patternsll

### Run app
```
cd my-app
yarn serve
// OR
npm run serve
```

## Plugins

### Install Vuetify
Vuetify will provide a huge number of components straight out of the box 

```
vue add vuetify
```

Select `Configure (advanced)` form the setup options

```
? Choose a preset: Configure (advanced)
? Use a pre-made template? (will replace App.vue and HelloWorld.vue) Yes
? Use custom theme? Yes
? Use custom properties (CSS variables)? Yes
? Select icon font Font Awesome 5
? Use fonts as a dependency (for Electron or offline)? No
? Use a-la-carte components? Yes
? Select locale English
```

Commit the changes

### Install Cordova (optional)
```
vue add cordova
```

// TODO

## Views
Views are basically Components just used as the Router access point

Standard View naming convention is Pascal Case `MyPage`

### Create a View
```
cd ./src/views
vgc MyPage
```

## Router
```
import MyPage from '@/views/MyPage;

export default [
    {
        path: '/my-page',
        name: 'myPage',
        component: MyPage,
        meta: {
            title: 'My Page',
        },
    },
];
```

## Components
Standard component name is Pascal Case `MyComponent`

### Create a component
```
cd ./src/components
vgc MyComponent
```

### Using Components
```
// MyPage.js
import MyComponent from '@/components/MyComponent';

components: {
    MyComponent
}

// MyPage.html
<my-component></my-component>
```
Or you can specify the component name
```
// MyPage.js
import MyNewComponent from '@/components/MyComponent';

components: {
    MyNewComponent
}

// MyPage.html
<my-new-component></my-new-component>
```

### Variables
#### Data
```
// MyPage.js
data() {
    return {
        customVaraible: '',
    };
},
methods: {
    doSomething() {
        this.customVariable;
    }
}

// MyPage.html
<div>
    {{ customVariable }}
</div>
```

#### Props
```
// MyComponent.js
props: {
    customProperty: {
        type: String, // or Object or Array
        default: '' // or an Object with () => ({}) or an Array with () => ([])
    }
},
methods: {
    doSomethingElse() {
        this.customProperty;
    }
}

// MyComponent.html
<div>
    {{ customProperty }}
</div>

//MyPage.html
<my-component customProperty="static-value">
// OR
<my-component :customProperty="customVariable">
```

### Events
```
// MyComponent.js
methods: {
    buttonClicked() {
        console.log('Button Clicked');
    }
}

// MyComponent.html
<v-btn @click="buttonClicked">Click </v-btn>
```

## Commands

### Project setup
```
yarn install
```

#### Compiles and hot-reloads for development
```
yarn run serve
```

#### Compiles and minifies for production
```
yarn run build
```

#### Run your tests
```
yarn run test
```

#### Lints and fixes files
```
yarn run lint
```

#### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
# vue-tutorial
