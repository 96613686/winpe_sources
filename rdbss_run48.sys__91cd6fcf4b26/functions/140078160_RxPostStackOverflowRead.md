# RxPostStackOverflowRead

- ea: `0x140078160`
- end: `0x140078270`
- name: `RxPostStackOverflowRead`
- size: `272`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, PFCB Fcb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015290`

## callees

- `0x140017280`
- `0x140017540`
- `0x140078160`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400781c2`
- `ntoskrnl!KeInitializeEvent` at `0x1400781c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078249`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b9f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078249`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007b9f0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400781f0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400781f0`
- `ntoskrnl!FsRtlPostStackOverflow` at `0x140078217`
- `ntoskrnl!FsRtlPostStackOverflow` at `0x140078217`
- `ntoskrnl!KeWaitForSingleObject` at `0x140078239`
- `ntoskrnl!KeWaitForSingleObject` at `0x140078239`

## pseudocode

```c

```
