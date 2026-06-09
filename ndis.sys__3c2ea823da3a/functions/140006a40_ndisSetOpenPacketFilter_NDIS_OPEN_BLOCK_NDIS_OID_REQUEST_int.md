# ndisSetOpenPacketFilter(_NDIS_OPEN_BLOCK *,_NDIS_OID_REQUEST *,int *)

- ea: `0x140006a40`
- end: `0x140006da5`
- name: `?ndisSetOpenPacketFilter@@YAEPEAU_NDIS_OPEN_BLOCK@@PEAU_NDIS_OID_REQUEST@@PEAH@Z`
- size: `869`
- prototype: `unsigned __int8 __fastcall(struct _NDIS_OPEN_BLOCK *, struct _NDIS_OID_REQUEST *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002b7d0`

## callees

- `0x140006a40`
- `0x140006db0`
- `0x140019c70`
- `0x14001c050`
- `0x14006a3a0`
- `0x140072ce0`
- `0x1400873e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140006b4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006b4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006c9d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ae1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ae1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006b88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bcc`

## pseudocode

```c

```
