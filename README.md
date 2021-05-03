# Glista Gui
## Prerequisites

- If you need to install the workload but already have Visual Studio, go to Tools > Get Tools and Features..., which opens the Visual Studio Installer. Choose the Node.js development workload, then choose Modify.
- You must have the [Node.js](https://nodejs.org/en/download/) runtime installed. If you don't have it installed, we recommend you install the LTS version from the Node.js website for best compatibility with outside frameworks and libraries.
- Install Visual Studio Code.
- Open _Glista.Gui.code-workspace_ with Visual Studio Code and open terminal and follow instructions under _Project setup_.

## Project setup

```
npm install
```

## Fix severity vulnerability

```
npm audit fix
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## Run

- With Visual Studio start Api project,
- With Visual Studio Code open Gui project and with terminal start for developement.

## Style guid lines

- Vue.js https://vuejs.org/v2/style-guide
- Vuex: https://vuex.vuejs.org/guide/structure.html
- Primevue: https://www.creative-tim.com/learning-lab/bootstrap-vue/overview/argon-dashboard - documentation for most of components.

## Generate Typescript Axios client

To generate Typescript Axios client for models, api, configuration, base, etc. go to `Gui` directory and use command (for exmaple from localhost):
If you don't have openapi-generator installed, run this command first `npm install @openapitools/openapi-generator-cli@cli-4.3.1 -g`
`openapi-generator generate -i http://localhost:5000/swagger/v1/swagger.json -g typescript-axios -o api-axios -c api-config.json`. After recreating client, check if BASE_PATH in `base.ts` is still set to `process.env.VUE_APP_BASE_API_URL`.
Documentation for typescript-axios generator: https://openapi-generator.tech/docs/generators/typescript-axios/.
(There is possibility to get error sth. like this: �.ps1 is not digitally signed. The script will not execute on the system.�. Then you need to run this command: `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` and run generate command again)

## Formatting html code

- Go to File > Preferences > Settings. In top right corner click on icon that opens settings (JSON) and paste and save this:
  ```json
  "[vue]": {
    "editor.defaultFormatter": "octref.vetur"
  },
  "[javascript]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features"
  },
  "[json]": {
    "editor.defaultFormatter": "vscode.json-language-features"
  },
  "[typescript]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "typescript.updateImportsOnFileMove.enabled": "always",
  "[markdown]": {
    "editor.wordWrap": "on",
    "editor.quickSuggestions": false
  },
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.formatOnType": true,
  "editor.wordWrap": "on",
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "vetur.format.defaultFormatter.html": "js-beautify-html",
  "vetur.format.defaultFormatter.ts": "vscode-typescript",
  "vetur.format.defaultFormatterOptions": {
    "js-beautify-html": {
      "wrap_attributes": "auto"
    }
  },
  "vetur.experimental.templateInterpolationService": true,
  "editor.codeActionsOnSave": null
  ```