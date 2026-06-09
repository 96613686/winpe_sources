# TxfCheckForLockConflict

- ea: `0x1401e4170`
- end: `0x1401e4dc0`
- name: `TxfCheckForLockConflict`
- size: `3152`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1401842cc`
- `0x140221e50`
- `0x140227568`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14003ba34`
- `0x14003f358`
- `0x14003f52c`
- `0x140188f30`
- `0x1401e4170`
- `0x140201430`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1401e4d64`
- `ntoskrnl!ExQueueWorkItem` at `0x1401e4d64`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1401e43dc`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1401e43dc`
- `ntoskrnl!DbgPrintEx` at `0x1401e4d50`
- `ntoskrnl!DbgPrintEx` at `0x1401e4d50`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4297`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4311`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e460b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4297`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e4311`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401e460b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4b65`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4cae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4cc6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b10c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b10da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4b65`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4cae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e4cc6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b10c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b10da`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401e44ac`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401e44ac`

## string_xrefs

- `0x1401e4d42`: `Closing PosixDeleteHandle, FCB=0x%p\n`

## pseudocode

```c

```
