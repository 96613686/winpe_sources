# TxfCheckForLockConflict

- ea: `0x1401e4120`
- end: `0x1401e4d70`
- name: `TxfCheckForLockConflict`
- size: `3152`
- prototype: `__int64 __fastcall(__int64, __int64, volatile signed __int32 *, int, char, char, char)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14018427c`
- `0x140221e00`
- `0x140227518`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14003ba34`
- `0x14003f358`
- `0x14003f52c`
- `0x140188ee0`
- `0x1401e4120`
- `0x1402013e0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1401e4d14`
- `ntoskrnl!ExQueueWorkItem` at `0x1401e4d14`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1401e438c`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1401e438c`
- `ntoskrnl!DbgPrintEx` at `0x1401e4d00`
- `ntoskrnl!DbgPrintEx` at `0x1401e4d00`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4247`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e42c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e45bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4247`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e42c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e45bb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4b15`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4c5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4c76`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1070`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b108a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4b15`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4c5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4c76`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1070`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b108a`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401e445c`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401e445c`

## string_xrefs

- `0x1401e4cf2`: `Closing PosixDeleteHandle, FCB=0x%p\n`

## pseudocode

```c

```
