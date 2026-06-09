# NatUnloadDriver

- ea: `0x180037ed4`
- end: `0x180037f3e`
- name: `NatUnloadDriver`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180037d80`

## callees

- `0x180037ed4`
- `0x18004b9e8`
- `0x180057374`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180037f0b`
- `ntdll!RtlInitUnicodeString` at `0x180037f0b`
- `ntdll!RtlNtStatusToDosError` at `0x180037f2e`
- `ntdll!RtlNtStatusToDosError` at `0x180037f2e`
- `ntdll!NtUnloadDriver` at `0x180037f16`
- `ntdll!NtUnloadDriver` at `0x180037f16`

## string_xrefs

- `0x180037eff`: `\Registry\Machine\System\CurrentControlSet\Services\IPNAT`

## pseudocode

```c

```
