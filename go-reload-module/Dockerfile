# ALPINE SERVER
FROM alpine:latest
RUN apk update && apk upgrade
RUN apk --no-cache add gcc g++ make
RUN apk add go
RUN apk add nano
RUN apk add curl
RUN go install github.com/pilu/fresh@latest


# GOLANG
WORKDIR /go
COPY .env . 
COPY go.mod .
COPY go.sum .
COPY *.go .
RUN go mod download  && go mod verify

CMD ["fresh"]

EXPOSE 8080




