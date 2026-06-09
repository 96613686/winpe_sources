# AslRegistryBuildMachinePath

- ea: `0x180167a40`
- end: `0x180167b1f`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180167b28`

## callees

- `0x18016796c`
- `0x180167a40`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180167b00`
- `ntdll!RtlAppendUnicodeToString` at `0x180167b0c`
- `ntdll!RtlAppendUnicodeToString` at `0x180167b00`
- `ntdll!RtlAppendUnicodeToString` at `0x180167b0c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180167ae5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180167ae5`
- `ntdll!RtlAllocateHeap` at `0x180167aa4`
- `ntdll!RtlAllocateHeap` at `0x180167aa4`
- `ntdll!RtlInitUnicodeString` at `0x180167a63`
- `ntdll!RtlInitUnicodeString` at `0x180167a63`

## string_xrefs

- `0x180167ac8`: `AslRegistryBuildMachinePath`
- `0x180167a52`: `\Registry\Machine`

## pseudocode

```c

```
