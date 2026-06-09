# VidSchiProcessHistoryBuffer(_VIDSCH_DMA_PACKET *,_VIDSCH_HISTORY_BUFFER_DATA *)

- ea: `0x14004e588`
- end: `0x14004e97c`
- name: `?VidSchiProcessHistoryBuffer@@YAXPEAU_VIDSCH_DMA_PACKET@@PEAU_VIDSCH_HISTORY_BUFFER_DATA@@@Z`
- size: `1012`
- prototype: `void __fastcall(struct _VIDSCH_DMA_PACKET *, struct _VIDSCH_HISTORY_BUFFER_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000c0b4`

## callees

- `0x140004268`
- `0x14003a820`
- `0x14004e588`
- `0x140059030`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004e762`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004e762`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004e915`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004e915`
- `watchdog!WdLogSingleEntry3` at `0x14004e719`
- `watchdog!WdLogSingleEntry3` at `0x14004e850`
- `watchdog!WdLogSingleEntry3` at `0x14004e719`
- `watchdog!WdLogSingleEntry3` at `0x14004e850`
- `watchdog!WdLogSingleEntry1` at `0x14004e895`
- `watchdog!WdLogSingleEntry1` at `0x14004e8d6`
- `watchdog!WdLogSingleEntry1` at `0x14004e92b`
- `watchdog!WdLogSingleEntry1` at `0x14004e895`
- `watchdog!WdLogSingleEntry1` at `0x14004e8d6`
- `watchdog!WdLogSingleEntry1` at `0x14004e92b`
- `dxgkrnl!DxgCoreInterface` at `0x14004e7a0`

## string_xrefs

- `0x14004e72a`: `Attempting to read memory outside the bounds of the history buffer. TimestampsStart=%I64X, TimestampsEnd=%I64X, BytesAccessed=%d`

## pseudocode

```c

```
