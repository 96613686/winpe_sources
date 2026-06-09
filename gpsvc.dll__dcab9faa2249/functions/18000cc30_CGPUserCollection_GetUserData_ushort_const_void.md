# CGPUserCollection::GetUserData(ushort const *,void *)

- ea: `0x18000cc30`
- end: `0x18000d2a3`
- name: `?GetUserData@CGPUserCollection@@QEAAPEAVCGroupPolicySession@@PEBGPEAX@Z`
- size: `1651`
- prototype: `struct CGroupPolicySession *(CGPUserCollection *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c584`
- `0x18000e5f0`
- `0x18008a930`
- `0x18008af70`
- `0x18008b310`

## callees

- `0x180008244`
- `0x18000a4b0`
- `0x18000cc30`
- `0x18000d2b0`
- `0x18005ce24`
- `0x180075ec0`
- `0x18007d304`
- `0x1800b4188`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cebd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d19b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d209`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ce49`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ce49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf81`

## string_xrefs

- `0x18000d021`: `The reader was not present in the list.`
- `0x18000d051`: `The reader was not present in the list.`
- `0x18000d15e`: `Signalling first writer with ID [%d]`
- `0x18000d186`: `Signalling first writer with ID [%d]`

## pseudocode

```c

```
