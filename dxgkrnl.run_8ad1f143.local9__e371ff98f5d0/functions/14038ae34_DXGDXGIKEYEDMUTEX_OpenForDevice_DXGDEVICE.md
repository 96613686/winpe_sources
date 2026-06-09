# DXGDXGIKEYEDMUTEX::OpenForDevice(DXGDEVICE *)

- ea: `0x14038ae34`
- end: `0x14038b2e8`
- name: `?OpenForDevice@DXGDXGIKEYEDMUTEX@@QEAAJPEAVDXGDEVICE@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(DXGDXGIKEYEDMUTEX *__hidden this, struct DXGDEVICE *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14038ac9c`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14002dbc0`
- `0x140030a30`
- `0x140033da4`
- `0x140048a5c`
- `0x1401d938c`
- `0x14024d9cc`
- `0x14032a5c4`
- `0x140334ce0`
- `0x140352270`
- `0x14038ae34`
- `0x1403dd080`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038b2af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14038b2af`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14038b2a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14038b2a3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038af22`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038af4f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038afb4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038afe1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b00a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b037`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b0d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b10b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b15a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b187`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038af22`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038af4f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038afb4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038afe1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b00a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b037`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b0d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b10b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b15a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038b187`
- `watchdog!WdLogSingleEntry2` at `0x14038aebb`
- `watchdog!WdLogSingleEntry2` at `0x14038af39`
- `watchdog!WdLogSingleEntry2` at `0x14038afcb`
- `watchdog!WdLogSingleEntry2` at `0x14038b021`
- `watchdog!WdLogSingleEntry2` at `0x14038b171`
- `watchdog!WdLogSingleEntry2` at `0x14038aebb`
- `watchdog!WdLogSingleEntry2` at `0x14038af39`
- `watchdog!WdLogSingleEntry2` at `0x14038afcb`
- `watchdog!WdLogSingleEntry2` at `0x14038b021`
- `watchdog!WdLogSingleEntry2` at `0x14038b171`
- `watchdog!WdLogSingleEntry3` at `0x14038b0f5`
- `watchdog!WdLogSingleEntry3` at `0x14038b0f5`
- `watchdog!WdLogSingleEntry0` at `0x14038ae64`
- `watchdog!WdLogSingleEntry0` at `0x14038b247`
- `watchdog!WdLogSingleEntry0` at `0x14038ae64`
- `watchdog!WdLogSingleEntry0` at `0x14038b247`

## string_xrefs

- `0x14038aecc`: `KeyedMutex 0x%I64x already opened locally by device 0x%I64x`
- `0x14038af5b`: `Failed to open local producer mutex for KeyedMutex 0x%I64x in process 0x%I64x`
- `0x14038b043`: `Failed to open shared surface for KeyedMutex 0x%I64x in process 0x%I64x, insure the DDA producer and consumer devices are on the same adapter`
- `0x14038b198`: `Failed to open DxgiKeyedMutex for device 0x%I64x in process 0x%I64x`
- `0x14038b11a`: `Failed to open GPU fence 0x%I64x for device 0x%I64x in process 0x%I64x`

## pseudocode

```c

```
