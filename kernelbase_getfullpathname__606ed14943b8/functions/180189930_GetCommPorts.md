# GetCommPorts

- ea: `0x180189930`
- end: `0x180189bea`
- name: `GetCommPorts`
- size: `698`
- prototype: `ULONG __stdcall(PULONG lpPortNumbers, ULONG uPortNumbersCount, PULONG puPortNumbersFound)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x180189930`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1801899bd`
- `ntdll!NtOpenKey` at `0x1801899bd`
- `ntdll!NtEnumerateValueKey` at `0x180189a41`
- `ntdll!NtEnumerateValueKey` at `0x180189a41`
- `ntdll!NtClose` at `0x180189b98`
- `ntdll!NtClose` at `0x180189b98`
- `ntdll!RtlPrefixUnicodeString` at `0x180189ada`
- `ntdll!RtlPrefixUnicodeString` at `0x180189ada`
- `ntdll!RtlFreeHeap` at `0x180189a73`
- `ntdll!RtlFreeHeap` at `0x180189bbb`
- `ntdll!RtlFreeHeap` at `0x180189a73`
- `ntdll!RtlFreeHeap` at `0x180189bbb`
- `ntdll!RtlAllocateHeap` at `0x180189a0a`
- `ntdll!RtlAllocateHeap` at `0x180189a0a`

## string_xrefs

- `0x180189957`: `\Registry\MACHINE\Hardware\DeviceMap\SERIALCOMM`

## pseudocode

```c

```
