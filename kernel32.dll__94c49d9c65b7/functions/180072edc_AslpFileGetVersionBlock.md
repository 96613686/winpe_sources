# AslpFileGetVersionBlock

- ea: `0x180072edc`
- end: `0x180073521`
- name: `AslpFileGetVersionBlock`
- size: `1605`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180072df0`

## callees

- `0x180021144`
- `0x1800212e4`
- `0x180022088`
- `0x18004f918`
- `0x18005c390`
- `0x18005c3a8`
- `0x180071908`
- `0x180072edc`
- `0x18007499c`
- `0x1800749e4`
- `0x180074a54`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x180073043`
- `ntdll!LdrResSearchResource` at `0x1800731b3`
- `ntdll!LdrResSearchResource` at `0x180073043`
- `ntdll!LdrResSearchResource` at `0x1800731b3`
- `ntdll!VerSetConditionMask` at `0x1800730bf`
- `ntdll!VerSetConditionMask` at `0x1800730ce`
- `ntdll!VerSetConditionMask` at `0x1800730bf`
- `ntdll!VerSetConditionMask` at `0x1800730ce`
- `ntdll!RtlVerifyVersionInfo` at `0x1800730e2`
- `ntdll!RtlVerifyVersionInfo` at `0x1800730e2`
- `ntdll!RtlAllocateHeap` at `0x18007330a`
- `ntdll!RtlAllocateHeap` at `0x18007330a`

## string_xrefs

- `0x1800732e3`: `Version block has bad size (falls outside file)`
- `0x180073466`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
