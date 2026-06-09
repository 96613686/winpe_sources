# PuGetDiskPropertiesByHandle(void *,ushort const *,int,int,int,int,int,PU_DISK_PROPERTIES *)

- ea: `0x1801a1fac`
- end: `0x1801a2cfc`
- name: `?PuGetDiskPropertiesByHandle@@YAHPEAXPEBGHHHHHPEAVPU_DISK_PROPERTIES@@@Z`
- size: `3408`
- prototype: `__int64 __usercall@<rax>(HANDLE hDevice@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, int@<r9d>, int, int, int, struct PU_DISK_PROPERTIES *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0x18011fec8`
- `0x1801a1f18`

## callees

- `0x180006350`
- `0x18000cd3c`
- `0x1800298d0`
- `0x18002b5e4`
- `0x1800c87b4`
- `0x18019a6d8`
- `0x18019aa70`
- `0x18019ac68`
- `0x18019cc38`
- `0x18019cde0`
- `0x18019d15c`
- `0x18019f5d8`
- `0x1801a0f00`
- `0x1801a1434`
- `0x1801a1694`
- `0x1801a17c0`
- `0x1801a1b64`
- `0x1801a1fac`
- `0x1801a35c4`
- `0x1801a470c`
- `0x1801a5788`
- `0x1801a66c8`
- `0x1801aa148`
- `0x1801aa74c`
- `0x1801aa884`
- `0x1801ab278`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2191`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a21d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a28f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a29dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2b5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2cc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2191`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a21d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a28f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a29dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2b5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a2cc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2156`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a27a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a280d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a299d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2bfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2156`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a27a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a280d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a299d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2bfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2c93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a2179`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a29c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a2179`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a29c3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2217`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2285`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2300`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2368`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a240d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2217`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2285`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2300`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2368`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a240d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a2cb3`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a2cb3`

## string_xrefs

- `0x1801a21e2`: `StringCchCopy`
- `0x1801a2a4f`: `PuCreateDeviceInfoSet`
- `0x1801a28a8`: `PuCreateGptRegionList`
- `0x1801a2880`: `PuCreateMbrRegionList`
- `0x1801a2ac0`: `GetDeviceRegistryProperty`

## pseudocode

```c

```
