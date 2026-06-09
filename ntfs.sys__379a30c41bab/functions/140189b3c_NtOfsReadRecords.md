# NtOfsReadRecords

- ea: `0x140189b3c`
- end: `0x14018a0b6`
- name: `NtOfsReadRecords`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, int, void *)`
- caller_count: `9`
- callee_count: `9`
- tags: ``

## callers

- `0x1400b6f40`
- `0x1400b8698`
- `0x1400e351c`
- `0x1400e3a70`
- `0x1400e3ed4`
- `0x1400e5dc8`
- `0x140189648`
- `0x140189a08`
- `0x14018a948`

## callees

- `0x140007ea0`
- `0x14000c450`
- `0x140012e70`
- `0x140059440`
- `0x140059740`
- `0x140122780`
- `0x140124490`
- `0x140153960`
- `0x140189b3c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018a04f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018a04f`
- `ntoskrnl!ExReleasePushLockEx` at `0x140189f47`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018a06f`
- `ntoskrnl!ExReleasePushLockEx` at `0x140189f47`
- `ntoskrnl!ExReleasePushLockEx` at `0x14018a06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140189efb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140189efb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140189b8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140189ecf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140189b8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140189ecf`
- `ntoskrnl!CcUnpinData` at `0x140189f8e`
- `ntoskrnl!CcUnpinData` at `0x140189fbc`
- `ntoskrnl!CcUnpinData` at `0x140189fd9`
- `ntoskrnl!CcUnpinData` at `0x140189ff6`
- `ntoskrnl!CcUnpinData` at `0x140189f8e`
- `ntoskrnl!CcUnpinData` at `0x140189fbc`
- `ntoskrnl!CcUnpinData` at `0x140189fd9`
- `ntoskrnl!CcUnpinData` at `0x140189ff6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a094`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a094`

## pseudocode

```c

```
