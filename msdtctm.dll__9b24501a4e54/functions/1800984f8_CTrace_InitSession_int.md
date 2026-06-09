# CTrace::InitSession(int)

- ea: `0x1800984f8`
- end: `0x1800987a9`
- name: `?InitSession@CTrace@@QEAAJH@Z`
- size: `689`
- prototype: `__int64 __fastcall(CTrace *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006420`

## callees

- `0x1800063b0`
- `0x18000fb90`
- `0x1800146f0`
- `0x180018ec8`
- `0x18001931c`
- `0x180020fcc`
- `0x1800983d4`
- `0x1800984f8`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180098652`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180098652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009865c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009865c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098731`
- `ADVAPI32!EnableTrace` at `0x1800986e7`
- `ADVAPI32!EnableTrace` at `0x1800986e7`

## string_xrefs

- `0x180098536`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800985a7`: `DoesTraceDirectoryExist FAILED`
- `0x1800985c8`: `OpenTracingLoggingOptionsKey FAILED`

## pseudocode

```c

```
