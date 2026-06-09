# PipeManager::CloseAndReleasePipeIfOpen(PipeManager::PipeImplementation *)

- ea: `0x1800ec1c8`
- end: `0x1800ec22f`
- name: `?CloseAndReleasePipeIfOpen@PipeManager@@AEAAXPEAVPipeImplementation@1@@Z`
- size: `103`
- prototype: `void __fastcall(PipeManager *__hidden this, struct PipeManager::PipeImplementation *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ebf7c`
- `0x1800ecb60`
- `0x1800eccc0`

## callees

- `0x1800ec1c8`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec20f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec20f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec1df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec1df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec1fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec1fd`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800ec1f3`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800ec1f3`

## pseudocode

```c

```
