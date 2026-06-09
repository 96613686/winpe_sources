# MprAdminConnectionEnumEx

- ea: `0x180004350`
- end: `0x180004548`
- name: `MprAdminConnectionEnumEx`
- size: `504`
- prototype: `DWORD __stdcall(RAS_SERVER_HANDLE hRasServer, PMPRAPI_OBJECT_HEADER pObjectHeader, DWORD dwPreferedMaxLen, LPDWORD lpdwEntriesRead, LPDWORD lpdwTotalEntries, PRAS_CONNECTION_EX *ppRasConn, LPDWORD lpdwResumeHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004350`
- `0x180051112`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000452b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000452b`
- `RPCRT4!NdrClientCall3` at `0x18000442d`
- `RPCRT4!NdrClientCall3` at `0x18000442d`

## pseudocode

```c

```
