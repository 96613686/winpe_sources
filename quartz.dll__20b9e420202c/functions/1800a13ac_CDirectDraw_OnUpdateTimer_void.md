# CDirectDraw::OnUpdateTimer(void)

- ea: `0x1800a13ac`
- end: `0x1800a1448`
- name: `?OnUpdateTimer@CDirectDraw@@QEAAHXZ`
- size: `156`
- prototype: `__int64 __fastcall(CDirectDraw *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800317f8`

## callees

- `0x1800a13ac`
- `0x1800a1818`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800a1409`
- `KERNEL32!LeaveCriticalSection` at `0x1800a142b`
- `KERNEL32!LeaveCriticalSection` at `0x1800a1409`
- `KERNEL32!LeaveCriticalSection` at `0x1800a142b`
- `KERNEL32!EnterCriticalSection` at `0x1800a13cc`
- `KERNEL32!EnterCriticalSection` at `0x1800a13db`
- `KERNEL32!EnterCriticalSection` at `0x1800a13cc`
- `KERNEL32!EnterCriticalSection` at `0x1800a13db`
- `USER32!KillTimer` at `0x1800a13fa`
- `USER32!KillTimer` at `0x1800a13fa`

## pseudocode

```c

```
