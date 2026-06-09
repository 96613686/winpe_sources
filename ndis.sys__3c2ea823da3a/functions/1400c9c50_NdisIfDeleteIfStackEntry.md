# NdisIfDeleteIfStackEntry

- ea: `0x1400c9c50`
- end: `0x1400c9d64`
- name: `NdisIfDeleteIfStackEntry`
- size: `276`
- prototype: `void __stdcall(NET_IFINDEX HigherLayerIfIndex, NET_IFINDEX LowerLayerIfIndex)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140180960`

## callees

- `0x140044f90`
- `0x140045150`
- `0x1400c9c50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9cf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9cf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c9d20`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c9d20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c9c92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c9c92`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400c9d0a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400c9d0a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400c9ca8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400c9ca8`

## pseudocode

```c

```
