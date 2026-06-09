# AslpFileGetVersionBlock

- ea: `0x18007abbc`
- end: `0x18007b226`
- name: `AslpFileGetVersionBlock`
- size: `1642`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007aacc`

## callees

- `0x18001ef8c`
- `0x18001f138`
- `0x18001ff34`
- `0x180054934`
- `0x180061d70`
- `0x180061d88`
- `0x1800795bc`
- `0x18007abbc`
- `0x18007c6b4`
- `0x18007c6fc`
- `0x18007c770`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x18007ad23`
- `ntdll!LdrResSearchResource` at `0x18007aeab`
- `ntdll!LdrResSearchResource` at `0x18007ad23`
- `ntdll!LdrResSearchResource` at `0x18007aeab`
- `ntdll!VerSetConditionMask` at `0x18007ada5`
- `ntdll!VerSetConditionMask` at `0x18007adba`
- `ntdll!VerSetConditionMask` at `0x18007ada5`
- `ntdll!VerSetConditionMask` at `0x18007adba`
- `ntdll!RtlVerifyVersionInfo` at `0x18007add4`
- `ntdll!RtlVerifyVersionInfo` at `0x18007add4`
- `ntdll!RtlAllocateHeap` at `0x18007b008`
- `ntdll!RtlAllocateHeap` at `0x18007b008`

## string_xrefs

- `0x18007afe1`: `Version block has bad size (falls outside file)`
- `0x18007b16a`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c

```
