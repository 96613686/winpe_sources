# CoGetInterceptorForOle32

- ea: `0x1800121a0`
- end: `0x18001259e`
- name: `CoGetInterceptorForOle32`
- size: `1022`
- prototype: `HRESULT __fastcall(const _GUID *iidIntercepted, IUnknown *punkOuter, const _GUID *iid, void **ppInterceptor)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180010594`
- `0x18001217c`
- `0x1800121a0`
- `0x1800126bc`
- `0x180012b98`
- `0x180046460`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001220b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800122c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800123b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001220b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800122c0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800123b7`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180012421`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180012421`

## string_xrefs

- `0x180012511`: `com\ole32\com\txf\callframe\interceptor.cpp`

## pseudocode

```c

```
