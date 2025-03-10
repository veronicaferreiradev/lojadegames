# 🎮 Loja de Games

## 📖 Descrição

API RESTful de uma Loja de Games, desenvolvida em Java com Spring Boot.  
Permite o gerenciamento de **produtos (jogos)** e **categorias**, com funcionalidades de **CRUD completo** e relacionamento entre tabelas.

---

## ⚙️ Tecnologias Utilizadas

- Java 17
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Hibernate
- MySQL
- Jakarta Validation (Validação de dados)
- Postman/Insomnia (para testes de API)

---

## 🔗 Endpoints da API

### 🎮 Produtos (`/produtos`)

| Método  | Caminho                         | Descrição                         |
|--------|----------------------------------|-----------------------------------|
| GET    | `/produtos`                      | Lista todos os produtos            |
| GET    | `/produtos/{id}`                 | Busca produto por ID               |
| GET    | `/produtos/nome/{nome}`          | Busca produto pelo nome            |
| POST   | `/produtos`                     | Cadastra um novo produto            |
| PUT    | `/produtos`                     | Atualiza um produto                 |
| DELETE | `/produtos/{id}`                | Deleta um produto                   |

---

### 📂 Categorias (`/categorias`)

| Método  | Caminho                                   | Descrição                             |
|--------|--------------------------------------------|---------------------------------------|
| GET    | `/categorias`                              | Lista todas as categorias              |
| GET    | `/categorias/{id}`                         | Busca categoria por ID                 |
| GET    | `/categorias/categoria/{nomecategoria}`    | Busca categoria pelo nome              |
| POST   | `/categorias`                              | Cadastra uma nova categoria            |
| PUT    | `/categorias`                              | Atualiza uma categoria                 |
| DELETE | `/categorias/{id}`                         | Deleta uma categoria                   |

---

## 🗄️ Diagrama de Classes (Mermaid UML)

```mermaid
classDiagram
    class Produto {
        +Long id
        +String nome
        +String descricao
        +float preco
        +Categoria categoria
    }

    class Categoria {
        +Long id
        +String nomecategoria
        +List~Produto~ produto
    }

    Produto "N" -- "1" Categoria : pertence a
