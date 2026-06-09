# RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)

- ea: `0x18016a080`
- end: `0x18016a5f3`
- name: `?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z`
- size: `1395`
- prototype: `void __fastcall(HRESULT hrError, unsigned int cStowedExceptions, _STOWED_EXCEPTION_INFORMATION_V2 **aStowedExceptionPointers)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x18018b9c0`
- `0x1801f1300`

## callees

- `0x180001dec`
- `0x180002eac`
- `0x18000b408`
- `0x180040078`
- `0x180088d4c`
- `0x1800bb15c`
- `0x1800fe6e4`
- `0x1800fe734`
- `0x1800fec04`
- `0x18011ef68`
- `0x180161344`
- `0x180164ffc`
- `0x18016a080`
- `0x180186f94`
- `0x1801999b0`
- `0x18019a654`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18016a4fb`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18016a5a4`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18016a4fb`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18016a5a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016a18f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18016a18f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18016a219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18016a219`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18016a485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18016a485`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18016a493`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18016a493`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18016a5b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18016a5b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18016a1f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18016a1f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18016a442`
- `OLEAUT32!__imp_SysFreeString` at `0x18016a442`

## pseudocode

```c

```
