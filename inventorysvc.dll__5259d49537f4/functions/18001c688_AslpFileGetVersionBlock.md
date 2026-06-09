# AslpFileGetVersionBlock

- ea: `0x18001c688`
- end: `0x18001cdb6`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001c494`

## callees

- `0x180002bf0`
- `0x180003804`
- `0x1800038b8`
- `0x180005483`
- `0x1800152d0`
- `0x18001a0f0`
- `0x18001a768`
- `0x18001c688`
- `0x18001e64c`

## import_xrefs

- `ntdll!ZwClose` at `0x18001cd4d`
- `ntdll!ZwClose` at `0x18001cd8b`
- `ntdll!ZwClose` at `0x18001cd4d`
- `ntdll!ZwClose` at `0x18001cd8b`
- `ntdll!RtlFreeHeap` at `0x18001cd30`
- `ntdll!RtlFreeHeap` at `0x18001cd30`
- `ntdll!RtlAllocateHeap` at `0x18001caf2`
- `ntdll!RtlAllocateHeap` at `0x18001caf2`
- `ntdll!ZwUnmapViewOfSection` at `0x18001cd6e`
- `ntdll!ZwUnmapViewOfSection` at `0x18001cd6e`
- `ntdll!LdrResSearchResource` at `0x18001c7fb`
- `ntdll!LdrResSearchResource` at `0x18001c96e`
- `ntdll!LdrResSearchResource` at `0x18001c7fb`
- `ntdll!LdrResSearchResource` at `0x18001c96e`
- `ntdll!RtlVerifyVersionInfo` at `0x18001c89c`
- `ntdll!RtlVerifyVersionInfo` at `0x18001c89c`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18001c87a`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18001c889`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18001c87a`
- `api-ms-win-core-sysinfo-l1-2-0!VerSetConditionMask` at `0x18001c889`

## string_xrefs

- `0x18001ccb9`: `Version block has bad size (falls outside file)`
- `0x18001cc8b`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
