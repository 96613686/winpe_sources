# CJobManagerExternal::GetJobInternal(_GUID const &,IBackgroundCopyJob * *)

- ea: `0x18000a9dc`
- end: `0x18000acd9`
- name: `?GetJobInternal@CJobManagerExternal@@QEAAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(CJobManagerExternal *this, const struct _GUID *, struct IBackgroundCopyJob **, void (*)(void))`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005cec0`

## callees

- `0x18000a680`
- `0x18000a9dc`
- `0x18000c2d0`
- `0x18000c520`
- `0x180031d74`
- `0x180070038`
- `0x18009d024`
- `0x1800ab7fc`
- `0x1800b1cbc`
- `0x1800b1eb8`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000abc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000abc0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ac71`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ac71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abf8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000abf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ac80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ac80`

## pseudocode

```c

```
