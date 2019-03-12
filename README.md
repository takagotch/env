### env
---
.go
https://github.com/codingconcepts/env

```go
type config struct {
  Address string `env:"ADDRESS" default:"0.0.0.0"`
}


package main

import (
  "fmt"
  "log"
  "time"
  
  "github.com/codingconcepts/env"
)

type awsConfig struct {
  Secret []byte `env:"SECRET" required:"true"`
  Region string `env:"REGION"`
  Port int `env:"PORT" required:"true"`
  Peers []string `env:"PEERS"`
  ConnectionTimeout time.Duration `env:"TIMEOUT"`
}

func main() {
  config := awsConfig{}
  if err := env.Set(&config); err != nil {
    log.Fatal(err)
  }
}
```

```sh
ID=1 SECRET=shh PORT=1234 PEERS=localhost:1235,localhost:1236 TIMEOUT=5s go run main.go

go get -u github.com/codingconcepts/env
```

```
```


