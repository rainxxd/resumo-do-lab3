# Laboratório: Configuração de Instância de Banco de Dados no Microsoft Azure

## 🎯 Objetivo

Praticar a configuração de uma instância de Banco de Dados na plataforma
Microsoft Azure e consolidar o aprendizado em um repositório de estudo.

------------------------------------------------------------------------

## 📝 Passo a Passo da Configuração

### 1. Acessar o Portal do Azure

-   Entrar no [Portal do Azure](https://portal.azure.com/).

### 2. Criar um Recurso de Banco de Dados

-   No menu lateral, clicar em **Criar um recurso** \> **Banco de
    Dados**.
-   Selecionar **Banco de Dados SQL**.

### 3. Configuração Básica

-   **Assinatura**: selecionar sua assinatura.
-   **Grupo de Recursos**: criar ou escolher um existente (ex:
    `lab-db-grupo`).
-   **Nome do Banco**: definir o nome (ex: `labdbazure`).
-   **Servidor**: criar um novo servidor com:
    -   Nome (ex: `server-lab-azure`).
    -   Usuário administrador e senha.
    -   Região mais próxima para menor latência.

### 4. Configurações de Rede

-   Permitir acesso a serviços do Azure.
-   Configurar **firewall** para permitir IPs confiáveis (ex: seu IP
    local).

### 5. Revisar e Criar

-   Revisar as configurações.
-   Clicar em **Criar** e aguardar a implantação.

------------------------------------------------------------------------

## 🔑 Conectando ao Banco

Após a criação: 1. Copiar a **string de conexão** no portal do Azure. 2.
Utilizar em ferramentas como: - **Azure Data Studio** - **SQL Server
Management Studio (SSMS)** - Aplicações em **C#, Java, Python,
Node.js**, etc.

Exemplo (C# com ADO.NET):

``` csharp
using System.Data.SqlClient;

string connectionString = "Server=tcp:server-lab-azure.database.windows.net,1433;Initial Catalog=labdbazure;Persist Security Info=False;User ID=usuario;Password=senha;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;";

using (SqlConnection conn = new SqlConnection(connectionString))
{
    conn.Open();
    Console.WriteLine("Conexão estabelecida com sucesso!");
}
```

------------------------------------------------------------------------

## 📚 Resumos Importantes

-   **CapEx x OpEx**: no Azure paga-se pelo uso (OpEx), evitando grandes
    investimentos iniciais (CapEx).
-   **Modelos de Nuvem**: Pública, Privada e Híbrida.
-   **Modelo de Consumo**: paga-se apenas pelo que utilizar.

------------------------------------------------------------------------

## 💡 Dicas e Boas Práticas

-   Sempre configure **firewalls e regras de acesso** de forma
    restritiva.
-   Utilize **autenticação multifator** para proteger acessos
    administrativos.
-   Ative **backup automático** e configure **alertas de
    monitoramento**.
-   Avalie o uso do **Azure Cost Management** para otimizar gastos.
