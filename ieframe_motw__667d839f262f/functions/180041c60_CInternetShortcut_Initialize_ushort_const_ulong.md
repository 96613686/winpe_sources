# CInternetShortcut::Initialize(ushort const *,ulong)

- ea: `0x180041c60`
- end: `0x1800420d1`
- name: `?Initialize@CInternetShortcut@@UEAAJPEBGK@Z`
- size: `1137`
- prototype: `int(CInternetShortcut *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180041c60`
- `0x180068754`
- `0x1800b83c8`
- `0x1800bc150`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180041c9e`
- `KERNEL32!CreateMutexW` at `0x180041c9e`
- `KERNEL32!GetProcessHeap` at `0x180041f16`
- `KERNEL32!GetProcessHeap` at `0x180041f16`
- `KERNEL32!HeapAlloc` at `0x180041f28`
- `KERNEL32!HeapAlloc` at `0x180041f28`
- `KERNEL32!CloseHandle` at `0x180041ee7`
- `KERNEL32!CloseHandle` at `0x180041fd6`
- `KERNEL32!CloseHandle` at `0x180041ee7`
- `KERNEL32!CloseHandle` at `0x180041fd6`
- `KERNEL32!GetLastError` at `0x180041f87`
- `KERNEL32!GetLastError` at `0x180041f87`
- `KERNEL32!ReleaseMutex` at `0x180041ed8`
- `KERNEL32!ReleaseMutex` at `0x180041fcd`
- `KERNEL32!ReleaseMutex` at `0x180041ed8`
- `KERNEL32!ReleaseMutex` at `0x180041fcd`
- `KERNEL32!WaitForSingleObject` at `0x180041cc1`
- `KERNEL32!WaitForSingleObject` at `0x180041cc1`
- `KERNEL32!SetLastError` at `0x180041fea`
- `KERNEL32!SetLastError` at `0x180041fea`
- `iertutil!__imp_Str_SetPtrW` at `0x180041cdc`
- `iertutil!__imp_Str_SetPtrW` at `0x180041cdc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180041de2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180041de2`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800420ab`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x1800420ab`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x180041e74`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x180041e74`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x180041cb3`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x180041cb3`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x180041ede`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x180041fdf`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x180041ede`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x180041fdf`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x180041e2c`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x180041e2c`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x180041e4f`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x180041e4f`

## pseudocode

```c

```
