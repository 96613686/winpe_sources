# MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::GetWait(void)

- ea: `0x18001ced0`
- end: `0x18001cf4b`
- name: `?GetWait@?$CSlimQueue@PEAUjpeg_task_resource_struct@@$03@CMJPGMFT@MotionTurboJpeg@@QEAAPEAUjpeg_task_resource_struct@@XZ`
- size: `123`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180021080`

## callees

- `0x18001ced0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cee2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cee2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cf12`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001cf43`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001cf43`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001cf1c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001cf1c`

## pseudocode

```c

```
