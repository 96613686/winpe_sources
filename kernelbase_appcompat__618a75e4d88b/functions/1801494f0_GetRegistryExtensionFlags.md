# GetRegistryExtensionFlags

- ea: `0x1801494f0`
- end: `0x180149668`
- name: `GetRegistryExtensionFlags`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1801494f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180149532`
- `ntdll!RtlInitUnicodeString` at `0x1801495c8`
- `ntdll!RtlInitUnicodeString` at `0x180149532`
- `ntdll!RtlInitUnicodeString` at `0x1801495c8`
- `ntdll!NtOpenKey` at `0x180149571`
- `ntdll!NtOpenKey` at `0x180149571`
- `ntdll!NtQueryValueKey` at `0x1801495f5`
- `ntdll!NtQueryValueKey` at `0x1801495f5`
- `ntdll!NtClose` at `0x180149648`
- `ntdll!NtClose` at `0x180149648`
- `ntdll!RtlFreeHeap` at `0x18014961a`
- `ntdll!RtlFreeHeap` at `0x18014961a`
- `ntdll!RtlAllocateHeap` at `0x1801495a5`
- `ntdll!RtlAllocateHeap` at `0x1801495a5`

## string_xrefs

- `0x180149508`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Terminal Server`
- `0x1801495bd`: `RegistryExtensionFlags`

## pseudocode

```c

```
