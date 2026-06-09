# AslpFileGetVersionBlock

- ea: `0x1800c2fec`
- end: `0x1800c3631`
- name: `AslpFileGetVersionBlock`
- size: `1605`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800c2f00`

## callees

- `0x180041774`
- `0x18004281c`
- `0x18006cf6c`
- `0x180075fa0`
- `0x180076e90`
- `0x180076f14`
- `0x180076f20`
- `0x1800c12cc`
- `0x1800c1338`
- `0x1800c2fec`
- `0x1800c4dbc`
- `0x1800c4e04`
- `0x1800c4e74`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x1800c3153`
- `ntdll!LdrResSearchResource` at `0x1800c32c3`
- `ntdll!LdrResSearchResource` at `0x1800c3153`
- `ntdll!LdrResSearchResource` at `0x1800c32c3`
- `ntdll!RtlVerifyVersionInfo` at `0x1800c31f2`
- `ntdll!RtlVerifyVersionInfo` at `0x1800c31f2`
- `ntdll!VerSetConditionMask` at `0x1800c31cf`
- `ntdll!VerSetConditionMask` at `0x1800c31de`
- `ntdll!VerSetConditionMask` at `0x1800c31cf`
- `ntdll!VerSetConditionMask` at `0x1800c31de`
- `ntdll!RtlAllocateHeap` at `0x1800c341a`
- `ntdll!RtlAllocateHeap` at `0x1800c341a`

## string_xrefs

- `0x1800c33f3`: `Version block has bad size (falls outside file)`
- `0x1800c3576`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
