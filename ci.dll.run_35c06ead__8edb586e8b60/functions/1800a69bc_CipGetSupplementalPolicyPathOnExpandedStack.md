# CipGetSupplementalPolicyPathOnExpandedStack

- ea: `0x1800a69bc`
- end: `0x1800a6bc5`
- name: `CipGetSupplementalPolicyPathOnExpandedStack`
- size: `521`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, PUNICODE_STRING DestinationString, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800a6990`

## callees

- `0x18000a990`
- `0x18002c200`
- `0x1800a69bc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a6bb4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a6bb4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6a22`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6a8f`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6b45`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6a22`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6a8f`
- `ntoskrnl!ExAllocatePool2` at `0x1800a6b45`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a6ab4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a69ef`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6a4c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a69ef`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a6a4c`

## pseudocode

```c

```
