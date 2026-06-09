# SmbCeGetPortFromRegistryServerTransportPortMappings

- ea: `0x1400440e4`
- end: `0x140044419`
- name: `SmbCeGetPortFromRegistryServerTransportPortMappings`
- size: `821`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140043670`

## callees

- `0x1400397b4`
- `0x14003a02c`
- `0x1400440e4`
- `0x140044fd0`
- `0x1400450c0`
- `0x1400452a8`
- `0x1400924c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400441c2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004422d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004427d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400441c2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004422d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004427d`
- `ntoskrnl!ExAllocatePool2` at `0x14004419c`
- `ntoskrnl!ExAllocatePool2` at `0x14004419c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400443f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400443f1`

## string_xrefs

- `0x1400442ed`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkstation\AlternativePorts`

## pseudocode

```c

```
