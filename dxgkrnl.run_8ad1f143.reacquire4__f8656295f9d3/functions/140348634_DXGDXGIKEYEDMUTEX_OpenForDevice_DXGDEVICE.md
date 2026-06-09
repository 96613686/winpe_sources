# DXGDXGIKEYEDMUTEX::OpenForDevice(DXGDEVICE *)

- ea: `0x140348634`
- end: `0x140348ae8`
- name: `?OpenForDevice@DXGDXGIKEYEDMUTEX@@QEAAJPEAVDXGDEVICE@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(DXGDXGIKEYEDMUTEX *__hidden this, struct DXGDEVICE *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14034849c`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14001bd70`
- `0x14002d9f0`
- `0x140030860`
- `0x140033bd4`
- `0x14004885c`
- `0x1401d678c`
- `0x14024a3ec`
- `0x140323854`
- `0x14032df70`
- `0x140348634`
- `0x140351dc0`
- `0x1403dcc60`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140348aaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140348aaf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140348aa3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140348aa3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348722`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034874f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403487b4`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403487e1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034880a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348837`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403488d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034890b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034895a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348987`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348722`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034874f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403487b4`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403487e1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034880a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348837`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403488d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034890b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14034895a`
- `ntoskrnl!PsGetCurrentProcess` at `0x140348987`
- `watchdog!WdLogSingleEntry2` at `0x1403486bb`
- `watchdog!WdLogSingleEntry2` at `0x140348739`
- `watchdog!WdLogSingleEntry2` at `0x1403487cb`
- `watchdog!WdLogSingleEntry2` at `0x140348821`
- `watchdog!WdLogSingleEntry2` at `0x140348971`
- `watchdog!WdLogSingleEntry2` at `0x1403486bb`
- `watchdog!WdLogSingleEntry2` at `0x140348739`
- `watchdog!WdLogSingleEntry2` at `0x1403487cb`
- `watchdog!WdLogSingleEntry2` at `0x140348821`
- `watchdog!WdLogSingleEntry2` at `0x140348971`
- `watchdog!WdLogSingleEntry3` at `0x1403488f5`
- `watchdog!WdLogSingleEntry3` at `0x1403488f5`
- `watchdog!WdLogSingleEntry0` at `0x140348664`
- `watchdog!WdLogSingleEntry0` at `0x140348a47`
- `watchdog!WdLogSingleEntry0` at `0x140348664`
- `watchdog!WdLogSingleEntry0` at `0x140348a47`

## string_xrefs

- `0x1403486cc`: `KeyedMutex 0x%I64x already opened locally by device 0x%I64x`
- `0x14034875b`: `Failed to open local producer mutex for KeyedMutex 0x%I64x in process 0x%I64x`
- `0x140348843`: `Failed to open shared surface for KeyedMutex 0x%I64x in process 0x%I64x, insure the DDA producer and consumer devices are on the same adapter`
- `0x140348998`: `Failed to open DxgiKeyedMutex for device 0x%I64x in process 0x%I64x`
- `0x14034891a`: `Failed to open GPU fence 0x%I64x for device 0x%I64x in process 0x%I64x`

## pseudocode

```c

```
