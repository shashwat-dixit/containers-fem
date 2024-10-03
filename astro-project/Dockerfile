# build stage
FROM node:20 AS node-builder
WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build

# runtime stage
FROM nginx:alpine
COPY --from=node-builder /app/dist /usr/share/nginx/html