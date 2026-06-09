# DXGPRESENTHISTORYTOKENQUEUE::PropagatePresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN *,bool,bool,bool,bool,bool,bool,bool,void *)

- ea: `0x14002471c`
- end: `0x140024937`
- name: `?PropagatePresentHistoryToken@DXGPRESENTHISTORYTOKENQUEUE@@QEAAXPEAU_D3DKMT_PRESENTHISTORYTOKEN@@_N111111PEAX@Z`
- size: `539`
- prototype: `void __usercall(PKSPIN_LOCK SpinLock@<rcx>, struct _D3DKMT_PRESENTHISTORYTOKEN *@<rdx>, bool@<r8b>, bool@<r9b>, bool, bool, bool, bool, bool, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002443c`

## callees

- `0x140004268`
- `0x140012d48`
- `0x14002471c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024758`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024758`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002484e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002484e`
- `ntoskrnl!KeSetEvent` at `0x14002483d`
- `ntoskrnl!KeSetEvent` at `0x14002483d`
- `watchdog!WdLogSingleEntry0` at `0x140024898`
- `watchdog!WdLogSingleEntry0` at `0x1400248ea`
- `watchdog!WdLogSingleEntry0` at `0x140024898`
- `watchdog!WdLogSingleEntry0` at `0x1400248ea`

## string_xrefs

- `0x1400248ad`: `m_PresentHistoryHead < D3DKMT_GETPRESENTHISTORY_MAXTOKENS`

## pseudocode

```c

```
