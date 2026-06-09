# RdpTaskScheduler::DoWork(int)

- ea: `0x1800dc188`
- end: `0x1800dc449`
- name: `?DoWork@RdpTaskScheduler@@IEAAXH@Z`
- size: `705`
- prototype: `void __fastcall(PVOID pv, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x1800dd0b0`
- `0x1800dd330`

## callees

- `0x1800018a4`
- `0x180019a80`
- `0x180019ab0`
- `0x1800db050`
- `0x1800db244`
- `0x1800db868`
- `0x1800dc188`
- `0x1800dcd24`
- `0x1800dcdec`
- `0x1800dd560`
- `0x1800dd860`
- `0x1800ddcfc`
- `0x1800ddd74`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dc1a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dc1a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc20d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc20d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc204`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc2fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc39f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc204`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc2fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc39f`

## string_xrefs

- `0x1800dc274`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc3c5`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc28b`: `Task scheduler RunTask call failed.`
- `0x1800dc3cc`: `Task scheduler RunTask call failed.`

## pseudocode

```c

```
