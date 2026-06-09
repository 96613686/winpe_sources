# AslRegistryGetString

- ea: `0x180020db0`
- end: `0x180020fa4`
- name: `AslRegistryGetString`
- size: `500`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ec90`
- `0x18001f680`

## callees

- `0x180020db0`
- `0x180020fac`
- `0x180036388`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180020dd8`
- `ntdll!RtlInitUnicodeString` at `0x180020dd8`
- `ntdll!RtlAllocateHeap` at `0x180020e3c`
- `ntdll!RtlAllocateHeap` at `0x180020e3c`
- `ntdll!RtlFreeHeap` at `0x180020ecd`
- `ntdll!RtlFreeHeap` at `0x180020ecd`
- `ntdll!ZwQueryValueKey` at `0x180020e03`
- `ntdll!ZwQueryValueKey` at `0x180020e77`
- `ntdll!ZwQueryValueKey` at `0x180020e03`
- `ntdll!ZwQueryValueKey` at `0x180020e77`

## string_xrefs

- `0x180020eee`: `AslRegistryGetString`
- `0x180020f2e`: `AslRegistryGetString`
- `0x180020f64`: `AslRegistryGetString`
- `0x180020f89`: `AslRegistryGetString`

## pseudocode

```c

```
