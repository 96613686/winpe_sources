# NatConfigurationChangedCallbackRoutine(void *,uchar)

- ea: `0x1800799b0`
- end: `0x180079b21`
- name: `?NatConfigurationChangedCallbackRoutine@@YAXPEAXE@Z`
- size: `369`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007c648`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18004c214`
- `0x1800799b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800799ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800799ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079a45`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180079add`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180079add`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180079a91`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180079a91`

## pseudocode

```c

```
