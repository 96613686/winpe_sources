# DTCTraceControlCallback

- ea: `0x180021a30`
- end: `0x180021c5f`
- name: `DTCTraceControlCallback`
- size: `559`
- prototype: `ULONG __stdcall(WMIDPREQUESTCODE RequestCode, PVOID RequestContext, ULONG *BufferSize, PVOID Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x180021a30`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021b5d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b67`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x180021b46`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x180021b46`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x180021b27`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x180021b27`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x180021b3a`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x180021b3a`

## string_xrefs

- `0x180021a4d`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180021b98`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180021be0`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`

## pseudocode

```c

```
