# Go in a shot
A brief and fucking fast guide to introduce yourself in Go in a dirty way.

## Motivation
I have wrote this short guide to Go why a lot of people increasingly ask me to reclicle java developers in Go developers.

* [Go for Java Programmers](https://talks.golang.org/2015/go-for-java-programmers.slide#1)
* [Quick Go-lang for Java Developers](http://blog.christianposta.com/programming/quick-go-lang-for-java-developers/)
* [Java is the COBOL of my generation and Go is its successor](https://influxdb.com/blog/2014/04/30/java-is-the-cobol-of-my-generation-and-go-is-its-successor.html)

## Step 0 - Install Go in your system
This step varies for each OS (Linux, Windows, iOS) and platform (Intel/amd, ARM, ..). Look it here [Go, getting started](https://golang.org/doc/install)

## Step 1 - Understanding the Go context
Prepare your system to write Go code and manage your workspaces correctly. Look it here [How to Write Go Code](https://golang.org/doc/code.html)

## Step 2 - Ide configuration
If you are a true programmer, you'll use [Vi](https://blog.gopheracademy.com/vimgo-development-environment/), just kidding ;-) , on the other hand, if you are and hipster programmer, surely you'll prefer [IntelliJ + Go plugin](http://networkstatic.net/installing-golang-ide-support-intellij/). Another good option is [Sublime Text + GoSublime](http://www.wolfe.id.au/2015/03/05/using-sublime-text-for-go-development). In any case, to developing Go software, you only need a text editor and a console to build and execute your code.

## Step 3 - Facing to Go
Make the fucking [Go Tour](https://tour.golang.org/welcome), the whole tour.

## Step 4 - Internalise the Go core concepts
As my old geek friends said, RFM, or in other words, the [Efective Go](https://golang.org/doc/effective_go.html ). Take special attention to this issues:

  * runtime.GOMAXPROCS
  * New vs make
  * Type casting vs type assertion vs type switch
  * Zero values
  * Defer
  * Function with multiple return values
  * Interfaces and methods
  * Initialization
  * Slices vs arrays - [Go Slices: usage and internals](http://blog.golang.org/go-slices-usage-and-internals)
  * Channels vs buffered channels
  * Goroutines
  * Anonimous struct attributes (composition relation)
  * Errors
  
In addition to these concepts, there are other packages/entities/tools which are also important for concurrent processes synchronization:

  * [sync.Mutex](https://golang.org/pkg/sync/)
  * [sync.Once](https://golang.org/pkg/sync/)
  * [sync.WorkGroup](https://golang.org/pkg/sync/)
  * [encoding](https://golang.org/pkg/encoding/)
  * [encoding/json](https://golang.org/pkg/encoding/json/) -- [JSON and Go](http://blog.golang.org/json-and-go)
  * [net/http](https://golang.org/pkg/net/http/) -- [Writing Web Applications](https://golang.org/doc/articles/wiki)
  
## Step 5 - Dependencies management
To manage the dependencies use the [godep tool](https://github.com/tools/godep). Look it here [Go Dependencies via Godep](https://devcenter.heroku.com/articles/go-dependencies-via-godep). Basically, tu initialize **godep** in your project follow these steps:

* Go to your project root folder and do:
```sh
go get -u github.com/tools/godep
godep save -r ./...
```
* After that, each time you do a *go get mydependeny* to retrieve a new needed dependency, do *godep save -r ./..* from your project root folder.

## Step 6 - Conditional building - build tags
Go source code may be built conditionally, this is, for a same package, compile one source or another according to build tags. Look it here [How to use conditional compilation with the go build tool](http://dave.cheney.net/2013/10/12/how-to-use-conditional-compilation-with-the-go-build-tool).

## Step 7 - Conditional behavior (flags)
(Pending ...)

## Step 8 - Testing
To implement the unit test, we'll use the [*go test* tool](https://golang.org/cmd/go/#hdr-Test_packages). Go provides a basic [testing package](https://golang.org/pkg/testing), but it doesn't offers mocking nor assertion funcionalities. To dispose of them, use the [Testify framework](https://github.com/stretchr/testify). It provides *mock* functionality over interfaces and *assert* validations. 

## Step 9 - Benchmarking
(pending)

## Step 10 - Profiling
(pending)

## Step 11 - Application life cycle
Coding                                -> Testing              -> Profiling    ->  Integrating               -> Deploying
go lint, go vet, go fmt, go build     -> go test -tags local  -> cpu,mem,lock ->  go test -tags integration -> go install

