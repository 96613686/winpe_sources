# SuCreatePool(_SP_POOL_INFO *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *,_SU_POOL_OBJECT * *)

- ea: `0x1801bb63c`
- end: `0x1801bbab6`
- name: `?SuCreatePool@@YAHPEAU_SP_POOL_INFO@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z3PEAPEAU_SU_POOL_OBJECT@@@Z`
- size: `1146`
- prototype: `__int64 __usercall@<rax>(struct _SP_POOL_INFO *@<rcx>, struct _LIST_ENTRY *@<rdx>, int (__high *)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *)@<r8>, void *@<r9>, struct _SU_POOL_OBJECT **)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002d170`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x18007c3a0`
- `0x18019a4a4`
- `0x1801b6c68`
- `0x1801b7e28`
- `0x1801b7fcc`
- `0x1801bb1cc`
- `0x1801bb4b0`
- `0x1801bb63c`
- `0x1801bc668`
- `0x1801bc874`
- `0x1801bc9e8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb8a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb8a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb6e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bba87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb6e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bb757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bba87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bb6c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bb8c0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bb6c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801bb8c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801bba73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801bba73`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801bb868`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801bb868`

## string_xrefs

- `0x1801bb87a`: `DeviceIoControl - IOCTL_SPACEPORT_CREATE_POOL`

## pseudocode

```c

```
