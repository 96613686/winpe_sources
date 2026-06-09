# NdisIfDeleteIfStackEntry

- ea: `0x1400cee00`
- end: `0x1400cef14`
- name: `NdisIfDeleteIfStackEntry`
- size: `276`
- prototype: `void __stdcall(NET_IFINDEX HigherLayerIfIndex, NET_IFINDEX LowerLayerIfIndex)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140186f10`

## callees

- `0x140049a90`
- `0x140049c50`
- `0x1400cee00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400ceea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ceea7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ceed0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ceed0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cee42`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cee42`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cee58`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cee58`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ceeba`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ceeba`

## pseudocode

```c

```
