# go-stream
[![GoDoc](https://godoc.org/github.com/r-evolve/go-stream?status.svg)](https://godoc.org/github.com/r-evolve/go-stream)
[![Go](https://github.com/r-evolve/go-stream/actions/workflows/go.yml/badge.svg)](https://github.com/r-evolve/go-stream/actions/workflows/go.yml)

## Summary
go-stream is a Go library for working with streamed data.
It is inspired by the Java 8 Stream API.

## Installation
```bash
go get github.com/r-evolve/go-stream
```

## Usage

```go
package main

import (
    "fmt"
    "github.com/r-evolve/go-stream"
)

func main() {
    // Create a stream from a slice
    stream := go_stream.New([]int{1, 2, 3, 4, 5})

    // Filter the stream
    stream = stream.Filter(func(i int) bool {
        return i > 2
    })

    // Map the stream
    stream = stream.Map(func(i int) int {
        return i * 2
    })

    // Reduce the stream
    sum := stream.Reduce(func(a, b int) int {
        return a + b
    }, 0)

    // Print the result
    fmt.Println(sum)
}
```

## Usage alternative

```go
package main

import (
    "fmt"
    "github.com/r-evolve/go-stream"
)

func main() { 
    // Create a stream from a slice
    stream := go_stream.New([]int{1, 2, 3, 4, 5})

    // Print the result
    fmt.Println(stream.Filter(func(i int) bool {
        return i > 2
    }).Map(func(i int) int {
        return i * 2
    }).Reduce(func(a, b int) int {
        return a + b
    }, 0))
}
```

## Other examples

```go
package main

import (
    "fmt"
    "github.com/r-evolve/go-stream"
)

func main() {
    // Create channels from single values
    _ = go_stream.Of(1, 2, 3, 4, 5).ToChannel()
}

```

## Documentation
[![GoDoc](https://godoc.org/github.com/r-evolve/go-stream?status.svg)](https://godoc.org/github.com/r-evolve/go-stream)