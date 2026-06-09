# AslRegistryBuildMachinePath

- ea: `0x180041ab0`
- end: `0x180041b91`
- name: `AslRegistryBuildMachinePath`
- size: `225`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800419a0`

## callees

- `0x180041ab0`
- `0x18004281c`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180041b6f`
- `ntdll!RtlAppendUnicodeToString` at `0x180041b89`
- `ntdll!RtlAppendUnicodeToString` at `0x180041b6f`
- `ntdll!RtlAppendUnicodeToString` at `0x180041b89`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180041b5e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180041b5e`
- `ntdll!RtlInitUnicodeString` at `0x180041ad3`
- `ntdll!RtlInitUnicodeString` at `0x180041ad3`
- `ntdll!RtlAllocateHeap` at `0x180041b14`
- `ntdll!RtlAllocateHeap` at `0x180041b14`

## string_xrefs

- `0x180041ac2`: `\Registry\Machine`
- `0x180041b38`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
