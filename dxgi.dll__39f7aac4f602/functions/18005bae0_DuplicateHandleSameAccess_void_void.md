# DuplicateHandleSameAccess(void *,void * *)

- ea: `0x18005bae0`
- end: `0x18005bb60`
- name: `?DuplicateHandleSameAccess@@YAJPEAXPEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, LPHANDLE lpTargetHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d2fc`
- `0x1800a0880`

## callees

- `0x18005bae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bb10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bb19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bb10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005bb19`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005bb3f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005bb3f`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x18005bafc`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x18005bafc`

## pseudocode

```c

```
