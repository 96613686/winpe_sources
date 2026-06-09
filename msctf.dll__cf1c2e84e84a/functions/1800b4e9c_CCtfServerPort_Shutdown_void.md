# CCtfServerPort::Shutdown(void)

- ea: `0x1800b4e9c`
- end: `0x1800b5038`
- name: `?Shutdown@CCtfServerPort@@QEAAXXZ`
- size: `412`
- prototype: `void __fastcall(CCtfServerPort *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180082c60`
- `0x1800b455c`

## callees

- `0x18000f900`
- `0x180033e50`
- `0x18004e310`
- `0x180053660`
- `0x1800a18d4`
- `0x1800b4e9c`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800b4f83`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800b4f83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b500b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b500b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4fc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4fc1`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800b4ffa`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800b4ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5014`

## pseudocode

```c

```
