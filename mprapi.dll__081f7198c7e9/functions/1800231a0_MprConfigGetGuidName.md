# MprConfigGetGuidName

- ea: `0x1800231a0`
- end: `0x180023207`
- name: `MprConfigGetGuidName`
- size: `103`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, PWSTR pszFriendlyName, PWCHAR pszBuffer, DWORD dwBufferSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180022f2c`

## callees

- `0x18000a354`
- `0x1800231a0`
- `0x180027d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800231cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800231cf`

## pseudocode

```c

```
