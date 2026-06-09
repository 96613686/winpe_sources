# CGroupPolicySession::AddSessionIdAndUpdateTargetId(CToken const &,ulong)

- ea: `0x180049700`
- end: `0x180049a2f`
- name: `?AddSessionIdAndUpdateTargetId@CGroupPolicySession@@QEAAKAEBVCToken@@K@Z`
- size: `815`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION **this, const struct CToken *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000fa40`
- `0x180010760`
- `0x180010ed0`

## callees

- `0x1800111dc`
- `0x180049700`
- `0x180049a40`
- `0x180075ec0`
- `0x18007d770`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800497a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800498c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800497a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800498c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800498e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800498fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049931`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004998b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800498e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800498fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049931`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004998b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004989b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004989b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049860`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049860`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004988d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004988d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800497c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800497c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a23`

## pseudocode

```c

```
