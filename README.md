# docker-gs-ping

A simple Go server/microservice example for [Docker's Go Language Guide](https://docs.docker.com/language/golang/).

Notable features:

* Includes a [multi-stage `Dockerfile`](https://github.com/olliefr/docker-gs-ping/blob/main/Dockerfile.multistage), which actually is a good example of how to build Go binaries _for production releases_.
* Has functional tests for application's business requirements with proper isolation between tests using [`ory/dockertest`](https://github.com/ory/dockertest).
* Has a CI pipeline using GitHub Actions to run functional tests in independent containers.
* Has a CD pipeline using GitHub Actions to publish to Docker Hub.

Planned:

* Building Go modules and Docker images with `goreleaser`

# Key Points for latest go release 1.19

* certain module not required for go-- run this command go mod tidy  to clean up the go.mod file and the go.sum file in the current directory. It removes any unused modules that are no longer needed by the code in the project.
* go test -v ./... cmd in WSL(ubuntu 20.0LTS) required gcc complier -- run these command 
                                   sudo apt update
                                   sudo apt install build-essential
                                   sudo apt-get install manpages-dev
                                   gcc --version

## Want _moar_?!

There is a more advanced example in [olliefr/docker-gs-ping-roach](https://github.com/olliefr/docker-gs-ping-roach) using [CockroachDB](https://github.com/cockroachdb/cockroach).

## Contributing

This was written for an _introduction_ section of the Docker tutorial and as such it favours brevity and pedagogical clarity over robustness. 

Thus, feedback is welcome, but please no nits or pedantry. Ain't nobody got time for that 🙃

## License

[Apache-2.0 License](LICENSE)
