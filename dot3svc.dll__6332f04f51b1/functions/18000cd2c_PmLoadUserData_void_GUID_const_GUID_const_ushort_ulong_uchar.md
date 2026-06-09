# PmLoadUserData(void *,_GUID const *,_GUID const *,ushort *,ulong *,uchar * *)

- ea: `0x18000cd2c`
- end: `0x18000ce20`
- name: `?PmLoadUserData@@YAKPEAXPEBU_GUID@@1PEAGPEAKPEAPEAE@Z`
- size: `244`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, GUID *rguid, GUID *, LPCWSTR lpValueName, unsigned int *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800206f8`
- `0x180020844`
- `0x180020da4`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000cd2c`
- `0x18001d168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cda8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cda8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdd2`

## pseudocode

```c

```
