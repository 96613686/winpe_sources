# ReleaseShadowBuffer

- ea: `0x1400e65a0`
- end: `0x1400e6675`
- name: `ReleaseShadowBuffer`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400d8e60`
- `0x1400eb300`

## callees

- `0x140009fc0`
- `0x1400e65a0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e65d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e65d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e6616`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e6616`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400e65f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400e65f5`
- `ntoskrnl!KeBugCheckEx` at `0x1400e6668`
- `ntoskrnl!KeBugCheckEx` at `0x1400e6668`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6642`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6642`

## pseudocode

```c

```
