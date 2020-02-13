<template>
  <div class="container">
    <codemirror v-model="code" 
                  :options="cmOption"
                  @cursorActivity="onCmCursorActivity"
                  @ready="onCmReady"
                  @focus="onCmFocus"
                  @blur="onCmBlur">
      </codemirror>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      code: `<table>
  <tr>
    <td class="as">asas</td>
  </tr>
</table>`,
      cmOption: {
        tabSize: 4,
        styleActiveLine: true,
        lineNumbers: true,
        line: true,
        foldGutter: true,
        styleSelectedText: true,
        mode: 'text/html',
        keyMap: "default",
        matchBrackets: true,
        showCursorWhenSelecting: true,
        theme: 'material-palenight',
        extraKeys: { "Ctrl": "autocomplete" },
        hintOptions:{
          completeSingle: true
        }
      }
    }
  },
  components: {
  },
  methods: {
    onCmCursorActivity(codemirror) {
      console.log('onCmCursorActivity', codemirror)
    },
    onCmReady(codemirror) {
      console.log('onCmReady', codemirror)
    },
    onCmFocus(codemirror) {
      console.log('onCmFocus', codemirror)
    },
    onCmBlur(codemirror) {
      console.log('onCmBlur', codemirror)
    }
  }
}
</script>

<style>

</style>
