FROM golang:1.16-alpine AS builder

WORKDIR /app
COPY . .

RUN go build fullcycle.go
RUN go clean -cache

FROM scratch
COPY --from=builder /app/fullcycle /
USER 1000
CMD ["./fullcycle"]