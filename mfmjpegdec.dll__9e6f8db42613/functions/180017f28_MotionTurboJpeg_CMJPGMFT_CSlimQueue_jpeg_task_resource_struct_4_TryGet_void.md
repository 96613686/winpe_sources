# MotionTurboJpeg::CMJPGMFT::CSlimQueue<jpeg_task_resource_struct *,4>::TryGet(void)

- ea: `0x180017f28`
- end: `0x180017f9c`
- name: `?TryGet@?$CSlimQueue@PEAUjpeg_task_resource_struct@@$03@CMJPGMFT@MotionTurboJpeg@@QEAAPEAUjpeg_task_resource_struct@@XZ`
- size: `116`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180017df0`
- `0x180017e50`

## callees

- `0x180017f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017f52`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180017f61`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180017f61`

## pseudocode

```c

```
