# PuCreatePartition(ushort const *,PU_DISK_PROPERTIES *,unsigned __int64,unsigned __int64,ulong,PU_CREATE_PARTITION_PARAMETERS *,unsigned __int64 *)

- ea: `0x18019dd64`
- end: `0x18019e551`
- name: `?PuCreatePartition@@YAJPEBGPEAVPU_DISK_PROPERTIES@@_K2KPEAUPU_CREATE_PARTITION_PARAMETERS@@PEA_K@Z`
- size: `2029`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, struct PU_DISK_PROPERTIES *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned int, struct PU_CREATE_PARTITION_PARAMETERS *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x180114b00`

## callees

- `0x180006350`
- `0x1800298d0`
- `0x18019a4a4`
- `0x18019a6b4`
- `0x18019c688`
- `0x18019cae0`
- `0x18019d8c4`
- `0x18019dd64`
- `0x18019e558`
- `0x1801a0708`
- `0x1801a0db0`
- `0x1801a5fb4`
- `0x1801a6c8c`
- `0x1801a9494`
- `0x1801a96d8`
- `0x1801a9a0c`
- `0x1801a9d4c`
- `0x1801aa228`
- `0x1801aa3e4`
- `0x1801aab6c`
- `0x1801aad34`
- `0x1801aafdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019df78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e3a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019df78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e3a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e505`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019e505`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019de07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019e3d8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019de07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019e3d8`

## string_xrefs

- `0x18019e130`: `DeleteBands`
- `0x18019de5a`: `Disk is read-only`
- `0x18019e3c6`: `PuRecreateRegionList`
- `0x18019e382`: `PuWriteLayout`
- `0x18019e0d0`: `PuCreatePartLayout`
- `0x18019e071`: `PuCreateRegions`

## pseudocode

```c

```
