# MonitoredCritSecLocker::Unlock(void)

- ea: `0x18000e7f0`
- end: `0x18000e8ff`
- name: `?Unlock@MonitoredCritSecLocker@@UEAAXXZ`
- size: `271`
- prototype: `void __fastcall(MonitoredCritSecLocker *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180010470`
- `0x18002fa74`
- `0x180067dc4`
- `0x180123cf0`
- `0x1801319cc`
- `0x18015e85c`
- `0x1801bcfec`

## callees

- `0x18000e7f0`
- `0x180098538`
- `0x1800be858`
- `0x1800f84c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e808`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e808`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e868`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e87e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e868`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e87e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8ac`

## string_xrefs

- `0x18000e8c0`: `Lock: Error found, LeaveCriticalSection is called by the wrong thread. Owner thread: {}, current thread: {}`

## pseudocode

```c

```
