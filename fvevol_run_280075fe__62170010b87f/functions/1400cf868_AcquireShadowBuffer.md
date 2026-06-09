# AcquireShadowBuffer

- ea: `0x1400cf868`
- end: `0x1400cf95c`
- name: `AcquireShadowBuffer`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400cee94`

## callees

- `0x140008904`
- `0x1400cf868`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf8a8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400cf8a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf93f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf93f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf907`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf907`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf8ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400cf8ec`

## pseudocode

```c

```
