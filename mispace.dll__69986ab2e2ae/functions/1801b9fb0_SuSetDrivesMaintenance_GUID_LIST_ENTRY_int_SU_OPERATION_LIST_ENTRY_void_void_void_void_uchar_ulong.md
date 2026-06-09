# SuSetDrivesMaintenance(_GUID *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),uchar,ulong)

- ea: `0x1801b9fb0`
- end: `0x1801ba17e`
- name: `?SuSetDrivesMaintenance@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@ZEK@Z`
- size: `462`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct _LIST_ENTRY *@<rdx>, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *)@<r8>, unsigned __int8@<r9b>, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18009e1d8`

## callees

- `0x18019a4a4`
- `0x1801b6c68`
- `0x1801b71d0`
- `0x1801b9fb0`
- `0x1801ba774`
- `0x1801ba8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ba08f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ba153`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ba153`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b9fee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801ba0a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b9fee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801ba0a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801ba141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801ba141`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801ba076`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801ba076`

## string_xrefs

- `0x1801ba088`: `SiUpdateSpaces`

## pseudocode

```c

```
