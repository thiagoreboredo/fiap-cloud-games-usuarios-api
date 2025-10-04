# Microsserviço de Usuários - FIAP Cloud Games 🚀

Este repositório contém o código-fonte do **Microsserviço de Usuários**, parte da arquitetura do projeto FIAP Cloud Games da Pós-Graduação em Arquitetura de Sistemas .NET com Azure.

Este serviço é totalmente independente e responsável por gerenciar todas as operações relacionadas a usuários, incluindo cadastro, autenticação via JWT e reativação de contas.

---

### 🎯 Responsabilidades do Serviço

-   **Cadastro de Novos Usuários**: Persiste novos usuários (perfis "Usuário" ou "Administrador") em um banco de dados PostgreSQL dedicado.
-   **Validação de Dados**: Garante que o e-mail tenha um formato válido e que a senha seja segura (mínimo de 8 caracteres, com letras, números e caracteres especiais).
-   **Autenticação**: Gera tokens JWT para usuários válidos e ativos.
-   **Autorização**: Fornece as `claims` de `Role` (perfil) no token JWT para controle de acesso em outros serviços.
-   **Gerenciamento de Contas**: Permite que administradores reativem contas de usuários.

---

### 🛠️ Tecnologias Utilizadas

-   **.NET 8**: Plataforma de desenvolvimento.
-   **ASP.NET Core (Minimal API)**: Framework para construção da API.
-   **Entity Framework Core**: ORM para acesso a dados.
-   **PostgreSQL**: Banco de dados relacional.
-   **JWT (JSON Web Tokens)**: Para autenticação e autorização.
-   **xUnit**: Framework para testes de unidade.
-   **Docker**: Para conteinerização da aplicação.
-   **New Relic**: Para monitoramento e observabilidade (APM).

---

### 📂 Estrutura do Projeto

-   **Domain**: Contém a entidade `Pessoa` e as regras de negócio centrais.
-   **Application**: Orquestra os casos de uso (Services e DTOs).
-   **Infrastructure**: Implementa a persistência de dados com EF Core e o `DbContext`.
-   **Usuarios.API**: Expõe os endpoints RESTful (`/pessoa`).
-   **FIAP-Cloud-GamesTest**: Contém os testes de unidade para o serviço.

---

### ▶️ Como Executar

1.  **Pré-requisitos**: .NET 8 SDK e Docker.
2.  **Configuração**: Ajuste a `ConnectionString` no arquivo `appsettings.Development.json` para apontar para o seu banco de dados PostgreSQL.
3.  **Execução**: Rode o projeto `Usuarios.API` a partir da sua IDE ou via linha de comando com `dotnet run`.