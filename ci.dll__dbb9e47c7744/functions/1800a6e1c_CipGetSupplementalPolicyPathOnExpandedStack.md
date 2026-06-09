# CipGetSupplementalPolicyPathOnExpandedStack

- ea: `0x1800a6e1c`
- end: `0x1800a7025`
- name: `CipGetSupplementalPolicyPathOnExpandedStack`
- size: `521`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, PUNICODE_STRING DestinationString, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800a6df0`

## callees

- `0x18000a980`
- `0x18002c080`
- `0x1800a6e1c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a7014`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a7014`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6e82`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6eef`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6fa5`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6e82`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6eef`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6fa5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6f14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6f14`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6e4f`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6eac`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6e4f`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6eac`

## pseudocode

```c

```
