# simple data pipeline project

총 3개의 서버를 구성하여 다음의 과정을 진행하였습니다.


crawling -> mysql -> logstash -> elasticsearch -> kibana

1. 크론탭을 이용하여 주기적인 crawling (5분, 30분 간격)
2. 크롤링한 데이터를 mysql에 적재하였습니다.
3. mysql에 적재된 데이터를 logstash를 이용하여 elasticsearch에 적재
4. kibana 시각화할 수 있었습니다.


ELK는 다음의 이미지를 사용하여 docker-compose로 구축하였습니다.
https://github.com/deviantony/docker-elk

![image](https://github.com/w00dy2/fashion_elasticsearch/assets/123388251/7671016d-6705-4e31-bdce-51d8b7ab4fbf)



<br>

# 주제

의류 브랜드 선택에 있어 가장 중요한 요소 중 하나인 브랜드 인지도를
무신사 랭킹 순위를 바탕으로 알아보았습니다.

<br>



# 로그스태시 설정

로그스태시를 이용하여 mysql데이터를 가져오고자 하면 jdbc 설정을 해주어야합니다.
관련 내용은 다음의 포스팅에 정리해놓았습니다.

https://velog.io/@pshyeok2/ELK-%EB%8B%A4%EC%9A%B4


elasticsearch 적재 내역

![image](https://github.com/w00dy2/fashion_elasticsearch/assets/123388251/97f1c0de-e0c8-4f12-b9f3-737ce41feb5d)

kibana를 이용한 시각화

![image](https://github.com/w00dy2/fashion_elasticsearch/assets/123388251/6318c105-b67a-491a-af95-5df9c1b4697d)
![image](https://github.com/w00dy2/fashion_elasticsearch/assets/123388251/507781fd-4c8b-4258-a2ed-7868b33c90ac)
![image](https://github.com/w00dy2/fashion_elasticsearch/assets/123388251/e8e4b6ac-dee6-4522-acd1-dce80e25b9c0)

## TODO

- [ ]  대용량 데이터 시뮬레이션
- [ ]  스트리밍 환경(Kafka, Spark Streaming) 구축해보기
- [ ]  클라우드 환경(Kuberenetes, EC2, EMR)으로 확장해보기
