# MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::WaitForFull(void)

- ea: `0x1800211d4`
- end: `0x180021240`
- name: `?WaitForFull@?$CSlimQueue@PEAUjpeg_task_resource_struct@@$03@CMJPGMFT@MotionTurboJpeg@@QEAAXXZ`
- size: `108`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180021150`

## callees

- `0x18001cb04`
- `0x1800211d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800211e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800211e6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002121d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002121d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180021225`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180021225`

## pseudocode

```c

```
