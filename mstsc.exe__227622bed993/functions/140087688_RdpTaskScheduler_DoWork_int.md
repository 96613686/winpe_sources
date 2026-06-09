# RdpTaskScheduler::DoWork(int)

- ea: `0x140087688`
- end: `0x140087949`
- name: `?DoWork@RdpTaskScheduler@@IEAAXH@Z`
- size: `705`
- prototype: `void __fastcall(PVOID pv, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x140088700`
- `0x140088980`

## callees

- `0x1400019e8`
- `0x14000dcac`
- `0x14003c0f0`
- `0x1400863a4`
- `0x140086598`
- `0x140086d68`
- `0x140087688`
- `0x14008836c`
- `0x140088434`
- `0x140088b94`
- `0x140088e20`
- `0x14008937c`
- `0x1400893f4`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1400876a3`
- `KERNEL32!GetTickCount64` at `0x1400876a3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400876d3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008770d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400876d3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008770d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087704`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087729`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400877fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008789f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087704`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087729`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400877fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14008789f`

## string_xrefs

- `0x140087774`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1400878c5`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x14008778b`: `Task scheduler RunTask call failed.`
- `0x1400878cc`: `Task scheduler RunTask call failed.`

## pseudocode

```c

```
