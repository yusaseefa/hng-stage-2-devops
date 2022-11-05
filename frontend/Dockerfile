FROM node:17-alpine as builder
WORKDIR /app

COPY package.json .
COPY package-lock.json .
RUN npm ci
RUN npm i -g serve

COPY public/ public
COPY src/ src
EXPOSE 3000

RUN npm run build
CMD ["serve", "-s", "build"]
