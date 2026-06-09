# AslRegistryBuildMachinePath

- ea: `0x180066e0c`
- end: `0x180066eeb`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180066ef4`

## callees

- `0x180066c10`
- `0x180066e0c`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x180066eb1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180066eb1`
- `ntdll!RtlAllocateHeap` at `0x180066e70`
- `ntdll!RtlAllocateHeap` at `0x180066e70`
- `ntdll!RtlInitUnicodeString` at `0x180066e2f`
- `ntdll!RtlInitUnicodeString` at `0x180066e2f`
- `ntdll!RtlAppendUnicodeToString` at `0x180066ecc`
- `ntdll!RtlAppendUnicodeToString` at `0x180066ed8`
- `ntdll!RtlAppendUnicodeToString` at `0x180066ecc`
- `ntdll!RtlAppendUnicodeToString` at `0x180066ed8`

## string_xrefs

- `0x180066e1e`: `\Registry\Machine`
- `0x180066e94`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
