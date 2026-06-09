# CTrace::InternalTerminate(void)

- ea: `0x1800146f0`
- end: `0x18001483e`
- name: `?InternalTerminate@CTrace@@AEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CTrace *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006420`
- `0x18001465c`
- `0x180016344`
- `0x1800984f8`

## callees

- `0x1800063b0`
- `0x1800146f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001474e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001474e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014760`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800147e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001478f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001478f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147c9`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180014772`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180014772`

## string_xrefs

- `0x18001472c`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180014815`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`

## pseudocode

```c

```
