postgres:
	docker run --name mypostgres -p 5432:5432 -e POSTGRES_PASSWORD=secret -e POSTGRES_USER=root -d postgres

createdb:
	docker exec -it mypostgres createdb --username=root --owner=root bank-go

dropdb:
	docker exec -it mypostgres dropdb bank-go

migrateup:
	migrate -path db/migration -database "postgresql://root:secret@localhost:5432/bank-go?sslmode=disable" -verbose up

migratedown:
	migrate -path db/migration -database "postgresql://root:secret@localhost:5432/bank-go?sslmode=disable" -verbose down

.PHONY: postgres createdb dropdb migrateup migratedown