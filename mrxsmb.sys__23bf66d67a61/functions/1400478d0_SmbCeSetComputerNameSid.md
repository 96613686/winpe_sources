# SmbCeSetComputerNameSid

- ea: `0x1400478d0`
- end: `0x140047b4f`
- name: `SmbCeSetComputerNameSid`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400302f0`

## callees

- `0x14003838c`
- `0x140039fd8`
- `0x1400478d0`
- `0x14004f4fc`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400479c1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400479f1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400479c1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400479f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400479a9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400479d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400479a9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400479d9`
- `ntoskrnl!ExAllocatePool2` at `0x140047974`
- `ntoskrnl!ExAllocatePool2` at `0x140047974`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140047a06`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140047b17`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140047a06`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140047b17`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140047939`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140047939`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b00`
- `ksecdd!SecLookupAccountName` at `0x140047a53`
- `ksecdd!SecLookupAccountName` at `0x140047a53`

## pseudocode

```c

```
