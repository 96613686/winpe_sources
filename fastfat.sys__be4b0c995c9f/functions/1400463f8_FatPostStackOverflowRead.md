# FatPostStackOverflowRead

- ea: `0x1400463f8`
- end: `0x1400464f8`
- name: `FatPostStackOverflowRead`
- size: `256`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006030`

## callees

- `0x140007440`
- `0x1400463f8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140046424`
- `ntoskrnl!KeInitializeEvent` at `0x140046424`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400464c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400464c7`
- `ntoskrnl!FsRtlPostStackOverflow` at `0x1400464a5`
- `ntoskrnl!FsRtlPostStackOverflow` at `0x1400464a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400464dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f7f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400464dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f7f5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140046457`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140046457`

## pseudocode

```c

```
