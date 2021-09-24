## 使用 TS

安装

```sh
yarn global add typescript
```

创建 `hello-world.ts` 文件

```ts
const message: string = 'helloWorld'

console.log('message')
console.log(message)
```

运行

```sh
tsc src/hello-world.ts
# 或者 tsc src/*
```

> 会自动编译一个 `hellow-world.js` 文件

## 在 Node 中使用 TS

安装 `ts-node-dev`

```sh
yarn global add ts-node-dev
```

再次运行

```sh
ts-node-dev src/hello-world.ts
```

## 使用 VSCode 运行 TS

> 如果克隆了当前项目，只需要 `yarn install` 即可

初始化项目

```sh
mkdir typescript-demo
cd typescript-demo
yarn init -y
```

安装依赖

```sh
yarn add -D ts-node typescript @types/node
```

添加 VSCode 配置文件 `.vscode/launch.json`

```js
{
  // 使用 IntelliSense 了解相关属性。 
  // 悬停以查看现有属性的描述。
  // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "ts-node",
      "type": "node",
      "request": "launch",
      "program": "${workspaceRoot}/node_modules/ts-node/dist/bin.js",
      "args": ["${relativeFile}"],
      "cwd": "${workspaceRoot}",
      "protocol": "inspector",
      "resolveSourceMapLocations": [
        "${workspaceFolder}/**",
        "!**/node_modules/**"
      ]
    }
  ],
}
```

打开 VSCode 的运行和调试，选择 ts-node 点击绿色小三角运行（运行时必须打开当前要运行的 TS 文件）


