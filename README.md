# kakaoarena

This code is edited in Colab.\
.py파일보다 .ipynb를 통해 구동하는 것을 추천드립니다.

코드상의 파일 경로에 유의해주시기 바랍니다.\
코드의 후반부 리스트를 저장하는 경로와 불러오는 경로가 일치되어야 합니다.

중간고사대체과제 화이팅

#코드 해설

Collaborative Filtering을 다양한 Parameter에 대해 진행합니다.

위는 주어진 Playlist의 요소들에 대하여 5가지 Parameter를 제공합니다.
Playlist에 곡이 일부 주어져 있다면,
1. 그 곡이 포함되어 있는 다른 Playlist에 속한 곡/태그들에 관한 Parameter
2. 그 곡이 포함되어 있는 앨범에 속한 곡에 관한 Parameter
3. 그 곡과 같은 아티스트 이름을 공유하는 곡에 관한 Parameter

Playlist에 태그가 일부 주어져 있다면,

4. 그 태그가 포함되어 있는 다른 Playlist에 속한 곡/태그들에 관한 Parameter

별도로, 혹시나 곡과 태그가 전혀 주어져있는 Case를 Handle하기 위해 제목관련 처리도 진행합니다.

5. 제목을 Tag화 하고(단순 Space 구분), 이를 태그처럼 다루어 이 태그가 포함되어 있는 다른 Playlist에 속한 곡/태그들에 관한 Parameter

위 5개 Parameter에 대해 (곡/태그나 나타난 횟수 * Parameter)를 구하여 더하고, 이가 높은 순으로 곡/태그를 선택합니다.
기반하여 모든 곡에 대해서 값을 구해내고 Sorting하여 가장 높은 100/10개의 곡/태그를 선택합니다.
혹시나 가장 높은 100/10개의 곡/태그를 선택하지 못하는 경우(예 : 전부다 0)
Default 값을 답안으로 제시합니다.
