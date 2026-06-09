# AslRegistryGetString

- ea: `0x18001ce60`
- end: `0x18001d035`
- name: `AslRegistryGetString`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ada8`
- `0x18001b710`

## callees

- `0x18001ce60`
- `0x18001d03c`
- `0x180035ea4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001ce88`
- `ntdll!RtlInitUnicodeString` at `0x18001ce88`
- `ntdll!RtlAllocateHeap` at `0x18001cee0`
- `ntdll!RtlAllocateHeap` at `0x18001cee0`
- `ntdll!RtlFreeHeap` at `0x18001cf65`
- `ntdll!RtlFreeHeap` at `0x18001cf65`
- `ntdll!ZwQueryValueKey` at `0x18001cead`
- `ntdll!ZwQueryValueKey` at `0x18001cf15`
- `ntdll!ZwQueryValueKey` at `0x18001cead`
- `ntdll!ZwQueryValueKey` at `0x18001cf15`

## string_xrefs

- `0x18001cf80`: `AslRegistryGetString`
- `0x18001cfbf`: `AslRegistryGetString`
- `0x18001cff5`: `AslRegistryGetString`
- `0x18001d01a`: `AslRegistryGetString`

## pseudocode

```c

```
