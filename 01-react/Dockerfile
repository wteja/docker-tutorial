FROM node:alpine as build
WORKDIR /app
COPY myapp/package*.json .
RUN npm install
COPY myapp/src ./src
COPY myapp/public ./public
RUN npm run build

FROM nginx:stable-alpine
COPY --from=build /app/build /usr/share/nginx/html