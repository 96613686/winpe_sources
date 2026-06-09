# NatConfigurationChangedCallbackRoutine(void *,uchar)

- ea: `0x18007fa60`
- end: `0x18007fbf0`
- name: `?NatConfigurationChangedCallbackRoutine@@YAXPEAXE@Z`
- size: `400`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082978`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18004ff48`
- `0x18007fa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007faaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007faaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fac8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fb01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fac8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007fb01`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007fba5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007fba5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007fb53`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007fb53`

## pseudocode

```c

```
