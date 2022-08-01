# ✅ Concluído : Desafio Técnico - ML Classificador
 Esse desafio consiste em desenvolver um modelo de aprendizado de máquina capaz de classificar as amostras do conjunto de dados.
## 📌  Orientações para executar o código :
    Caso tenha interesse em executar o código desenvolvido em seu computador, vale ressaltar que as ferramentas utilizadas estão 
    listada a seguir.
    
      🐍 Python : 3.10.2 64-bit
      🟠 Jupyter Notebook
      📚 Bibliotecas: Pandas, Numpy, Seaborn, Sklearn
      
     Após configurar o ambiente de desenvolvimento, não esqueça de fazer o download do arquivo 'dataset_cdjr.parquet.gzip', que 
     se encontra na página inicial desse repositório.

# Desenvolvimento do Projeto
   O primeiro passo foi importar a base de dados que seria utilizanda em todo o projeto.
   ![image](https://user-images.githubusercontent.com/89054626/182064898-bd3c56d9-3d4a-4b12-87bd-0e2a80f3e1df.png)

  ## 1- Análise exploratória dos dados:
         Nessa etapa foram feita as seguintes análises:
            - Levantamento das dimensões da base de dados.
            - Avaliação dos tipos das variáveis.
            - Busca de possiveis valores nulos.
            - Validação de linhas duplicadas
         Ao fim dessa análise partimos para a proxima etapa.
  
  ## 2- Preparação dos dados:
         A preparação dos dados seguiram a seguinte ordem:
            - Separação das features e da variável de referêcia, está se encontrava na ultima coluna.
            - Montagem das variáveis de treino e teste (X_train, X_test,y_train, y_test)
            - Análise e escolha do valor de K: 
            -  Foi desenvolvido um algoritmo onde o valor de K variou entre 1 ate 11 tendo como objetivo
                  encontrar o menor valor de erro possivél em um intervalo continuo, assim sendo, foi plotando 
                  um gráfico com o valores da saída e escolhido o numero 5 como o melhor valor para K.
 ![image](https://user-images.githubusercontent.com/89054626/182068998-4781698e-cb95-4983-bf51-d2e9a44cff4d.png)
 ![image](https://user-images.githubusercontent.com/89054626/182068932-ef6e4f88-0bfb-4181-9fe8-e68328ed201e.png)
                  
            - Em seguida foi feita a preparação das features que mais contribuiram para o valor de K:
  ![image](https://user-images.githubusercontent.com/89054626/182068566-cbf8981d-597a-48c0-b875-268575a603d7.png)
  ![image](https://user-images.githubusercontent.com/89054626/182068811-6063f056-e6bd-4eab-8eb4-5586c67087da.png)
        
            - Essas features serão utilizadas para desenvolver nosso modelo.              
                     
 ## 3- Modelagem
          Para construção do nosso modelo foram feitas as seguintes etapas:
             - As features que não foram apresentadas no gráfico anterior fora excluidas da base.
             - A ultima coluna foi removida da base e transformada em nossa labels.
             - Os valores da tabela feature, formada pelas feature restantes, foram normalizados.
          Estes valores normalizados foram separados em teste e treinamento, devido a base possuir um baixo numero 
          de valores, optou-se por fazer esssa separação manual. Onde das 466 linhas totais da tabela, foram separadas
          372 para para esse processso, as demais ficaram reservadas para o processo de previsão do modelo ja pronto.
          
 ![image](https://user-images.githubusercontent.com/89054626/182070110-4bc7eaf7-f094-4e5b-95be-f81126a0f550.png)
           
            - Destas 372 linhas, 80 % foram separadas para treino do modelo e 20% para teste do mesmo.
            - Os modelos utilizados foram:
                # LogisticRegression
                # SVC (C-Support Vector Classification)
                # Decision Tree
                # Naive baeys
            - Todos os modelos recebem os mesmo feature para realizar seus treinamentos e teste.
            - Todos passaram por uma avaliação de suas acurácidade e F1 Score.
 
 
 
  ## 4- Avaliação da performance do modelo
  
          No processo de avaliação de perfomance foram análisadas as seguintes informações:
              - Acurácidade
              - F1 Score
              - Comportamento do modelo na Matriz de confusão
              
          Os dois primeiros pontos podem ser visto na imagem abaixo:
   ![image](https://user-images.githubusercontent.com/89054626/182071343-7aeee902-7c36-4742-80de-86fad471d6b9.png)
          
          O modelo Naive baeys, foi o que apresentou o melhor valor de acurácidade, porém quando fazemos um comparativo do
          comportamento da Matriz de Confusão entre o Modelo Naive baeys e LogisticRegression, foi possivel observar um melhor
          desempenho do Modelo LogisticRegression.
          
          Nas Imagens abaixo, a primeira é referente a Matriz de Confusão do Modelo LogisticRegression, e a segunda imagem e do 
          Modelo Naive baeys.
          
   ![image](https://user-images.githubusercontent.com/89054626/182071876-a31c3535-df36-4a2a-a172-b96effbe6e7c.png)
   ![image](https://user-images.githubusercontent.com/89054626/182071992-06132b32-f15b-4f19-882a-0ea358e3cb29.png)
       
   
  ### Por isso o modelo adotado foi : Modelo LogisticRegression que apresentou uma acurácidade de 62%. 
  
  
  
  
