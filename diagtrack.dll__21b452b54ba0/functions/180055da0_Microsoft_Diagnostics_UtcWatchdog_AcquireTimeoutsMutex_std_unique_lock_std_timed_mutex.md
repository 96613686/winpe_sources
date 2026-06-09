# Microsoft::Diagnostics::UtcWatchdog::AcquireTimeoutsMutex(std::unique_lock<std::timed_mutex> &)

- ea: `0x180055da0`
- end: `0x180055f5d`
- name: `?AcquireTimeoutsMutex@UtcWatchdog@Diagnostics@Microsoft@@AEAA_NAEAV?$unique_lock@Vtimed_mutex@std@@@std@@@Z`
- size: `445`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d1a0`
- `0x18026bdd0`
- `0x18026c954`

## callees

- `0x180054a74`
- `0x180055614`
- `0x18005565c`
- `0x180055da0`
- `0x18005d660`
- `0x1801c2238`
- `0x1801ce4d8`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x180055e5e`
- `msvcp_win!_Mtx_lock` at `0x180055e5e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180055f37`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180055f43`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180055f37`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180055f43`
- `msvcp_win!_Mtx_unlock` at `0x180055ea5`
- `msvcp_win!_Mtx_unlock` at `0x180055ec3`
- `msvcp_win!_Mtx_unlock` at `0x180055ea5`
- `msvcp_win!_Mtx_unlock` at `0x180055ec3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180055f04`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180055f04`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180055ddb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180055ddb`

## string_xrefs

- `0x180055f14`: `onecore\base\telemetry\utc\service\include\UtcWatchdog.h`

## pseudocode

```c

```
