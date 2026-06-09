# CClfsLogFcbPhysical::ReadQueuedOwnerPage(_CLS_LSN const &,uchar *,ulong)

- ea: `0x140001008`
- end: `0x140001162`
- name: `?ReadQueuedOwnerPage@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@PEAEK@Z`
- size: `346`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, const union _CLS_LSN *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400647c0`

## callees

- `0x140001008`
- `0x140008c40`
- `0x140017f20`
- `0x140017f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001040`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001040`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001143`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019309`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001143`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019309`

## pseudocode

```c

```
