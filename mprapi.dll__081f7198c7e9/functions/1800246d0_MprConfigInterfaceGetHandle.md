# MprConfigInterfaceGetHandle

- ea: `0x1800246d0`
- end: `0x18002479b`
- name: `MprConfigInterfaceGetHandle`
- size: `203`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, LPWSTR lpwsInterfaceName, HANDLE *phRouterInterface)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180035f84`

## callees

- `0x180022324`
- `0x1800246d0`
- `0x180027d5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002476d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002477e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002476d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002477e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024711`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024711`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024746`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024746`

## pseudocode

```c

```
