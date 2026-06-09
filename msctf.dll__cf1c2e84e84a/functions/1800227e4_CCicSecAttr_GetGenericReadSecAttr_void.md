# CCicSecAttr::GetGenericReadSecAttr(void)

- ea: `0x1800227e4`
- end: `0x180022888`
- name: `?GetGenericReadSecAttr@CCicSecAttr@@QEAAPEAU_SECURITY_ATTRIBUTES@@XZ`
- size: `164`
- prototype: `struct _SECURITY_ATTRIBUTES *__fastcall(CCicSecAttr *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c7ac`
- `0x18005c8c0`

## callees

- `0x1800227e4`
- `0x1800229d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002285b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002285b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800227f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800227f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002280c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002280c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002281f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002281f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002284e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002284e`

## pseudocode

```c

```
