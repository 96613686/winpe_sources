# MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::PutWait(jpeg_task_resource_struct *)

- ea: `0x18001b780`
- end: `0x18001b813`
- name: `?PutWait@?$CSlimQueue@PEAUjpeg_task_resource_struct@@$03@CMJPGMFT@MotionTurboJpeg@@QEAAXPEAUjpeg_task_resource_struct@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180017df0`

## callees

- `0x18001b780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b795`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b795`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7dd`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001b80b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001b80b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001b7f6`

## pseudocode

```c

```
