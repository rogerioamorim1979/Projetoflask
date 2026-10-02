# Projeto Flask

Aplicação web didática desenvolvida com Flask. O projeto reúne exemplos de rotas, templates Jinja, formulários, mensagens flash e validação simples de login. Os arquivos `appFlask_v1.py` a `appFlask_v8.py` representam versões da evolução dos exercícios; a versão mais completa é `appFlask_v8.py`.

## Requisitos

- Python 3.9 ou superior
- Flask

## Instalação e execução

No terminal, a partir da pasta do projeto, crie e ative um ambiente virtual (opcional, mas recomendado) e instale o Flask:

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
py -m pip install Flask
```

Se a política do PowerShell bloquear a ativação do ambiente virtual, consulte a documentação do Python para ativá-lo pelo terminal disponível no seu sistema. Também é possível instalar o Flask sem ambiente virtual.

Inicie a aplicação:

```powershell
py appFlask_v8.py
```

Acesse [http://127.0.0.1:8000](http://127.0.0.1:8000). Para interromper o servidor, pressione `Ctrl+C` no terminal.

## Funcionalidades e rotas

| Rota | Descrição |
| --- | --- |
| `/` e `/index` | Página inicial |
| `/contato` | Página de contato |
| `/usuario` | Exibe o perfil com valores padrão |
| `/usuario/<nome_usuario>;<nome_profissao>` | Exibe o perfil com nome e profissão informados na URL |
| `/login` | Formulário de login e acesso ao formulário de cadastro |
| `/autenticar` | Recebe o formulário por `GET` ou `POST` e verifica as credenciais de demonstração |
| `/novocadastro/` | Exibe a página de cadastro com o nome informado no formulário |

O login é validado contra um dicionário definido no próprio código. As credenciais de demonstração estão na variável `tabelaUsuarios`, em `appFlask_v8.py`.

## Estrutura

```text
.
├── appFlask_v1.py ... appFlask_v8.py  # versões dos exercícios
├── importando.py                      # exemplo de importação
├── static/
│   ├── css/                            # folhas de estilo
│   └── js/                             # scripts do navegador
├── t_templates/                       # templates usados pela versão 8
└── templates/                         # templates de versões anteriores
```

## Observações

- A versão 8 usa a pasta `t_templates` e executa o servidor de desenvolvimento na porta `8000`.
- O cadastro atual apenas apresenta uma página com o nome enviado; não cria nem armazena uma conta.
- Os usuários e senhas ficam em texto simples no código e são mantidos somente em memória. Este exemplo é voltado a estudo e não deve ser usado como sistema de autenticação em produção.
- A chave secreta do Flask também está definida diretamente no código. Em uma aplicação real, configure-a por variável de ambiente e use armazenamento seguro de senhas.