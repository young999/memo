# memo

https://www.gov.kr/mw/AA020InfoCappView.do?HighCtgCD=&CappBizCD=12100000016



function getQueryParamsFromString(queryString) {
    let queryParams = {};

    // 쿼리 스트링 앞의 '?'를 제거
    if (queryString.startsWith('?')) {
        queryString = queryString.slice(1);
    }

    // 쿼리 스트링이 빈 문자열이 아니면 처리 시작
    if (queryString) {
        let params = queryString.split('&');
        params.forEach(param => {
            let [key, value] = param.split('=');
            queryParams[decodeURIComponent(key)] = decodeURIComponent(value || '');
        });
    }

    return queryParams;
}

// 예제 사용법
let queryString = "?name=JohnDoe&age=25";
let params = getQueryParamsFromString(queryString);
console.log(params); // { name: "JohnDoe", age: "25" }

function isEmptyObject(obj) {
    return Object.keys(obj).length === 0;
}
