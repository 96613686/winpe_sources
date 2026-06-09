# ndisSendPacketsWithPause(void *,_NDIS_PACKET * *,uint)

- ea: `0x140005640`
- end: `0x140005834`
- name: `?ndisSendPacketsWithPause@@YAXPEAXPEAPEAU_NDIS_PACKET@@I@Z`
- size: `500`
- prototype: `void __fastcall(void *, struct _NDIS_PACKET **, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005610`

## callees

- `0x140005640`
- `0x140005840`
- `0x140005c70`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400ebf46`
- `ntoskrnl!KeLowerIrql` at `0x1400ebf46`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400057f6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400057f6`
- `ntoskrnl!KfRaiseIrql` at `0x1400ebecc`
- `ntoskrnl!KfRaiseIrql` at `0x1400ebecc`
- `ntoskrnl!KeSetEvent` at `0x1400ebfe4`
- `ntoskrnl!KeSetEvent` at `0x1400ebfe4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400056b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ebf98`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400056b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ebf98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005670`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005670`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ebf0d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ebf0d`

## pseudocode

```c

```
