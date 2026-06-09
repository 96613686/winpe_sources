# USER_SESSION::Impersonate(TOKEN_CACHE_ENTRY *,int *)

- ea: `0x1800116a4`
- end: `0x18001189e`
- name: `?Impersonate@USER_SESSION@@AEAAJPEAVTOKEN_CACHE_ENTRY@@PEAH@Z`
- size: `506`
- prototype: `__int64 __fastcall(USER_SESSION *this, struct TOKEN_CACHE_ENTRY *, int *)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000ed00`
- `0x18000f370`
- `0x18000f560`
- `0x18000f7a0`
- `0x18000f930`
- `0x1800101a0`
- `0x180010370`
- `0x1800113d0`
- `0x1800123a0`
- `0x180012c90`

## callees

- `0x1800116a4`
- `0x18001ff3c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800117d9`
- `msvcrt!wcscpy_s` at `0x1800117d9`
- `KERNEL32!GetLastError` at `0x1800116f5`
- `KERNEL32!GetLastError` at `0x180011721`
- `KERNEL32!GetLastError` at `0x1800116f5`
- `KERNEL32!GetLastError` at `0x180011721`
- `ADVAPI32!SetThreadToken` at `0x180011717`
- `ADVAPI32!SetThreadToken` at `0x180011717`
- `Secur32!GetUserNameExW` at `0x1800117a6`
- `Secur32!GetUserNameExW` at `0x1800117c2`
- `Secur32!GetUserNameExW` at `0x1800117a6`
- `Secur32!GetUserNameExW` at `0x1800117c2`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011870`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180011870`

## pseudocode

```c

```
