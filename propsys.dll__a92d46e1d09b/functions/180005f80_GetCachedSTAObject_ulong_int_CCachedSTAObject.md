# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x180005f80`
- end: `0x1800060d4`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000595c`
- `0x180007190`

## callees

- `0x1800059cc`
- `0x180005f80`
- `0x1800062b0`
- `0x18006f1fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006083`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006083`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006029`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006029`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005fb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005fb1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800060a2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800060a2`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18000600c`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18000600c`

## pseudocode

```c

```
