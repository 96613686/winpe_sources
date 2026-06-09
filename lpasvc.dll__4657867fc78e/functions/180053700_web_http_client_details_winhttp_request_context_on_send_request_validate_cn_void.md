# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x180053700`
- end: `0x180053db1`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1713`
- prototype: `void __fastcall(web::http::client::details::winhttp_request_context *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050120`

## callees

- `0x18000df90`
- `0x18000e430`
- `0x18000e46c`
- `0x18000ebd0`
- `0x18000ebe8`
- `0x180038ff0`
- `0x18004fbe0`
- `0x180050080`
- `0x180053700`
- `0x18007067c`
- `0x1800716c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005376e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005376e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ab7`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180053aa9`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180053aa9`
- `CRYPT32!CertFreeCertificateChain` at `0x180053d6a`
- `CRYPT32!CertFreeCertificateChain` at `0x180053d6a`
- `CRYPT32!CertFreeCertificateContext` at `0x180053d7d`
- `CRYPT32!CertFreeCertificateContext` at `0x180053d7d`
- `CRYPT32!CertGetCertificateChain` at `0x180053976`
- `CRYPT32!CertGetCertificateChain` at `0x180053976`
- `WINHTTP!WinHttpQueryOption` at `0x180053760`
- `WINHTTP!WinHttpQueryOption` at `0x180053760`

## string_xrefs

- `0x180053b9e`: `Incorrect common name`

## pseudocode

```c

```
