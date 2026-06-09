# AslRegistryBuildMachinePath

- ea: `0x18001f4e8`
- end: `0x18001f5e6`
- name: `AslRegistryBuildMachinePath`
- size: `254`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f5ec`

## callees

- `0x18001f138`
- `0x18001f4e8`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18001f5c4`
- `ntdll!RtlAppendUnicodeToString` at `0x18001f5d6`
- `ntdll!RtlAppendUnicodeToString` at `0x18001f5c4`
- `ntdll!RtlAppendUnicodeToString` at `0x18001f5d6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001f5a3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001f5a3`
- `ntdll!RtlInitUnicodeString` at `0x18001f50b`
- `ntdll!RtlInitUnicodeString` at `0x18001f50b`
- `ntdll!RtlAllocateHeap` at `0x18001f552`
- `ntdll!RtlAllocateHeap` at `0x18001f552`

## string_xrefs

- `0x18001f4fa`: `\Registry\Machine`
- `0x18001f57c`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
