# CIptPlugin::InitializeForUserModeApp(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x180033198`
- end: `0x180033517`
- name: `?InitializeForUserModeApp@CIptPlugin@@AEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(wchar_t **this, struct WER_PLUGIN_INIT_IN *, __int64, HINSTANCE)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180033020`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x18000aa54`
- `0x180024bc4`
- `0x180033198`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003327a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003327a`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x18003336e`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x18003340d`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x18003336e`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFamilyName` at `0x18003340d`

## pseudocode

```c

```
