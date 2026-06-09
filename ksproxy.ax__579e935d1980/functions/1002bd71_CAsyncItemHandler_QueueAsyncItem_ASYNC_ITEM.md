# CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)

- ea: `0x1002bd71`
- end: `0x1002be30`
- name: `?QueueAsyncItem@CAsyncItemHandler@@QAGKPAU_ASYNC_ITEM@@@Z`
- size: `191`
- prototype: `unsigned int(CAsyncItemHandler *__hidden this, struct _ASYNC_ITEM *)`
- caller_count: `13`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100150a0`
- `0x10017097`
- `0x100173a0`
- `0x10018250`
- `0x10018450`
- `0x1001a8f0`
- `0x1001cb15`
- `0x1001cd50`
- `0x1001ce70`
- `0x1001d6ae`
- `0x1001d8a0`
- `0x1001d9fe`
- `0x1001dfb0`

## callees

- `0x1001a001`
- `0x1002bd71`
- `0x1002c305`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1002bddd`
- `KERNEL32!SetEvent` at `0x1002bddd`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bd85`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bd94`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bda2`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bd85`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bd94`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002bda2`
- `KERNEL32!ReleaseMutex` at `0x1002be24`
- `KERNEL32!ReleaseMutex` at `0x1002be24`

## pseudocode

```c

```
