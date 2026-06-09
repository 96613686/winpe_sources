# HnsService::Shutdown(void)

- ea: `0x180065828`
- end: `0x180065a81`
- name: `?Shutdown@HnsService@@IEAAXXZ`
- size: `601`
- prototype: `void __fastcall(HnsService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x180066390`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005f560`
- `0x180064018`
- `0x180064754`
- `0x180064814`
- `0x180064b4c`
- `0x180065828`
- `0x180065bfc`
- `0x180065d70`
- `0x180066418`
- `0x18006d588`
- `0x180075040`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180065a13`
- `WS2_32!__imp_WSACleanup` at `0x180065a13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065a41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065a41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065894`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065894`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065943`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065911`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800658fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065928`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065933`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065933`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180065991`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180065991`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180065909`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180065909`

## pseudocode

```c

```
