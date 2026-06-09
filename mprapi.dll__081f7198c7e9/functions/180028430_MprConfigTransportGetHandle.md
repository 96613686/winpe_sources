# MprConfigTransportGetHandle

- ea: `0x180028430`
- end: `0x1800284eb`
- name: `MprConfigTransportGetHandle`
- size: `187`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwTransportId, HANDLE *phRouterTransport)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001808c`
- `0x1800181b8`
- `0x1800364f4`

## callees

- `0x180022be8`
- `0x180027d5c`
- `0x180028430`
- `0x180029414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002846a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002846a`

## pseudocode

```c

```
