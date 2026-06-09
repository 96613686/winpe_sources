# SuSetDrivesMaintenance(_GUID *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),uchar,ulong)

- ea: `0x1801b3d44`
- end: `0x1801b3eed`
- name: `?SuSetDrivesMaintenance@@YAHPEAU_GUID@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@ZEK@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(struct _GUID *@<rcx>, struct _LIST_ENTRY *@<rdx>, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *)@<r8>, unsigned __int8@<r9b>, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18009b8b8`

## callees

- `0x180195a90`
- `0x1801b0d44`
- `0x1801b1280`
- `0x1801b3d44`
- `0x1801b44ac`
- `0x1801b45f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b3e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b3ec9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b3ec9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b3d82`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b3e24`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b3d82`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b3e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b3ebd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b3ebd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b3e04`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801b3e04`

## string_xrefs

- `0x1801b3e10`: `SiUpdateSpaces`

## pseudocode

```c

```
