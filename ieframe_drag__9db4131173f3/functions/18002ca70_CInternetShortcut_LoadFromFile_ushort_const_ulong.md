# CInternetShortcut::LoadFromFile(ushort const *,ulong)

- ea: `0x18002ca70`
- end: `0x18002cee7`
- name: `?LoadFromFile@CInternetShortcut@@QEAAJPEBGK@Z`
- size: `1143`
- prototype: `int(CInternetShortcut *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002c148`
- `0x18006c770`
- `0x18007b5a0`
- `0x1800834d0`
- `0x1800cfaf0`
- `0x1800d4450`
- `0x180151e90`

## callees

- `0x18002ca70`
- `0x180068754`
- `0x1800b83c8`
- `0x1800bc150`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18002caae`
- `KERNEL32!CreateMutexW` at `0x18002caae`
- `KERNEL32!GetProcessHeap` at `0x18002cd29`
- `KERNEL32!GetProcessHeap` at `0x18002cd29`
- `KERNEL32!HeapAlloc` at `0x18002cd3b`
- `KERNEL32!HeapAlloc` at `0x18002cd3b`
- `KERNEL32!CloseHandle` at `0x18002ccfa`
- `KERNEL32!CloseHandle` at `0x18002cdec`
- `KERNEL32!CloseHandle` at `0x18002ccfa`
- `KERNEL32!CloseHandle` at `0x18002cdec`
- `KERNEL32!GetLastError` at `0x18002cd9d`
- `KERNEL32!GetLastError` at `0x18002cd9d`
- `KERNEL32!ReleaseMutex` at `0x18002cceb`
- `KERNEL32!ReleaseMutex` at `0x18002cde3`
- `KERNEL32!ReleaseMutex` at `0x18002cceb`
- `KERNEL32!ReleaseMutex` at `0x18002cde3`
- `KERNEL32!WaitForSingleObject` at `0x18002cad1`
- `KERNEL32!WaitForSingleObject` at `0x18002cad1`
- `KERNEL32!SetLastError` at `0x18002ce00`
- `KERNEL32!SetLastError` at `0x18002ce00`
- `iertutil!__imp_Str_SetPtrW` at `0x18002caec`
- `iertutil!__imp_Str_SetPtrW` at `0x18002caec`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18002cbf5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18002cbf5`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002cec1`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002cec1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x18002cc87`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x18002cc87`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x18002cac3`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x18002cac3`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ccf1`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002cdf5`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ccf1`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002cdf5`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x18002cc3f`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x18002cc3f`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002cc62`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002cc62`

## pseudocode

```c

```
