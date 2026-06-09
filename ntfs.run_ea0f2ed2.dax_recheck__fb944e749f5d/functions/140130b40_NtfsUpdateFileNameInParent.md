# NtfsUpdateFileNameInParent

- ea: `0x140130b40`
- end: `0x14013160f`
- name: `NtfsUpdateFileNameInParent`
- size: `2767`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, char, char)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1400ee960`
- `0x140130550`
- `0x1402864ec`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400410a8`
- `0x140059250`
- `0x1400596c0`
- `0x140059be0`
- `0x1401250b0`
- `0x1401261d0`
- `0x140130b40`
- `0x140131620`
- `0x14014dde0`
- `0x1401620c0`
- `0x140188028`
- `0x140188ce4`
- `0x14018c44c`
- `0x1401e0660`
- `0x140279c44`
- `0x140288010`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401311c7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401311c7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401311eb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401311eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140131497`
- `ntoskrnl!ExFreePoolWithTag` at `0x140131497`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140130dd6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140130dd6`
- `ntoskrnl!CcUnpinData` at `0x140131543`
- `ntoskrnl!CcUnpinData` at `0x140131568`
- `ntoskrnl!CcUnpinData` at `0x14013158d`
- `ntoskrnl!CcUnpinData` at `0x140131543`
- `ntoskrnl!CcUnpinData` at `0x140131568`
- `ntoskrnl!CcUnpinData` at `0x14013158d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130e70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130edc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401315ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a6213`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130e70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130edc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401315ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a6213`

## pseudocode

```c

```
