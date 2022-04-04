# Identificação_de_Documentos_do_Tipo_Certidão_de_Óbito_e_Nascimento_Através_de_um_Classificador_Baseado_em_Rede_Neural_Convolucional.

#### Aluno: Marcio Martins Rocha Ramos
#### Orientador: Leonardo Forero Mendoza

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código](https://github.com/marcio-7/Projeto_final_PUC_TCC/blob/main/Identificacao_documento_imagem_011021v1.ipynb).
---

### Resumo

Este trabalho corresponde a implementação de uma rede neural convolucional capaz de identificar dois tipos de documentos diferentes no formato de imagens. 

Foi utilizado o conceito de *Deep Learning*, ou seja, redes com diversas camadas também conhecidas como “redes profundas” e o conceito de *Transfer Learning*, ou seja, transferência de conhecimento, onde uma rede existente pré-treinada é utilizada para auxiliar na implementação.

Um dos objetivos é obter um protótipo inicial simples como uma prova de conceito. O ganho destes tipos de sistemas está na redução dos custos e tempo de processamento na análise de documentos através da automatização de processos geralmente realizados de forma manual. 


### Abstract 

This work corresponds to the implementation of a convolutional neural network capable of identifying two different types of documents in image format. The concept of Deep Learning was used, and the concept of Transfer Learning, that is, knowledge transfer, where an existing pre-trained network is used to assist in the implementation.

One of the goals is to get a simple initial prototype as a proof of concept. The gain of these types of systems lies in the reduction of costs and processing time in document analysis through the automation of processes usually performed manually.


### 1. Introdução

Em diversas empresas e instituições públicas existem processos operacionais que envolvem o processamento de diversos tipos de documentos de seus clientes. Muitas vezes a grande quantidade e diversidade destes documentos representam um grande desafio em relação ao recebimento, armazenagem, análise, separação por tipos e demais procedimentos.

As empresas de previdência privada, bancos, as instituições de previdência social como o INSS (Instituto Nacional de Serviço Social) e os regimes próprios de previdência social de estados e municípios, entre outros, são exemplos de instituições que processam uma enorme quantidade de documentos, principalmente nas primeiras etapas de atendimento ao cliente.

Um processo de concessão de pensão a um beneficiário de um sistema de previdência Social, por exemplo, pode envolver o recebimento e análise de uma dezena de documentos diferentes. Com isso, a proposta deste trabalho, que representa uma “prova de conceito”, corresponde a uma implementação de um sistema baseada em inteligência artificial capaz de identificar dois tipos de documentos bem conhecidos da grande maioria da população brasileira: a certidão de casamento e a certidão de óbito.

Este sistema, por representar uma prova de conceito, foi implementado para apenas dois tipos de documentos no formato de imagens. Mas se mostro suscetível de ser explorado de uma maneira mais ampla em futuros desenvolvimentos envolvendo uma gama muito maior de tipos de documentos como comprovantes de residência, carteiras de identificação, declarações de cartórios, etc.., sendo uma etapa importante no processo de criação de um protótipo realmente operativo. 


### 2. Modelagem

O modelo correspondeu a construção de uma rede *Convolutional Neural Network (CNN)* combinada com uma rede *Fully Conected*.  Foi aplicada a técnica de *TRANSFER LEARNING* baseada em um VGG16 *(Visual Geometry Group)* pré-treinada com *dataset Imagenet*.

Esta arquitetura VGG16 apresenta 16 camadas, sendo constituídas por *convolutional layers, max pooling layers, activation layers e fully connected layers*. Ao todo há 13 camadas de convolução, 5 camadas de *max pooling* e 3 camadas densas.

A Base de dados corresponde a 119 imagens de certidões de óbito e 103 imagens de certidões de casamento. As imagens em formato PDF foram convertidas na extensão JPG. O sistema foi implementado com a utilização da plataforma *JUPYTER NOTEBOOK* e uso da linguagem de programação *PYTHON*.

Foram utilizados os pesos da rede convolucional pré treinada, onde a rede *Fully Conected* original da VGG16 foi desconectada e construída uma nova rede densa com 64 neurônios na camada intermediaria e 2 neurônios na camada de saída, já que temos 2 rótulos na base de dados. Outras técnicas utilizadas foram *pooling* e *dropout*.


### 3. Resultados

A acurácia do sistema ficou em 93%. Os erros de classificação foram semelhantes entre as duas classes. Em relação a matriz de confusão, na base de validação, das 26 imagens de certidão de casamento, 2 foram classificadas como óbito; em relação as imagens de certidão de óbito, das 30 imagens processadas, 2 foram classificadas como casamento. 


### 4. Conclusões

O sistema apresentou bons resultados de forma geral, porém outras combinações de valores dos parâmetros envolvidos como taxa de aprendizado ou diferentes números de neurônios, por exemplos, podem ser testados a fim de que melhores resultados possam ser encontrados. Outro teste de melhoria poderia envolver o desligamento de algumas camadas convolucionais responsáveis pelas features mais específicas de uma imagem, de forma a customizar ainda mais a rede para o caso de imagens específicas de documentos.  

A quantidade de imagens do banco de dados deve ser aumentada, o que resultará em uma maior generalização do sistema. Procurou-se neste trabalho minimizar este problema com a adoção de *Data Augmentation e Transfer Learning* com uma rede pré-treinada com menor profundidade dentre as redes disponibilizadas na plataforma Keras.  

O sistema se mostro suscetível de ser explorado de uma maneira mais ampla em futuros desenvolvimentos envolvendo uma gama muito maior de tipos de documentos.

A sugestão para outros projetos de identificação ou classificação de documentos em imagens seria a utilização de um *Optical Character Recognition (OCR)* para captura dos textos e posterior uso de Processamento de Linguagem Natural *(NLP - Natural Language Processing)*.


---

Matrícula: 201.190.055

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*

