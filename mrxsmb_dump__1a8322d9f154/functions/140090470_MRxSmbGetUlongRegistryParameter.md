# MRxSmbGetUlongRegistryParameter

- ea: `0x140090470`
- end: `0x140090525`
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
- `0x140090470`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400904db`
- `ntoskrnl!ZwQueryValueKey` at `0x1400904db`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400904aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400904aa`

## pseudocode

```c

```
