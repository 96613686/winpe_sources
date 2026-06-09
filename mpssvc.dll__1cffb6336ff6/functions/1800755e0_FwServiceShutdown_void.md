# FwServiceShutdown(void)

- ea: `0x1800755e0`
- end: `0x180075994`
- name: `?FwServiceShutdown@@YAXXZ`
- size: `948`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x1800753b0`
- `0x180076c20`

## callees

- `0x180009460`
- `0x18000a0c0`
- `0x180017110`
- `0x18004d58c`
- `0x18004d9b0`
- `0x18005cf9c`
- `0x180066564`
- `0x1800665f8`
- `0x180069cb8`
- `0x18006aa00`
- `0x18006b438`
- `0x18006f520`
- `0x180074cbc`
- `0x180075194`
- `0x1800755e0`
- `0x180078f24`
- `0x18007957c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180075950`
- `ntdll!EtwEventWrite` at `0x180075950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007586f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007586f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180075739`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18007585d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180075739`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18007585d`
- `fwbase!FwCriticalSectionDestroy` at `0x180075896`
- `fwbase!FwCriticalSectionDestroy` at `0x180075896`
- `fwbase!FwVerifyNoHeapLeaks` at `0x1800758b4`
- `fwbase!FwVerifyNoHeapLeaks` at `0x1800758b4`
- `fwbase!FwCriticalSectionEnter` at `0x180075815`
- `fwbase!FwCriticalSectionEnter` at `0x180075815`
- `fwbase!FwCriticalSectionLeave` at `0x180075822`
- `fwbase!FwCriticalSectionLeave` at `0x180075822`

## string_xrefs

- `0x18007563c`: `FwServiceShutdown`
- `0x180075875`: `FwServiceShutdown`
- `0x180075917`: `set_service_stopped`

## pseudocode

```c

```
