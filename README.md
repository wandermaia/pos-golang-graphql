# pos-golang-graphql

Inicializando o módulo

```bash

go mod init github.com/wandermaia/pos-golang-graphql

```

## Servidor GraphQL

O site gqlgen disponibiliza alguns passos para gerar um servidor:


```bash

printf '// +build tools\npackage tools\nimport (_ "github.com/99designs/gqlgen"\n _ "github.com/99designs/gqlgen/graphql/introspection")' | gofmt > tools.go

go mod tidy



wander@bsnote283:~$ go run github.com/99designs/gqlgen init
Creating gqlgen.yml
Creating graph/schema.graphqls
Creating server.go
Generating...

Exec "go run ./server.go" to start GraphQL server
wander@bsnote283:~$ 

go mod tidy


```

## GraphQL

Os inputs nos ajudam a fazer a entrada de dados.

Mutation é quando você vai fazer alterações no modelo.

Utilizando o comando gqlgen com a opção generate, ele vai gerar as estruturas conforme o eschema criado:

go run github.com/99designs/gqlgen generate


Querys para playground:


```sql

mutation createCategory{
  createCategory(input: {name: "Tecnologia2", description: "Cursos de Tecnologia2"}){
    id
    name
    description
  }
}

mutation createCourse{
  createCourse(input: {name: "FullCycle", description: "The Best!", categoryId: "a4577a62-8041-4401-ac8f-49174d7d1c90"}){
    id
    name
  }
}

query queryCategories{
  categories{
    id
    name
    description
  }
}

query queryCourses{
  courses{
    name
    id
  }
}

```

## Nested Information



## Dicas

Instale a extensão "GraphQL: Language Feature Support" do VSCode.


## Referências

gqlgen

https://gqlgen.com/