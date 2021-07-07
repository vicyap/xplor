FROM rust:1.53.0 as builder
WORKDIR /usr/src/app
COPY . .
RUN cargo build --release
RUN cargo install --path .

FROM debian:buster-slim
# RUN apt-get update && apt-get install -y extra-runtime-dependencies && rm -rf /var/lib/apt/lists/*
COPY --from=builder /usr/local/cargo/bin/xplor /usr/local/bin/xplor
CMD ["xplor"]
