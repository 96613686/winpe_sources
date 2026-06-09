# SmbCeGetPortFromPolicyServerTransportPortMappings

- ea: `0x140043e0c`
- end: `0x1400440dc`
- name: `SmbCeGetPortFromPolicyServerTransportPortMappings`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140043670`

## callees

- `0x14003838c`
- `0x140039fa8`
- `0x140043e0c`
- `0x14004d28c`
- `0x140059ea0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x140043eab`
- `ntoskrnl!_wcsnicmp` at `0x140043fae`
- `ntoskrnl!_wcsnicmp` at `0x140043ff3`
- `ntoskrnl!_wcsnicmp` at `0x140043fae`
- `ntoskrnl!_wcsnicmp` at `0x140043ff3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400440b9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400440b9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043e8c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043e8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043e7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043e7c`

## string_xrefs

- `0x140043e59`: `RtlQueryRegistryValuesEx`
- `0x140043ea4`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`

## pseudocode

```c

```
