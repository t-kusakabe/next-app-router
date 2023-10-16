##########################
## Builder Container
##########################
FROM node:20.8.0-alpine3.18 as builder

WORKDIR /next-app-router

COPY package.json package-lock.json ./

RUN npm i --no-progress

COPY . .

RUN npm run build

##########################
## Application Container
##########################
FROM node:20.8.0-alpine3.18

WORKDIR /next-app-router

COPY --from=builder /next-app-router ./

CMD ["npm", "run", "start"]
