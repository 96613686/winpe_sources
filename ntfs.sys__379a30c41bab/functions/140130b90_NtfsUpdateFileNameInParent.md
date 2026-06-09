# NtfsUpdateFileNameInParent

- ea: `0x140130b90`
- end: `0x14013165f`
- name: `NtfsUpdateFileNameInParent`
- size: `2767`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, char, char)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1400ee9b0`
- `0x1401305a0`
- `0x14028653c`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400410a8`
- `0x1400592c0`
- `0x140059740`
- `0x140059c60`
- `0x140125100`
- `0x140126220`
- `0x140130b90`
- `0x140131670`
- `0x14014de30`
- `0x140162110`
- `0x140188078`
- `0x140188d34`
- `0x14018c49c`
- `0x1401e06b0`
- `0x140279c94`
- `0x140288060`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140131217`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140131217`
- `ntoskrnl!ExReleasePushLockEx` at `0x14013123b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14013123b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401314e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401314e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140130e26`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140130e26`
- `ntoskrnl!CcUnpinData` at `0x140131593`
- `ntoskrnl!CcUnpinData` at `0x1401315b8`
- `ntoskrnl!CcUnpinData` at `0x1401315dd`
- `ntoskrnl!CcUnpinData` at `0x140131593`
- `ntoskrnl!CcUnpinData` at `0x1401315b8`
- `ntoskrnl!CcUnpinData` at `0x1401315dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130ec0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130f2c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013161e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a6263`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130ec0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140130f2c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013161e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a6263`

## pseudocode

```c

```
