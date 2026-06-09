# FltpAttachPolicyGetRegValue

- ea: `0x180020690`
- end: `0x18002073e`
- name: `FltpAttachPolicyGetRegValue`
- size: `174`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020600`
- `0x180020750`

## callees

- `0x180024880`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800206ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800206ee`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800206ff`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800206ff`
- `ntoskrnl!RtlQueryRegistryValues` at `0x180020721`

## string_xrefs

- `0x1800206c1`: `RtlQueryRegistryValuesEx`

## pseudocode

```c

```
