# AslRegistryBuildMachinePath

- ea: `0x18002167c`
- end: `0x18002175b`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180021764`

## callees

- `0x1800212e4`
- `0x18002167c`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180021745`
- `ntdll!RtlAppendUnicodeToString` at `0x180021751`
- `ntdll!RtlAppendUnicodeToString` at `0x180021745`
- `ntdll!RtlAppendUnicodeToString` at `0x180021751`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002172a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002172a`
- `ntdll!RtlInitUnicodeString` at `0x18002169f`
- `ntdll!RtlInitUnicodeString` at `0x18002169f`
- `ntdll!RtlAllocateHeap` at `0x1800216e0`
- `ntdll!RtlAllocateHeap` at `0x1800216e0`

## string_xrefs

- `0x18002168e`: `\Registry\Machine`
- `0x180021704`: `AslRegistryBuildMachinePath`

## pseudocode

```c

```
