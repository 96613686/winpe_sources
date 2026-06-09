# RdpTaskScheduler::DoWork(int)

- ea: `0x1400897f8`
- end: `0x140089ab9`
- name: `?DoWork@RdpTaskScheduler@@IEAAXH@Z`
- size: `705`
- prototype: `void __fastcall(PVOID pv, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x14008a870`
- `0x14008aaf0`

## callees

- `0x1400019e8`
- `0x14000dcac`
- `0x14003e0b4`
- `0x140088514`
- `0x140088708`
- `0x140088ed8`
- `0x1400897f8`
- `0x14008a4dc`
- `0x14008a5a4`
- `0x14008ad04`
- `0x14008af90`
- `0x14008b4ec`
- `0x14008b564`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x140089813`
- `KERNEL32!GetTickCount64` at `0x140089813`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089843`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008987d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089843`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008987d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089874`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089899`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008996d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089a0f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089874`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089899`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008996d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089a0f`

## string_xrefs

- `0x1400898e4`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089a35`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400898fb`: `Task scheduler RunTask call failed.`
- `0x140089a3c`: `Task scheduler RunTask call failed.`

## pseudocode

```c

```
