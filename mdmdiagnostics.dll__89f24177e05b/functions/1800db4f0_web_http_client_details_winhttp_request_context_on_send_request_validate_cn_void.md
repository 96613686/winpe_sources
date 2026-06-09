# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x1800db4f0`
- end: `0x1800dbae9`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1529`
- prototype: `void __fastcall(web::http::client::details::winhttp_request_context *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d7f10`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019508`
- `0x180019fa0`
- `0x1800be450`
- `0x1800d79d0`
- `0x1800d7e70`
- `0x1800db4f0`
- `0x18013e390`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800db8b0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800db8b0`
- `CRYPT32!CertFreeCertificateChain` at `0x1800dbaa8`
- `CRYPT32!CertFreeCertificateChain` at `0x1800dbaa8`
- `CRYPT32!CertGetCertificateChain` at `0x1800db77b`
- `CRYPT32!CertGetCertificateChain` at `0x1800db77b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dbabb`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dbabb`
- `WINHTTP!WinHttpQueryOption` at `0x1800db550`
- `WINHTTP!WinHttpQueryOption` at `0x1800db550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8be`

## string_xrefs

- `0x1800db9a7`: `Incorrect common name`

## pseudocode

```c

```
