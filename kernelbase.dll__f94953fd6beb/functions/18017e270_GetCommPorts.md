# GetCommPorts

- ea: `0x18017e270`
- end: `0x18017e4ff`
- name: `GetCommPorts`
- size: `655`
- prototype: `ULONG __stdcall(PULONG lpPortNumbers, ULONG uPortNumbersCount, PULONG puPortNumbersFound)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x18017e270`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18017e2fd`
- `ntdll!NtOpenKey` at `0x18017e2fd`
- `ntdll!NtEnumerateValueKey` at `0x18017e375`
- `ntdll!NtEnumerateValueKey` at `0x18017e375`
- `ntdll!NtClose` at `0x18017e4ba`
- `ntdll!NtClose` at `0x18017e4ba`
- `ntdll!RtlPrefixUnicodeString` at `0x18017e402`
- `ntdll!RtlPrefixUnicodeString` at `0x18017e402`
- `ntdll!RtlFreeHeap` at `0x18017e3a1`
- `ntdll!RtlFreeHeap` at `0x18017e4d7`
- `ntdll!RtlFreeHeap` at `0x18017e3a1`
- `ntdll!RtlFreeHeap` at `0x18017e4d7`
- `ntdll!RtlAllocateHeap` at `0x18017e344`
- `ntdll!RtlAllocateHeap` at `0x18017e344`

## string_xrefs

- `0x18017e297`: `\Registry\MACHINE\Hardware\DeviceMap\SERIALCOMM`

## pseudocode

```c

```
