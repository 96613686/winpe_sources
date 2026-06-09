# CertHelper::IsCertTimeValid(_CERT_CONTEXT const *,bool &)

- ea: `0x180096b08`
- end: `0x180096cf1`
- name: `?IsCertTimeValid@CertHelper@@YAJPEBU_CERT_CONTEXT@@AEA_N@Z`
- size: `489`
- prototype: `__int64 __fastcall(CertHelper *__hidden this, const struct _CERT_CONTEXT *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008b024`

## callees

- `0x180001aa0`
- `0x180078c20`
- `0x180096b08`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180096bda`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180096bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096bf6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180096be8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180096be8`

## string_xrefs

- `0x180096b80`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180096c49`: `onecore\termsrv\rdp\win\security\certhelper.cpp`

## pseudocode

```c

```
