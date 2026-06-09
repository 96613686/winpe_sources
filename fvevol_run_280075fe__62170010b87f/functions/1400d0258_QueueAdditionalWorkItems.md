# QueueAdditionalWorkItems

- ea: `0x1400d0258`
- end: `0x1400d0565`
- name: `QueueAdditionalWorkItems`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400d6d48`

## callees

- `0x1400d0258`
- `0x1400d0570`
- `0x1400d1820`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400d0520`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400d0520`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d036a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d036a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0480`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0480`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d032c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d032c`

## pseudocode

```c

```
