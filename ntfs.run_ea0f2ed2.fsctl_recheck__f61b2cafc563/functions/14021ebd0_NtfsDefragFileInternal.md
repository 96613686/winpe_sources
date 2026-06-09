# NtfsDefragFileInternal

- ea: `0x14021ebd0`
- end: `0x140220b33`
- name: `NtfsDefragFileInternal`
- size: `8035`
- prototype: `__int64 __usercall@<rax>(PVOID Context1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `53`
- tags: ``

## callers

- `0x14022c00c`

## callees

- `0x1400055f0`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000e220`
- `0x1400100b0`
- `0x140010be0`
- `0x140012e70`
- `0x140015b90`
- `0x14001d8f0`
- `0x14001e2f0`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x14002b680`
- `0x140030850`
- `0x14003e5b4`
- `0x14004062c`
- `0x1400410a8`
- `0x140059250`
- `0x140123170`
- `0x1401241a0`
- `0x1401250b0`
- `0x140137c60`
- `0x140140380`
- `0x140159768`
- `0x140160250`
- `0x140160e90`
- `0x140173db0`
- `0x140175220`
- `0x140176e60`
- `0x1401aab20`
- `0x1401be398`
- `0x1401c00e0`
- `0x1401cfc18`
- `0x1401d24d8`
- `0x1401d2c34`
- `0x1401d2cec`
- `0x1401e0660`
- `0x140209910`
- `0x14020f350`
- `0x14021aa20`
- `0x14021ebd0`
- `0x14022888c`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14021f623`
- `ntoskrnl!IoAllocateMdl` at `0x14021f623`
- `ntoskrnl!IoFreeMdl` at `0x14022083e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5a7d`
- `ntoskrnl!IoFreeMdl` at `0x14022083e`
- `ntoskrnl!IoFreeMdl` at `0x1402b5a7d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14021f63f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14021f63f`
- `ntoskrnl!MmMdlPageContentsState` at `0x14021f658`
- `ntoskrnl!MmMdlPageContentsState` at `0x14021f658`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14021f34c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14021f34c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402206fd`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5987`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402206fd`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402b5987`
- `ntoskrnl!KeClearEvent` at `0x14021f89a`
- `ntoskrnl!KeClearEvent` at `0x14021f89a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021ef50`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021f8e3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021ef50`
- `ntoskrnl!KeWaitForSingleObject` at `0x14021f8e3`
- `ntoskrnl!KeInitializeEvent` at `0x14021ee63`
- `ntoskrnl!KeInitializeEvent` at `0x14021ee63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021f66e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14022084f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402208a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5b00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021f66e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14022084f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402208a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b5b00`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021ee41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021f5ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021ee41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14021f5ea`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f871`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f9bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fb18`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fcb7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b56ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f871`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021f9bf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fb18`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14021fcb7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b56ac`
- `ntoskrnl!CcUnpinData` at `0x1402207bf`
- `ntoskrnl!CcUnpinData` at `0x1402207e4`
- `ntoskrnl!CcUnpinData` at `0x140220809`
- `ntoskrnl!CcUnpinData` at `0x1402207bf`
- `ntoskrnl!CcUnpinData` at `0x1402207e4`
- `ntoskrnl!CcUnpinData` at `0x140220809`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f8b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f9da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140220742`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b56c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b59cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f8b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14021f9da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140220742`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b56c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b59cb`
- `ntoskrnl!CcFlushCache` at `0x14021fee1`
- `ntoskrnl!CcFlushCache` at `0x14021fee1`

## pseudocode

```c

```
