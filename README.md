### termui
---
https://github.com/gizak/termui


```go
package main

import (
  "log"
  
  ui "github.com/gizak/termui"
  "github.com/gizak/termui/widgets"
)

func main() {
  if err := ui.Init(); err != nil {
    log.Fatalf("failed to initialize termui: %v", err)
  }
  defer ui.Close()
  
  p := widgets.NewParagraph()
  p.Text = "Hello"
  p.SetRect(0, 0, 25, 5)
  
  ui.Render(p)
  
  for e := range ui.PollEvents() {
    if e.Type == ui.KeyboardEvent {
      break
    }
  }
}
```

```
go get -u github.com/gizak/termui@master
```

```
```



