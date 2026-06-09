# AslpFileGetVersionBlock

- ea: `0x18006feb0`
- end: `0x1800705de`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006fcbc`

## callees

- `0x180005e40`
- `0x180006e04`
- `0x180006eb8`
- `0x180006ec4`
- `0x180066c10`
- `0x18006d524`
- `0x18006db9c`
- `0x18006feb0`
- `0x180071e74`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x180070023`
- `ntdll!LdrResSearchResource` at `0x180070196`
- `ntdll!LdrResSearchResource` at `0x180070023`
- `ntdll!LdrResSearchResource` at `0x180070196`
- `ntdll!ZwUnmapViewOfSection` at `0x180070596`
- `ntdll!ZwUnmapViewOfSection` at `0x180070596`
- `ntdll!ZwClose` at `0x180070575`
- `ntdll!ZwClose` at `0x1800705b3`
- `ntdll!ZwClose` at `0x180070575`
- `ntdll!ZwClose` at `0x1800705b3`
- `ntdll!RtlVerifyVersionInfo` at `0x1800700c4`
- `ntdll!RtlVerifyVersionInfo` at `0x1800700c4`
- `ntdll!VerSetConditionMask` at `0x1800700a2`
- `ntdll!VerSetConditionMask` at `0x1800700b1`
- `ntdll!VerSetConditionMask` at `0x1800700a2`
- `ntdll!VerSetConditionMask` at `0x1800700b1`
- `ntdll!RtlAllocateHeap` at `0x18007031a`
- `ntdll!RtlAllocateHeap` at `0x18007031a`
- `ntdll!RtlFreeHeap` at `0x180070558`
- `ntdll!RtlFreeHeap` at `0x180070558`

## string_xrefs

- `0x1800704e1`: `Version block has bad size (falls outside file)`
- `0x1800704b3`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
