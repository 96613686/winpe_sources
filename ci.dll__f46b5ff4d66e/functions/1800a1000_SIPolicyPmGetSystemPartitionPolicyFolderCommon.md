# SIPolicyPmGetSystemPartitionPolicyFolderCommon

- ea: `0x1800a1000`
- end: `0x1800a11e2`
- name: `SIPolicyPmGetSystemPartitionPolicyFolderCommon`
- size: `482`
- prototype: `__int64 __fastcall(SYSTEM_INFORMATION_CLASS SystemInformationClass)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007c250`
- `0x1800a0fd0`

## callees

- `0x1800a00c0`
- `0x1800a1000`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a11be`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a11be`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a11a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a11a0`
- `ntoskrnl!ExAllocatePool2` at `0x1800a105b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a10e4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a105b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a10e4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a110f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a112d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a1147`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a1166`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a117f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a110f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a112d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a1147`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a1166`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800a117f`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a1081`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a1081`

## pseudocode

```c

```
