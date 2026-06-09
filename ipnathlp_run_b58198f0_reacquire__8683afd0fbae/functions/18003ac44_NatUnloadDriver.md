# NatUnloadDriver

- ea: `0x18003ac44`
- end: `0x18003acc1`
- name: `NatUnloadDriver`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18003aad0`

## callees

- `0x18003ac44`
- `0x18004f634`
- `0x18005b83c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003ac7b`
- `ntdll!RtlInitUnicodeString` at `0x18003ac7b`
- `ntdll!RtlNtStatusToDosError` at `0x18003acaa`
- `ntdll!RtlNtStatusToDosError` at `0x18003acaa`
- `ntdll!NtUnloadDriver` at `0x18003ac8c`
- `ntdll!NtUnloadDriver` at `0x18003ac8c`

## string_xrefs

- `0x18003ac6f`: `\Registry\Machine\System\CurrentControlSet\Services\IPNAT`

## pseudocode

```c

```
