# ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread(void)

- ea: `0x180185314`
- end: `0x180185433`
- name: `?DestroyContextAndEntryForCurrentThread@ThreadBoundThreadContextManager@@SAXXZ`
- size: `287`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801f2ba8`

## callees

- `0x180121ed0`
- `0x180185314`
- `0x18018543c`
- `0x1802c8ddc`
- `0x1802cab50`

## import_xrefs

- `msvcrt!free` at `0x1801853a4`
- `msvcrt!free` at `0x1801853ee`
- `msvcrt!free` at `0x1801853a4`
- `msvcrt!free` at `0x1801853ee`
- `KERNEL32!TlsGetValue` at `0x180185347`
- `KERNEL32!TlsGetValue` at `0x180185347`
- `KERNEL32!EnterCriticalSection` at `0x18018533a`
- `KERNEL32!EnterCriticalSection` at `0x18018533a`
- `KERNEL32!LeaveCriticalSection` at `0x180185358`
- `KERNEL32!LeaveCriticalSection` at `0x180185427`
- `KERNEL32!LeaveCriticalSection` at `0x180185358`
- `KERNEL32!LeaveCriticalSection` at `0x180185427`

## pseudocode

```c

```
