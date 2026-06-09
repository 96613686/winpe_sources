# CoGetInterceptorForOle32

- ea: `0x180014f80`
- end: `0x180015368`
- name: `CoGetInterceptorForOle32`
- size: `1000`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, IUnknown *punkOuter, const _GUID *iid, void **ppInterceptor)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180013154`
- `0x180014f80`
- `0x180015464`
- `0x1800158d8`
- `0x1800185ec`
- `0x180052390`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001516c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001516c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015183`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014ff0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800150a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800151cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014ff0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800150a8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800151cb`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001520a`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001520a`

## string_xrefs

- `0x1800152d2`: `com\ole32\com\txf\callframe\interceptor.cpp`

## pseudocode

```c

```
