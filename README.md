# queue-worker

[![Build Status](https://img.shields.io/github/actions/workflow/status/user/queue-worker/ci.yml?branch=main)]()
[![Go Version](https://img.shields.io/badge/go-1.22+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

**queue-worker** persistent job queue with retries, dead-letter, and priority scheduling. Built with simplicity and performance in mind.

## Features

- Graceful Shutdown: Clean shutdown handling with configurable drain timeout
- High Performance: Optimized for low-latency, high-throughput workloads
- Minimal Allocations: Designed to minimize GC pressure in hot paths

## Installation

```bash
go get github.com/user/queue-worker@latest
```

## Quick Start

```go
package main

import (
	"fmt"
	"github.com/user/queue-worker"
)

func main() {
	client := queueworker.New(
		queueworker.WithTimeout(30 * time.Second),
	)

	result, err := client.Run(context.Background())
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(result)
}
```

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
