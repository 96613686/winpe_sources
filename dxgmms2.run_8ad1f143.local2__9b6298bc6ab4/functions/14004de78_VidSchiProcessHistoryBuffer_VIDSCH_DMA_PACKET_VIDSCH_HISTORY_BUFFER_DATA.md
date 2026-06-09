# VidSchiProcessHistoryBuffer(_VIDSCH_DMA_PACKET *,_VIDSCH_HISTORY_BUFFER_DATA *)

- ea: `0x14004de78`
- end: `0x14004e26c`
- name: `?VidSchiProcessHistoryBuffer@@YAXPEAU_VIDSCH_DMA_PACKET@@PEAU_VIDSCH_HISTORY_BUFFER_DATA@@@Z`
- size: `1012`
- prototype: `void __fastcall(struct _VIDSCH_DMA_PACKET *, struct _VIDSCH_HISTORY_BUFFER_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000c364`

## callees

- `0x1400045ec`
- `0x14003bb10`
- `0x14004de78`
- `0x140058760`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004e052`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004e052`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004e205`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004e205`
- `watchdog!WdLogSingleEntry3` at `0x14004e009`
- `watchdog!WdLogSingleEntry3` at `0x14004e140`
- `watchdog!WdLogSingleEntry3` at `0x14004e009`
- `watchdog!WdLogSingleEntry3` at `0x14004e140`
- `watchdog!WdLogSingleEntry1` at `0x14004e185`
- `watchdog!WdLogSingleEntry1` at `0x14004e1c6`
- `watchdog!WdLogSingleEntry1` at `0x14004e21b`
- `watchdog!WdLogSingleEntry1` at `0x14004e185`
- `watchdog!WdLogSingleEntry1` at `0x14004e1c6`
- `watchdog!WdLogSingleEntry1` at `0x14004e21b`
- `dxgkrnl!DxgCoreInterface` at `0x14004e090`

## string_xrefs

- `0x14004e01a`: `Attempting to read memory outside the bounds of the history buffer. TimestampsStart=%I64X, TimestampsEnd=%I64X, BytesAccessed=%d`

## pseudocode

```c

```
