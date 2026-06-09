# MprConfigGetFriendlyName

- ea: `0x180023130`
- end: `0x180023197`
- name: `MprConfigGetFriendlyName`
- size: `103`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, PWSTR pszGuidName, PWCHAR pszBuffer, DWORD dwBufferSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180022f2c`

## callees

- `0x18000a198`
- `0x180023130`
- `0x180027d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002317f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002317f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002315f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002315f`

## pseudocode

```c

```
