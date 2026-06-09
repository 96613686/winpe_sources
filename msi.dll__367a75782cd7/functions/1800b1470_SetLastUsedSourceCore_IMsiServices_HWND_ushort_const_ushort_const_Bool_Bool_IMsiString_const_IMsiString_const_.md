# SetLastUsedSourceCore(IMsiServices &,HWND__ *,ushort const *,ushort const *,Bool,Bool,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,bool,bool,bool *)

- ea: `0x1800b1470`
- end: `0x1800b314c`
- name: `?SetLastUsedSourceCore@@YAPEAVIMsiRecord@@AEAVIMsiServices@@PEAUHWND__@@PEBG2W4Bool@@3PEAPEBVIMsiString@@44444_N5PEA_N@Z`
- size: `7388`
- prototype: `struct IMsiRecord *__fastcall(__int64 *, void *, const WCHAR *, unsigned __int16 *, int, unsigned int, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, char, char, _BYTE *)`
- caller_count: `2`
- callee_count: `43`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1801b0db0`
- `0x1801b2dc0`

## callees

- `0x18000a150`
- `0x180015950`
- `0x180022120`
- `0x180025904`
- `0x180025a18`
- `0x18002684c`
- `0x18002b35c`
- `0x18002e3ec`
- `0x180035a8c`
- `0x18004295c`
- `0x18004b560`
- `0x180066074`
- `0x180068680`
- `0x180079dd0`
- `0x18008be90`
- `0x18008f3e8`
- `0x180090f70`
- `0x180098b50`
- `0x1800a5fc4`
- `0x1800b1450`
- `0x1800b1470`
- `0x1800b7800`
- `0x1800b8034`
- `0x1800b8e10`
- `0x1800bc708`
- `0x1800cddb0`
- `0x1800d6ff0`
- `0x1800e92ec`
- `0x18013a830`
- `0x180142ba8`
- `0x180143508`
- `0x180149bb4`
- `0x18014a6fc`
- `0x180154eb4`
- `0x180156530`
- `0x180157584`
- `0x18016e120`
- `0x180181e08`
- `0x1801b2e6c`
- `0x1801cc968`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800b1953`
- `KERNEL32!InitializeCriticalSection` at `0x1800b1953`
- `KERNEL32!CloseHandle` at `0x1800b26de`
- `KERNEL32!CloseHandle` at `0x1800b2988`
- `KERNEL32!CloseHandle` at `0x1800b26de`
- `KERNEL32!CloseHandle` at `0x1800b2988`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2ba3`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2ba3`
- `KERNEL32!EnterCriticalSection` at `0x1800b2b7b`
- `KERNEL32!EnterCriticalSection` at `0x1800b2b7b`
- `KERNEL32!GlobalFree` at `0x1800b274c`
- `KERNEL32!GlobalFree` at `0x1800b2adb`
- `KERNEL32!GlobalFree` at `0x1800b2bbb`
- `KERNEL32!GlobalFree` at `0x1800b307f`
- `KERNEL32!GlobalFree` at `0x1800b274c`
- `KERNEL32!GlobalFree` at `0x1800b2adb`
- `KERNEL32!GlobalFree` at `0x1800b2bbb`
- `KERNEL32!GlobalFree` at `0x1800b307f`

## string_xrefs

- `0x1800b176c`: `Installer\Products`
- `0x1800b1583`: `Entering CMsiConfigurationManager::SetLastUsedSource.`
- `0x1800b16bc`: `Installer\Patches`
- `0x1800b2241`: `Specifed source is%s already in a list.`
- `0x1800b294b`: `MSI_LUA: Consent provided to add new source`
- `0x1800b2a81`: `Warning: rejected attempt to add new source '%s' (product: %s)`

## pseudocode

```c

```
