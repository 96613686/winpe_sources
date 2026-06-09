# DXGPRESENTHISTORYTOKENQUEUE::PropagatePresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN *,bool,bool,bool,bool,bool,bool,bool,void *)

- ea: `0x140018c6c`
- end: `0x140018e87`
- name: `?PropagatePresentHistoryToken@DXGPRESENTHISTORYTOKENQUEUE@@QEAAXPEAU_D3DKMT_PRESENTHISTORYTOKEN@@_N111111PEAX@Z`
- size: `539`
- prototype: `void __usercall(PKSPIN_LOCK SpinLock@<rcx>, struct _D3DKMT_PRESENTHISTORYTOKEN *@<rdx>, bool@<r8b>, bool@<r9b>, bool, bool, bool, bool, bool, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001898c`

## callees

- `0x1400045ec`
- `0x1400132a8`
- `0x140018c6c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018ca8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018ca8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018d9e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018d9e`
- `ntoskrnl!KeSetEvent` at `0x140018d8d`
- `ntoskrnl!KeSetEvent` at `0x140018d8d`
- `watchdog!WdLogSingleEntry0` at `0x140018de8`
- `watchdog!WdLogSingleEntry0` at `0x140018e3a`
- `watchdog!WdLogSingleEntry0` at `0x140018de8`
- `watchdog!WdLogSingleEntry0` at `0x140018e3a`

## string_xrefs

- `0x140018dfd`: `m_PresentHistoryHead < D3DKMT_GETPRESENTHISTORY_MAXTOKENS`

## pseudocode

```c

```
