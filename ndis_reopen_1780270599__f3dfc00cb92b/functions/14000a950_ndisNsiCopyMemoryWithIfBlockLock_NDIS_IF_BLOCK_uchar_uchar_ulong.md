# ndisNsiCopyMemoryWithIfBlockLock(_NDIS_IF_BLOCK *,uchar *,uchar *,ulong)

- ea: `0x14000a950`
- end: `0x14000aa9c`
- name: `?ndisNsiCopyMemoryWithIfBlockLock@@YAXPEAU_NDIS_IF_BLOCK@@PEAE1K@Z`
- size: `332`
- prototype: `void __fastcall(struct _NDIS_IF_BLOCK *, unsigned __int8 *, unsigned __int8 *Src, size_t Size)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1401725a0`
- `0x140172cb0`

## callees

- `0x14000a950`
- `0x14000ab20`
- `0x140017220`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa11`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa48`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa81`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa11`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa48`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aa81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a971`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a9d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa24`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a971`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a9d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa24`

## pseudocode

```c

```
