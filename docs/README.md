# Helm Chart Repository
여러 Helm 차트를 GitHub Pages를 통해 배포 및 버전 관리하기 위한 저장소
각 하위 폴더에 저장된 인덱스 파일로 버전을 확인이 가능

## 차트 구성 및 패키징
1. **차트 받기**
   ```bash
   helm repo add grafana-alloy https://vegeterianlee.github.io/helm-chart-repo/grafana-alloy
   
2. **차트 수정 및 버전 업데이트**  
   - 차트를 받은 뒤, 압축을 풀고 소스 코드를 받기
   - 각 차트(예: grafana-alloy)의 소스 코드가 로컬에서 수정된 사항을 반영해 upgrade 명령을 실행
   - 이 경우, templates이하 차트와 최종 반영된 values를 기존 values.yaml에 덮어쓰기

3. **차트 패키징**  
   - 로컬에서 아래의 차트 패키지를 생성
      ```bash
      helm package ./alloy -d ./grafana-alloy

4. **index.yaml 파일 생성 및 커밋**
   - index.yaml 파일을 생성
      ``` bash
      helm repo index ./docs/grafana-alloy --url https://vegeterianlee.github.io/helm-chart-repo/grafana-alloy
      ```
   - tgz 파일과 index.yaml 파일을 커밋
