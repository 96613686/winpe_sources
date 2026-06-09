# CInternetShortcut::LoadFromFile(ushort const *,ulong)

- ea: `0x18002eb70`
- end: `0x18002f061`
- name: `?LoadFromFile@CInternetShortcut@@QEAAJPEBGK@Z`
- size: `1265`
- prototype: `int(CInternetShortcut *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002e1dc`
- `0x180071b44`
- `0x180081620`
- `0x1800d7ce0`
- `0x1800dc9a0`
- `0x180161b40`

## callees

- `0x18002eb70`
- `0x18006d374`
- `0x1800bf0d8`
- `0x1800c2e80`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18002ebae`
- `KERNEL32!CreateMutexW` at `0x18002ebae`
- `KERNEL32!GetProcessHeap` at `0x18002ee6c`
- `KERNEL32!GetProcessHeap` at `0x18002ee6c`
- `KERNEL32!HeapAlloc` at `0x18002ee84`
- `KERNEL32!HeapAlloc` at `0x18002ee84`
- `KERNEL32!CloseHandle` at `0x18002ee36`
- `KERNEL32!CloseHandle` at `0x18002ef47`
- `KERNEL32!CloseHandle` at `0x18002ee36`
- `KERNEL32!CloseHandle` at `0x18002ef47`
- `KERNEL32!GetLastError` at `0x18002eeec`
- `KERNEL32!GetLastError` at `0x18002eeec`
- `KERNEL32!ReleaseMutex` at `0x18002ee1b`
- `KERNEL32!ReleaseMutex` at `0x18002ef38`
- `KERNEL32!ReleaseMutex` at `0x18002ee1b`
- `KERNEL32!ReleaseMutex` at `0x18002ef38`
- `KERNEL32!WaitForSingleObject` at `0x18002ebdd`
- `KERNEL32!WaitForSingleObject` at `0x18002ebdd`
- `KERNEL32!SetLastError` at `0x18002ef67`
- `KERNEL32!SetLastError` at `0x18002ef67`
- `iertutil!__imp_Str_SetPtrW` at `0x18002ebfe`
- `iertutil!__imp_Str_SetPtrW` at `0x18002ebfe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18002ed0d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18002ed0d`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002f035`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002f035`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x18002edb1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_Set` at `0x18002edb1`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x18002ebc9`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x18002ebc9`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ee27`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ef56`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ee27`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x18002ef56`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x18002ed5d`
- `PROPSYS!PSCreatePropertyStoreFromObject` at `0x18002ed5d`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002ed86`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002ed86`

## pseudocode

```c

```
