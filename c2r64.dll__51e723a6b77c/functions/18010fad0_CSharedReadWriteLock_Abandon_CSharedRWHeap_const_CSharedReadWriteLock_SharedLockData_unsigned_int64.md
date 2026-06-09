# CSharedReadWriteLock::Abandon(CSharedRWHeap const *,CSharedReadWriteLock::SharedLockData *,unsigned __int64)

- ea: `0x18010fad0`
- end: `0x18010fd0b`
- name: `?Abandon@CSharedReadWriteLock@@SAJPEBVCSharedRWHeap@@PEAUSharedLockData@1@_K@Z`
- size: `571`
- prototype: `static int(const struct CSharedRWHeap *, struct CSharedReadWriteLock::SharedLockData *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010f560`

## callees

- `0x18003e690`
- `0x18010fad0`
- `0x1801116c0`
- `0x180113100`
- `0x180122030`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18010fbb0`
- `KERNEL32!GetLastError` at `0x18010fc50`
- `KERNEL32!GetLastError` at `0x18010fbb0`
- `KERNEL32!GetLastError` at `0x18010fc50`
- `KERNEL32!CloseHandle` at `0x18010fcbb`
- `KERNEL32!CloseHandle` at `0x18010fcc9`
- `KERNEL32!CloseHandle` at `0x18010fcd8`
- `KERNEL32!CloseHandle` at `0x18010fcbb`
- `KERNEL32!CloseHandle` at `0x18010fcc9`
- `KERNEL32!CloseHandle` at `0x18010fcd8`
- `KERNEL32!ReleaseSemaphore` at `0x18010fc87`
- `KERNEL32!ReleaseSemaphore` at `0x18010fcad`
- `KERNEL32!ReleaseSemaphore` at `0x18010fc87`
- `KERNEL32!ReleaseSemaphore` at `0x18010fcad`

## string_xrefs

- `0x18010fbdf`: `_RwLockWriterSem`
- `0x18010fb34`: `_RwLockReaderSem`

## pseudocode

```c

```
