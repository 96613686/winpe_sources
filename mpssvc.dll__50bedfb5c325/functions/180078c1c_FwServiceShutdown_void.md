# FwServiceShutdown(void)

- ea: `0x180078c1c`
- end: `0x180079007`
- name: `?FwServiceShutdown@@YAXXZ`
- size: `1003`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x1800789c0`
- `0x18007a360`

## callees

- `0x180008a80`
- `0x1800097b0`
- `0x1800192e0`
- `0x1800508b4`
- `0x180050cd8`
- `0x180061c90`
- `0x18006a8a8`
- `0x18006a964`
- `0x18006ca20`
- `0x18006da64`
- `0x18006e614`
- `0x1800729c0`
- `0x180078248`
- `0x180078770`
- `0x180078c1c`
- `0x18007caf0`
- `0x18007d1d8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180078fbc`
- `ntdll!EtwEventWrite` at `0x180078fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078ec9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180078d75`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180078eb1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180078d75`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180078eb1`
- `fwbase!FwCriticalSectionDestroy` at `0x180078ef6`
- `fwbase!FwCriticalSectionDestroy` at `0x180078ef6`
- `fwbase!FwVerifyNoHeapLeaks` at `0x180078f1a`
- `fwbase!FwVerifyNoHeapLeaks` at `0x180078f1a`
- `fwbase!FwCriticalSectionEnter` at `0x180078e57`
- `fwbase!FwCriticalSectionEnter` at `0x180078e57`
- `fwbase!FwCriticalSectionLeave` at `0x180078e6a`
- `fwbase!FwCriticalSectionLeave` at `0x180078e6a`

## string_xrefs

- `0x180078c78`: `FwServiceShutdown`
- `0x180078ed5`: `FwServiceShutdown`
- `0x180078f83`: `set_service_stopped`

## pseudocode

```c

```
