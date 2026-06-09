# CGPUserCollection::RWUnlock(void *)

- ea: `0x18000bdf0`
- end: `0x18000c392`
- name: `?RWUnlock@CGPUserCollection@@QEAAXPEAX@Z`
- size: `1442`
- prototype: `void(CGPUserCollection *__hidden this, void *)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180009d2c`
- `0x18000c398`
- `0x180010760`
- `0x1800535e0`
- `0x180090284`

## callees

- `0x18000844c`
- `0x18000a4b0`
- `0x18000bdf0`
- `0x18005ce24`
- `0x180075ec0`
- `0x18007d304`
- `0x1800b4188`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000beea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000be29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000beea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfa1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c1fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c311`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c1fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c311`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000beb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c000`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000beb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c32d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfeb`

## string_xrefs

- `0x18000c073`: `The reader was not present in the list.`
- `0x18000c0a3`: `The reader was not present in the list.`
- `0x18000c1be`: `Signalling first writer with ID [%d]`
- `0x18000c1e6`: `Signalling first writer with ID [%d]`
- `0x18000c2d4`: `Waking up writer with ID [%d].`
- `0x18000c2fc`: `Waking up writer with ID [%d].`

## pseudocode

```c

```
