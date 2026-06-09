# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetConfigurationTimestamp(_SYSTEMTIME *)

- ea: `0x140008970`
- end: `0x140008b0f`
- name: `?GetConfigurationTimestamp@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@UEBAJPEAU_SYSTEMTIME@@@Z`
- size: `415`
- prototype: `int(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002618`
- `0x140002c10`
- `0x140007740`
- `0x140008970`
- `0x140008b10`
- `0x140033ab0`
- `0x140046514`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x140008a94`
- `KERNEL32!FileTimeToSystemTime` at `0x140008a94`
- `KERNEL32!GetLastError` at `0x140008a9e`
- `KERNEL32!GetLastError` at `0x140008a9e`

## string_xrefs

- `0x140008a07`: `ExtensionManager\EnabledExtensions`
- `0x14000899e`: `Invalid argument to GetConfigurationTimestamp`

## pseudocode

```c

```
