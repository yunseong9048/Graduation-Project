# 강좌 강의평 기반 챗봇 모델

2024 성균관대학교 소프트웨어학과 졸업작품 - 강좌 강의평 기반 챗봇 웹 어플리케이션

## 기능
1) 강의평 요약
2) 강의평 기반 사용자의 질문을 대답해주는 챗봇
-----------------------------------------------------------------
## 프로젝트에서 사용한 기술
1) LLM: 인간의 언어를 처리하는 모델 - gpt4 사용
2) RAG: 정보 검색과 생성을 결합한 인공지능 모델
   
   2.1)데이터 - pdf 사용
   
   2.2)벡터 데이터베이스: 벡터를 저장하는 저장소. 데이터 관리 및 검색 - chromadb 사용
   
   2.3)프레임워크: 언어모델을 위한 프레임워크 - langchain 사용
   
4) streamlit: 사용자와 상호작용을 할 수 있는 어플리케이션을 쉽게 만들어주는 도구

----------------------------------------------------------------
## 모델 구조

![구조](https://github.com/user-attachments/assets/86e2735b-b16b-45fa-8f67-c33a1e8920f1)


1. 데이터 : 데이터를 로컬에서 langchain으로 가져옴
2. 임베딩: 가지고 온 데이터를 벡터로 변환
3. 벡터 데이터베이스: 벡터 저장 및 검색
4. LLM: 프롬프트 전달 및 결과 반환
5. 웹: 사용자와 상호작용
----------------------------------------------------------------

## 환경설정: anaconda
1. anaconda 가상환경 설정
   
   annaconda prompt에서 다음 명령어 입력
   
       conda create -n llm python=3.8
       activate llm
       pip install ipykernel
       python -m ipykernel install --user --name llm --display-name "llm"
       jupyter notebook
   
3. jupyter notebook 실행
   
   ipynb파일 업로드 후 ipynb 파일 실행
   
   파일 실행 후 !pip install 과 관련된 부분들은 주석처리

   file-> save and export notebook as-> executable script(파일 다운로드)
   
4. 다운받은 파일을 아나콘다의 가상환경이 설치된 위치로 이동

   C:\Users\ <사용자 계정>\anaconda3\envs\llm\Scripts
   
5. 해당 파일에서 cmd 실행 후 다음 명령어 입력
   
   streamlit run <저장한 파일 이름>

   예시)

       streamlit run final.py
   

----------------------------------------------------------------
## 데이터 저장

로컬에 "c:/data/DNN.pdf" 로 저장된 pdf를 사용한다는 가정하에 코드 작성(로컬 경로를 적절히 변경 가능)

