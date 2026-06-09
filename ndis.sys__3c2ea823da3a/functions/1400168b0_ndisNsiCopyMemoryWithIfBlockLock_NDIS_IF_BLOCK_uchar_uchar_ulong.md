# ndisNsiCopyMemoryWithIfBlockLock(_NDIS_IF_BLOCK *,uchar *,uchar *,ulong)

- ea: `0x1400168b0`
- end: `0x1400169fc`
- name: `?ndisNsiCopyMemoryWithIfBlockLock@@YAXPEAU_NDIS_IF_BLOCK@@PEAE1K@Z`
- size: `332`
- prototype: `void __fastcall(struct _NDIS_IF_BLOCK *, unsigned __int8 *, unsigned __int8 *Src, size_t Size)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14016b730`
- `0x14016be40`

## callees

- `0x1400168b0`
- `0x140016a80`
- `0x1400230c0`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140016918`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016971`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400169a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400169e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016918`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016971`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400169a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400169e1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400168d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016931`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016984`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400168d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016931`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016984`

## pseudocode

```c

```
