# DAS::DevnodeManagment::DevnodeFactory::SetupWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002cb60`
- end: `0x18002cc8b`
- name: `?SetupWorkCallback@DevnodeFactory@DevnodeManagment@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `299`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x1800186ac`
- `0x18002482c`
- `0x18002cb60`
- `0x18002cc94`
- `0x18002d070`
- `0x18002d09c`
- `0x18002d448`
- `0x180045df0`
- `0x18005d1a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002cbdb`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002cbdb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002cbee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002cbee`

## string_xrefs

- `0x18002cc66`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c

```
