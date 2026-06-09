# ThreadBoundThreadContextManager::DestroyContextAndEntryForCurrentThread(void)

- ea: `0x18018656c`
- end: `0x1801866b0`
- name: `?DestroyContextAndEntryForCurrentThread@ThreadBoundThreadContextManager@@SAXXZ`
- size: `324`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801f6028`

## callees

- `0x180117010`
- `0x18018656c`
- `0x1801866b8`
- `0x1802ce578`
- `0x1802d0350`

## import_xrefs

- `msvcrt!free` at `0x18018660f`
- `msvcrt!free` at `0x18018665f`
- `msvcrt!free` at `0x18018660f`
- `msvcrt!free` at `0x18018665f`
- `KERNEL32!TlsGetValue` at `0x1801865a5`
- `KERNEL32!TlsGetValue` at `0x1801865a5`
- `KERNEL32!EnterCriticalSection` at `0x180186592`
- `KERNEL32!EnterCriticalSection` at `0x180186592`
- `KERNEL32!LeaveCriticalSection` at `0x1801865bc`
- `KERNEL32!LeaveCriticalSection` at `0x18018669e`
- `KERNEL32!LeaveCriticalSection` at `0x1801865bc`
- `KERNEL32!LeaveCriticalSection` at `0x18018669e`

## pseudocode

```c

```
