# CachedSTAObject_QueryInterface(ulong,int *,_GUID const &,void * *)

- ea: `0x1800060e0`
- end: `0x18000629c`
- name: `?CachedSTAObject_QueryInterface@@YAJKPEAHAEBU_GUID@@PEAPEAX@Z`
- size: `444`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800656d4`

## callees

- `0x1800059cc`
- `0x1800060e0`
- `0x1800062b0`
- `0x18006bb14`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800061f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800061f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000619d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000619d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000612b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000612b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000620f`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000620f`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18000617d`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18000617d`

## pseudocode

```c

```
