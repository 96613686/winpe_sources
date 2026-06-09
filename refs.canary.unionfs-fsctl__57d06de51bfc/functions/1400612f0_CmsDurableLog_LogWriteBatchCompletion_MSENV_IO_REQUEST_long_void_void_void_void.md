# CmsDurableLog::LogWriteBatchCompletion(_MSENV_IO_REQUEST *,long,void *,void *,void *,void *)

- ea: `0x1400612f0`
- end: `0x14006162c`
- name: `?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@JPEAX111@Z`
- size: `828`
- prototype: `__int64 __fastcall(PVOID P, int, void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140060a4c`
- `0x140060b80`
- `0x140060d80`
- `0x1400610f0`
- `0x140061238`
- `0x1400612d0`
- `0x1400612f0`
- `0x140061640`
- `0x140062510`
- `0x140072970`
- `0x140092220`
- `0x1400c4acc`
- `0x14012084c`
- `0x14014e60c`
- `0x1401556d4`
- `0x1401e9dc0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1400615ad`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400615ad`
- `ntoskrnl!KeSetEvent` at `0x140061602`
- `ntoskrnl!KeSetEvent` at `0x140061602`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140061471`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006148a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400614d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140061471`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006148a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400614d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400614f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400613f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400613f3`

## pseudocode

```c

```
