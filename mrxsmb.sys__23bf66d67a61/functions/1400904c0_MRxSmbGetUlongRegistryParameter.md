# MRxSmbGetUlongRegistryParameter

- ea: `0x1400904c0`
- end: `0x140090575`
- name: `MRxSmbGetUlongRegistryParameter`
- size: `181`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140020540`
- `0x140020930`
- `0x140028fec`
- `0x14003bc54`

## callees

- `0x140059dc0`
- `0x1400904c0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14009052b`
- `ntoskrnl!ZwQueryValueKey` at `0x14009052b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400904fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400904fa`

## pseudocode

```c

```
