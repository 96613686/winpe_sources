# web::http::client::details::winhttp_request_context::on_send_request_validate_cn(void)

- ea: `0x1800db690`
- end: `0x1800dbc89`
- name: `?on_send_request_validate_cn@winhttp_request_context@details@client@http@web@@QEAAXXZ`
- size: `1529`
- prototype: `void __fastcall(web::http::client::details::winhttp_request_context *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d80b0`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x180019588`
- `0x18001a030`
- `0x1800be5f0`
- `0x1800d7b70`
- `0x1800d8010`
- `0x1800db690`
- `0x1801407ac`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800dba50`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800dba50`
- `CRYPT32!CertFreeCertificateChain` at `0x1800dbc48`
- `CRYPT32!CertFreeCertificateChain` at `0x1800dbc48`
- `CRYPT32!CertGetCertificateChain` at `0x1800db91b`
- `CRYPT32!CertGetCertificateChain` at `0x1800db91b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dbc5b`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dbc5b`
- `WINHTTP!WinHttpQueryOption` at `0x1800db6f0`
- `WINHTTP!WinHttpQueryOption` at `0x1800db6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dba5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dba5e`

## string_xrefs

- `0x1800dbb47`: `Incorrect common name`

## pseudocode

```c

```
