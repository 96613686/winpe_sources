# HyperVRepository::UnlockExclusiveIfNeeded(int)

- ea: `0x1800949a4`
- end: `0x180094a03`
- name: `?UnlockExclusiveIfNeeded@HyperVRepository@@AEAAXH@Z`
- size: `95`
- prototype: `void __fastcall(HyperVRepository *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180093180`
- `0x1800945d0`

## callees

- `0x1800949a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800949e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800949e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800949b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800949b9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800949f2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800949f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800949bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800949bf`

## pseudocode

```c

```
