	Visão Geral do Sistema de Recomendações de Livros



 O Sistema de Recomendações de Livros

Contexto do Sistema:
 A digitalização crescente do mercado editorial e o aumento do interesse pelas plataformas de leitura digital contribuíram para a demanda por sistemas de recomendação que ajudaram os leitores a descobrirem novos rumos de acordo com suas preferências. Este sistema, com uma infraestrutura robusta e focada na experiência do usuário, visa atender essa demanda, oferecendo recomendações que ajudam o usuário a encontrar livros que correspondam ao seu gosto e, ao mesmo tempo, contribuem para uma experiência de leitura mais rica e personalizada.

Módulos do Sistema:
Interface do Usuário (Web ou Mobile) A interface será a principal via de interação com o sistema, podendo ser acessada por um site ou aplicativo mobile. Uma interface permitirá que o usuário navegue pelos livros, acesse as recomendações e visualize as categorias de livros.

Módulo de Autenticação
 Responsável por garantir a segurança e o controle de acesso, permitindo que cada usuário tenha uma conta pessoal para registrador ocasional, histórico de leitura e outras informações pessoais. Este módulo incluirá o cadastro de novos usuários e o login seguro.
 


Requisitos do Sistema de Recomendações de Livros
Cadastro de Usuários:
•	O sistema deve permitir que novos usuários se registrem com informações básicas, como nome, e-mail e senha, para criação de um perfil.
•	O sistema deve validar os dados de cadastro para garantir a integridade e segurança das informações

Autenticação e Login Seguro:

•	O sistema deve permitir que os usuários façam login utilizando suas credenciais, com verificação de ocorrências pessoais para proteger o acesso aos dados
 
Casos de uso:

Cadastro de Usuário – O usuário se cadastra no sistema para acessar as funcionalidades. 

Autenticação de Usuário – O usuário faz login para acessar uma plataforma. 

Listagem de Livros – O usuário visualiza a lista de livros disponíveis no sistema, filtrando por categorias. 

Recomendação Personalizada – O sistema sugere livros ao usuário com base no histórico de leitura e preferências. 

Gerenciamento de Histórico – O sistema registra o histórico de leitura do usuário, usado para recomendações futuras
 
Diagrama de caso de uso:

 
 
Nome de caso de uso	Receber Recomendações de Livros
Ator Principal	Usuário Leitor
Objetivo	Receber uma lista de livros recomendados
Pré-condições	Usuário autenticado e com perfil de leitura
Fluxo Principal	1. Usuário acessa a página de recomendações
2. Sistema consulta API de IA para recomendações
3. Recomendações são exibidas ao usuário com base no perfil
Fluxo Alternativo	2a. Usuário sem histórico de leitura; sistema sugere livros populares ou por categoria
Pós-condição	Lista de recomendações é apresentada ao usuário
Cenário de Caso de Uso



Este é um diagrama de pacotes que representa a estrutura de um sistema para um sistema de recomendações de livros. Nesse diagrama, são representadas as classes ou módulos e suas relações. Cada classe contém métodos ou funcionalidades que são as ações que o sistema executa.



 



Explicação das classes e dos relacionamentos:

 InterfaceUsuario: 
Camada que entra em contato com o usuário final, ou seja, o que o usuário vê e interage no sistema. 
Métodos: 
TelaLogin: exibe a tela de login para o usuário se autenticar 
TelaRecomendações: Exibe a tela com os livros recomendados calculados de acordo com o cálculo de similaridade que tal usuário vê ao abrir o sistema.  TelaPesquisaLivros() : exibe a tela onde o usuário pode procurar livros disponíveis no sistema


ModuloAutenticacao :
Este módulo é responsável por gerenciar a autenticação dos usuários, ou seja, ele deve verificar se o usuário está registrado no sistema e tem permissões para usar suas funcionalidades.
Métodos: 
RealizarCadastro (): Permitir que o usuário crie um novo cadastro no sistema. FazerLogin (): Deve permitir que o usuário faça login no sistema usando suas credenciais. AutenticarUsuario : Verificar se as credenciais de login do usuário são válidas e autenticá-lo.
Relacionamento: este módulo é referência ao BancoDeDados para armazenar e verificar os detalhes dos usuários.
 

ModuloRecomendacoes:
Gera recomendacoes de livros para o usuário com base em seu histórico ou preferências de leitura.
Metodos:
GerarRecomendacoes(): Gera uma lista de livros e retorna para o usuário.
ConsultarAPIdeIA(): Faz uma chamada na API de uma inteligência artificial externa ou lógica interna para gerar as recomendações com base no perfil do usuário.
Relacionamento: Depende do BancoDeDados para consultar as informações do usuário para o sistema verificar os dados dos usuários.SQLException
 
BancoDeDados:
Representa um banco de dados que armazena todas as informações sobre usuários, livros, comentários, favoritos e histórico de leitura.
método:

ArmazenarUsuarios(): Armazena dados do usuário (como informações pessoais, histórico de leitura, etc.).
ArmazenarLivros(): Armazena os dados dos livros no sistema.
RegistrarAvaliacao(): Registra as avaliações feitas pelos usuários sobre os livros.
Relacionamento: O BancoDeDados se comunica com todos os outros módulos, pois é onde os dados são armazenados e acessados.
