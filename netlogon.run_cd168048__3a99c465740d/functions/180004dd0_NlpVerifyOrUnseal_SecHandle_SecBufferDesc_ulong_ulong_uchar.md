# NlpVerifyOrUnseal(_SecHandle *,_SecBufferDesc *,ulong,ulong *,uchar)

- ea: `0x180004dd0`
- end: `0x1800055ce`
- name: `?NlpVerifyOrUnseal@@YAJPEAU_SecHandle@@PEAU_SecBufferDesc@@KPEAKE@Z`
- size: `2046`
- prototype: `__int64 __fastcall(struct _SecHandle *, struct _SecBufferDesc *, unsigned int, unsigned int *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800559e0`
- `0x180056a40`

## callees

- `0x180004dd0`
- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x180041944`
- `0x180041a5c`
- `0x180055068`
- `0x180091010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180004e78`
- `ntdll!RtlLeaveCriticalSection` at `0x180004e78`
- `ntdll!RtlEnterCriticalSection` at `0x180004e41`
- `ntdll!RtlEnterCriticalSection` at `0x180004e41`
- `cryptdll!CDLocateCheckSum` at `0x1800052c9`
- `cryptdll!CDLocateCheckSum` at `0x1800052c9`
- `cryptdll!CDLocateCSystem` at `0x180005037`
- `cryptdll!CDLocateCSystem` at `0x180005037`

## string_xrefs

- `0x1800052fe`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180005470`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x18000552a`: `onecore\ds\netapi\svcdlls\logonsrv\server\secpkg.cxx`
- `0x180005305`: `Check->CheckSumSize <= sizeof(LocalChecksum)`

## pseudocode

```c

```
