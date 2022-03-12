# curso-webpack-react

### Inicializar el proyecto:
```npm
npm init || npm init -y 
```

### Instalando las dependencias para React: 
```npm 
npm i react react-dom -S
```

### Babel
```npm
npm i @babel/core @babel/preset-env @babel/preset-react babel-loader -D
```

### Webpack
```npm
npm i webpack webpack-cli webpack-dev-server -D
```

## Configuracion de plugins y loaders para React

Diferencia entre un plugin y un loader
Es importante saber la diferencia entre un plugin y un loader, ya que estos no son sinónimos. El plugin es código que es capaz de modificar la compilación, como en el caso de Babel, el cual transpila el código, modificando la compilación.
.
Por otro lado, el loader funciona antes de que se haga la compilación, por lo que no afecta a esta. Sabiendo eso, el plugin es mucho mas difícil de manejar que el loader (en relacion a darle mantenimiento y esas cosas).

### HtmlWebpackPlugin
Es un plugin para inyectar javascript, css, favicons, y nos facilita la tarea de enlazar los bundles a nuestro template HTML.

```npm
npm i html-loader html-webpack-plugin -D
```

## Configuración de Webpack para Css en React

```npm 
npm i mini-css-extract-plugin css-loader style-loader sass sass-loader -D
```

**configurando la regla para mini-css-extract-plugin:**

```js
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
...
module: {
	rules: [
        ...
        {
		  test: /\.(css|scss)$/,
		  use:[
              MiniCssExtractPlugin.loader, 'css-loader', 'sass-loader' /*'style-loader'*/
              ],
		},
        ...
		],
	},
	plugins: [
		...
		new MiniCssExtractPlugin({
			filename: '[name].css',
		}),
	],
};
```


