.. _api:

===================================================
REST API
===================================================

| Digest API는 노드가 블록체인 데이터를 탐색할 수 있도록 합니다.
| 지갑이나 블록체인 탐색기와 같은 응용 프로그램에 사용할 수 있습니다.

* API는 HTTP/2 network protocol를 통해 제공됩니다.
* 응답 메시지는 `HAL <https://datatracker.ietf.org/doc/html/draft-kelly-json-hal-08>`_ 을 따르며 *JSON* 형식으로 전달됩니다.
* API 데이터 스토리지는 Mitum Currency의 :ref:`config` 에서 설정할 수 있습니다.
* Mitum의 메인 스토리지가 사용되거나 별도의 데이터베이스를 사용할 수도 있습니다.
* 서비스 호스트가 로컬호스트이거나 별도의 파일이 설정되지 않은 경우 HTTP/2에 의해 요구되는 TLS certificates는 무작위의 자체 서명 인증서를 생성합니다.

| 어떤 문제로 operation이 블록에 저장되지 않은 경우 응답에 의해 이유를 확인할 수 있습니다.

---------------------------------------------------
Summary
---------------------------------------------------

| 다음은 Mitum Currency의 REST API 요약입니다.

+----------------------------------------+-----------------------+------------------------------------+
| REQUEST URL                            | METHOD                | RESPONSE                           |
+========================================+=======================+====================================+
| /                                      | GET                   | Node information                   |
+----------------------------------------+-----------------------+------------------------------------+
| /block/manifests                       | GET                   | All block manifests                |
+----------------------------------------+-----------------------+------------------------------------+
| /block/{height}                        | GET                   | Block by block height              |
+----------------------------------------+-----------------------+------------------------------------+
| /block/{height}/manifest               | GET                   | Block manifest by block height     |
+----------------------------------------+-----------------------+------------------------------------+
| /block/{height}/operations             | GET                   | All operations of block            |
+----------------------------------------+-----------------------+------------------------------------+
| /block/{block_hash}                    | GET                   | Block by block hash                |
+----------------------------------------+-----------------------+------------------------------------+
| /block/{block_hash}/manifest           | GET                   | Block manifest by block hash       |
+----------------------------------------+-----------------------+------------------------------------+
| /block/operations                      | GET                   | All operations                     |
+----------------------------------------+-----------------------+------------------------------------+
| /block/operation/{fact_hash}           | GET                   | Operation by fact hash             |
+----------------------------------------+-----------------------+------------------------------------+
| /account/{address}                     | GET                   | Latest state of account            |
+----------------------------------------+-----------------------+------------------------------------+
| /account/{address}/operations          | GET                   | Operations related to account      |
+----------------------------------------+-----------------------+------------------------------------+
| /accounts?publickey={public_key}       | GET                   | Accounts related to public key     |
+----------------------------------------+-----------------------+------------------------------------+
| /builder/operation                     | GET                   | Available Operation types          |
+----------------------------------------+-----------------------+------------------------------------+
| /builder/operation/fact/template/{fact}| GET                   | Fact template                      |
+----------------------------------------+-----------------------+------------------------------------+
| /builder/operation/fact                | POST {fact}           | Operation message from fact        |
+----------------------------------------+-----------------------+------------------------------------+
| /builder/operation/sign                | POST {operation}      | Operation with hash from operation |
+----------------------------------------+-----------------------+------------------------------------+
| /builder/send                          | POST {operation/seal} | Broadcast seal                     |
+----------------------------------------+-----------------------+------------------------------------+
| /currency                              | GET                   | All currencies                     |
+----------------------------------------+-----------------------+------------------------------------+
| /currency/{currency_id}                | GET                   | Currency by currency id            |
+----------------------------------------+-----------------------+------------------------------------+

| 자세한 내용은 `Mitum Currency Digest API Docs <https://rapidoc.test.protocon.network/>`_ 를 참고하세요.

| 이 문서는 Mitum Blocksign나 Mitum Blockcity API에 대한 아무런 정보도 제공하지 않습니다. Mitum Blocksign에 대해서는 `Mitum Blocksign Digest API Docs <https://rapidoc.blocksign.protocon.network>`_ 를 확인하세요. 