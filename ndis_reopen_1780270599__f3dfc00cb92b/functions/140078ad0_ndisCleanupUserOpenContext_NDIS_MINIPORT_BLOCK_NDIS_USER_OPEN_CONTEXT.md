# ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)

- ea: `0x140078ad0`
- end: `0x140078c3c`
- name: `?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z`
- size: `364`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140087848`
- `0x1400a2ecc`

## callees

- `0x140010d20`
- `0x1400400d0`
- `0x140078ad0`
- `0x140087b14`
- `0x140088a2c`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140078b3a`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140078b3a`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140078bec`
- `ntoskrnl!MmUnlockPagableImageSection` at `0x140078bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078b4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078b10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078bd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078b10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078bd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078b69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078b69`

## pseudocode

```c

```
