# RdpTaskScheduler::DoWorkOnSignaledEvent(void)

- ea: `0x140087950`
- end: `0x140087b8c`
- name: `?DoWorkOnSignaledEvent@RdpTaskScheduler@@IEAAXXZ`
- size: `572`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1400887c0`

## callees

- `0x1400019e8`
- `0x14000dcac`
- `0x14003c0f0`
- `0x140086d68`
- `0x140087950`
- `0x14008836c`
- `0x140088434`
- `0x140088b94`
- `0x1400893f4`
- `0x140112010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14008798f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400879cc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14008798f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400879cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400879c3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400879e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087ac2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400879c3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400879e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140087ac2`

## string_xrefs

- `0x140087a36`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087ae3`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140087b10`: `Task scheduler RunTask call failed.`
- `0x140087a27`: `Task scheduler trigger task callback on event failed.`

## pseudocode

```c

```
