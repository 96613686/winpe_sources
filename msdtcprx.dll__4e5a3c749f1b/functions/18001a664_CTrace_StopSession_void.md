# CTrace::StopSession(void)

- ea: `0x18001a664`
- end: `0x18001a96e`
- name: `?StopSession@CTrace@@QEAAJXZ`
- size: `778`
- prototype: `__int64 __fastcall(CTrace *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c210`

## callees

- `0x180003cf0`
- `0x18000f674`
- `0x18001a360`
- `0x18001a664`
- `0x18001d138`
- `0x18001d178`
- `0x180027920`
- `0x18007ccd4`
- `0x180081d9e`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a8f0`
- `ADVAPI32!EnableTrace` at `0x18001a805`
- `ADVAPI32!EnableTrace` at `0x18001a805`
- `ADVAPI32!QueryTraceW` at `0x18001a7a3`
- `ADVAPI32!QueryTraceW` at `0x18001a7a3`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18001a864`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18001a864`

## string_xrefs

- `0x18001a69b`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001a82d`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001a896`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001a930`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001a720`: `OpenTracingMSDTCKey FAILED`

## pseudocode

```c

```
