# Instructions

## Docker installation

- Install docker
- Create a network
  - `docker network create docker-compose-network`
- Start postgres
  - `docker run --network docker-compose-network --name postgres -e POSTGRES_PASSWORD=mysecretpass -d -p 5432:5432 postgres`
- Build the image
  - `docker build --network=host -t docker-compose .`
- Start the image
  - `docker run -e DATABASE_URL=postgresql://postgres:mysecretpass@postgres:5432/postgres --network docker-compose-network  -p 3000:3000 docker-compose`
  
## Docker compose installation
