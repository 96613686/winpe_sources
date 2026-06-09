# SuDeletePool(_SU_POOL_OBJECT *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *)

- ea: `0x1801bbabc`
- end: `0x1801bbcd0`
- name: `?SuDeletePool@@YAHPEAU_SU_POOL_OBJECT@@P6AHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX333@Z3@Z`
- size: `532`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *), void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002d880`

## callees

- `0x180029b40`
- `0x18019a4a4`
- `0x1801b6504`
- `0x1801ba464`
- `0x1801bac24`
- `0x1801bbabc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bbbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bbbda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bbcb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bbcb4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bbaf1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bbbec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bbaf1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bbbec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801bbc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801bbc99`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801bbb67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801bbb67`

## string_xrefs

- `0x1801bbb79`: `DeviceIoControl - IOCTL_SPACEPORT_DELETE_POOL`
- `0x1801bbc26`: `SuDeletePool`
- `0x1801bbc4b`: `SuDeletePool`

## pseudocode

```c

```
