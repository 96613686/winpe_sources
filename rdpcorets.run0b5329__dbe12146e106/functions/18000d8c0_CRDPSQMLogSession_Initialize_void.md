# CRDPSQMLogSession::Initialize(void)

- ea: `0x18000d8c0`
- end: `0x18000daaa`
- name: `?Initialize@CRDPSQMLogSession@@EEAAJXZ`
- size: `490`
- prototype: `__int64 __fastcall(CRDPSQMLogSession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d5f0`

## callees

- `0x1800091a8`
- `0x18000d8c0`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x180059838`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d931`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d9de`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000d9de`
- `ntdll!WinSqmIsOptedIn` at `0x18000d8e4`
- `ntdll!WinSqmIsOptedIn` at `0x18000d8e4`
- `ntdll!WinSqmStartSession` at `0x18000da38`
- `ntdll!WinSqmStartSession` at `0x18000da38`

## string_xrefs

- `0x18000da1f`: `CoCreateGuid failed!`

## pseudocode

```c

```
