# RdpTaskScheduler::DoWorkOnSignaledEvent(void)

- ea: `0x140089ac0`
- end: `0x140089cfc`
- name: `?DoWorkOnSignaledEvent@RdpTaskScheduler@@IEAAXXZ`
- size: `572`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x14008a930`

## callees

- `0x1400019e8`
- `0x14000dcac`
- `0x14003e0b4`
- `0x140088ed8`
- `0x140089ac0`
- `0x14008a4dc`
- `0x14008a5a4`
- `0x14008ad04`
- `0x14008b564`
- `0x140114010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140089aff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089b3c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089aff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140089b3c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089b33`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089b58`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089c32`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089b33`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089b58`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140089c32`

## string_xrefs

- `0x140089ba6`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089c53`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x140089c80`: `Task scheduler RunTask call failed.`
- `0x140089b97`: `Task scheduler trigger task callback on event failed.`

## pseudocode

```c

```
