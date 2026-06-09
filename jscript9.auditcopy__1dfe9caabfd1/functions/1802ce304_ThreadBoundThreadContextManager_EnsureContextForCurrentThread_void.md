# ThreadBoundThreadContextManager::EnsureContextForCurrentThread(void)

- ea: `0x1802ce304`
- end: `0x1802ce442`
- name: `?EnsureContextForCurrentThread@ThreadBoundThreadContextManager@@SAPEAVThreadContext@@XZ`
- size: `318`
- prototype: `struct ThreadContext *(void)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1801dc0cc`
- `0x1802005d0`
- `0x180220eac`

## callees

- `0x18012dca4`
- `0x1801a31bc`
- `0x1801bc71c`
- `0x18020666c`
- `0x1802ce304`
- `0x1802d03d0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1802ce33a`
- `KERNEL32!TlsGetValue` at `0x1802ce359`
- `KERNEL32!TlsGetValue` at `0x1802ce33a`
- `KERNEL32!TlsGetValue` at `0x1802ce359`
- `KERNEL32!EnterCriticalSection` at `0x1802ce327`
- `KERNEL32!EnterCriticalSection` at `0x1802ce327`
- `KERNEL32!LeaveCriticalSection` at `0x1802ce412`
- `KERNEL32!LeaveCriticalSection` at `0x1802ce426`
- `KERNEL32!LeaveCriticalSection` at `0x1802ce412`
- `KERNEL32!LeaveCriticalSection` at `0x1802ce426`

## pseudocode

```c

```
