# ClientSideConnection::GetCacheMemorySectionWithRetry(CacheType,MemorySection *,ScopedHandle<EventHandlePolicy,void *> *)

- ea: `0x18012ad08`
- end: `0x18012af03`
- name: `?GetCacheMemorySectionWithRetry@ClientSideConnection@@QEAAJW4CacheType@@PEAVMemorySection@@PEAV?$ScopedHandle@UEventHandlePolicy@@PEAX@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(ClientSideConnection *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18012ac2c`

## callees

- `0x18012a85c`
- `0x18012ad08`
- `0x18012af0c`
- `0x18012af78`
- `0x18012b00c`
- `0x180212490`
- `0x180212f4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ad5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ad5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012add3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012add3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18012ae13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18012ae13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012ae73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aeb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012ae73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aeb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012aef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012adf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012aec9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012adf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012aec9`

## pseudocode

```c

```
