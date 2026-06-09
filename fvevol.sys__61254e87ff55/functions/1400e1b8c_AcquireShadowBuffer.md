# AcquireShadowBuffer

- ea: `0x1400e1b8c`
- end: `0x1400e1c80`
- name: `AcquireShadowBuffer`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400eb300`

## callees

- `0x1400089c4`
- `0x1400e1b8c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e1bcc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400e1bcc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e1c63`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e1c63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400e1c2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400e1c2b`
- `ntoskrnl!ExAllocatePool2` at `0x1400e1c10`
- `ntoskrnl!ExAllocatePool2` at `0x1400e1c10`

## pseudocode

```c

```
