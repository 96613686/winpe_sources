# CipGetSupplementalPolicyPathOnExpandedStack

- ea: `0x1800a57ec`
- end: `0x1800a59f5`
- name: `CipGetSupplementalPolicyPathOnExpandedStack`
- size: `521`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, PUNICODE_STRING DestinationString, PUNICODE_STRING UnicodeString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800a57c0`

## callees

- `0x18000a980`
- `0x18002c040`
- `0x1800a57ec`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a59e4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a59e4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5852`
- `ntoskrnl!ExAllocatePool2` at `0x1800a58bf`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5975`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5852`
- `ntoskrnl!ExAllocatePool2` at `0x1800a58bf`
- `ntoskrnl!ExAllocatePool2` at `0x1800a5975`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a58e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a58e4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a581f`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a587c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a581f`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a587c`

## pseudocode

```c

```
