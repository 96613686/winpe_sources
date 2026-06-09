# ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::StopSession(void)

- ea: `0x18009b5dc`
- end: `0x18009b730`
- name: `?StopSession@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@QEAAXXZ`
- size: `340`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18009b54c`
- `0x1800ea794`
- `0x1800f0c88`

## callees

- `0x18009b5dc`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800f14e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009b6cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009b6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b6fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b6fe`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009b64f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009b64f`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009b690`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009b690`

## string_xrefs

- `0x18009b6a9`: `CloseTrace failed [%u] - thus will not unblock the APC thread processing events`
- `0x18009b66c`: `ctEtwReader::StopSession - ControlTrace failed [%u] : cannot stop the trace session`
- `0x18009b6df`: `Failed waiting on ctEtwReader::StopSession thread to stop [%u - gle %u]`

## pseudocode

```c

```
