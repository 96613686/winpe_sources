# ndisSendPacketsWithPause(void *,_NDIS_PACKET * *,uint)

- ea: `0x140036870`
- end: `0x140036a64`
- name: `?ndisSendPacketsWithPause@@YAXPEAXPEAPEAU_NDIS_PACKET@@I@Z`
- size: `500`
- prototype: `void __fastcall(void *, struct _NDIS_PACKET **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140036840`

## callees

- `0x140036870`
- `0x140036a70`
- `0x140036ea0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400e9ada`
- `ntoskrnl!KfRaiseIrql` at `0x1400e9ada`
- `ntoskrnl!KeLowerIrql` at `0x1400e9b54`
- `ntoskrnl!KeLowerIrql` at `0x1400e9b54`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036a26`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036a26`
- `ntoskrnl!KeSetEvent` at `0x1400e9bf2`
- `ntoskrnl!KeSetEvent` at `0x1400e9bf2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400368e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e9ba6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400368e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400e9ba6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400368a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400368a0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400e9b1b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400e9b1b`

## pseudocode

```c

```
