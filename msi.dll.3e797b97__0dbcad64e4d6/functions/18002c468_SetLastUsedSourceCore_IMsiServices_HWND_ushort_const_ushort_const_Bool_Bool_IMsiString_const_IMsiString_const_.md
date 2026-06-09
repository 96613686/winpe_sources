# SetLastUsedSourceCore(IMsiServices &,HWND__ *,ushort const *,ushort const *,Bool,Bool,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,bool,bool,bool *)

- ea: `0x18002c468`
- end: `0x18002e17b`
- name: `?SetLastUsedSourceCore@@YAPEAVIMsiRecord@@AEAVIMsiServices@@PEAUHWND__@@PEBG2W4Bool@@3PEAPEBVIMsiString@@44444_N5PEA_N@Z`
- size: `7443`
- prototype: ``
- caller_count: `2`
- callee_count: `43`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1801b8a50`
- `0x1801bab80`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180006970`
- `0x18000c4bc`
- `0x180010ac0`
- `0x180014528`
- `0x180015c14`
- `0x180027634`
- `0x18002c444`
- `0x18002c468`
- `0x18003c030`
- `0x1800491f0`
- `0x18004c8f0`
- `0x180067fec`
- `0x180077470`
- `0x180082cec`
- `0x180086264`
- `0x180087e68`
- `0x18008c93c`
- `0x18009ad3c`
- `0x1800ae46c`
- `0x1800bfc6c`
- `0x1800c0678`
- `0x1800c08f8`
- `0x1800ca378`
- `0x1800d7594`
- `0x1800dcef8`
- `0x1800f0794`
- `0x18013fa30`
- `0x180147efc`
- `0x180148890`
- `0x18014ea78`
- `0x18014fd24`
- `0x180159c18`
- `0x18015bfc0`
- `0x18015d078`
- `0x180174230`
- `0x180188448`
- `0x1801bac30`
- `0x1801d52c8`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18002c94b`
- `KERNEL32!InitializeCriticalSection` at `0x18002c94b`
- `KERNEL32!CloseHandle` at `0x18002d6dc`
- `KERNEL32!CloseHandle` at `0x18002d992`
- `KERNEL32!CloseHandle` at `0x18002d6dc`
- `KERNEL32!CloseHandle` at `0x18002d992`
- `KERNEL32!LeaveCriticalSection` at `0x18002dbbf`
- `KERNEL32!LeaveCriticalSection` at `0x18002dbbf`
- `KERNEL32!EnterCriticalSection` at `0x18002db91`
- `KERNEL32!EnterCriticalSection` at `0x18002db91`
- `KERNEL32!GlobalFree` at `0x18002d750`
- `KERNEL32!GlobalFree` at `0x18002daeb`
- `KERNEL32!GlobalFree` at `0x18002dbdd`
- `KERNEL32!GlobalFree` at `0x18002e0a7`
- `KERNEL32!GlobalFree` at `0x18002d750`
- `KERNEL32!GlobalFree` at `0x18002daeb`
- `KERNEL32!GlobalFree` at `0x18002dbdd`
- `KERNEL32!GlobalFree` at `0x18002e0a7`

## string_xrefs

- `0x18002c764`: `Installer\Products`
- `0x18002c57b`: `Entering CMsiConfigurationManager::SetLastUsedSource.`
- `0x18002c6b4`: `Installer\Patches`
- `0x18002d23f`: `Specifed source is%s already in a list.`
- `0x18002d955`: `MSI_LUA: Consent provided to add new source`
- `0x18002da91`: `Warning: rejected attempt to add new source '%s' (product: %s)`

## pseudocode

```c

```
