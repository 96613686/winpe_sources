# ThreadContext::AddRecyclerCollectCallBack(void (*)(void *,RecyclerCollectCallBackFlags),void *)

- ea: `0x1802ae1a4`
- end: `0x1802ae25d`
- name: `?AddRecyclerCollectCallBack@ThreadContext@@QEAAPEAUCollectCallBack@1@P6AXPEAXW4RecyclerCollectCallBackFlags@@@Z0@Z`
- size: `185`
- prototype: `struct ThreadContext::CollectCallBack *__fastcall(ThreadContext *__hidden this, void (__high *)(void *, enum RecyclerCollectCallBackFlags), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1801fd100`
- `0x18020a9c8`

## callees

- `0x180107364`
- `0x1802ae1a4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1802ae1d3`
- `KERNEL32!EnterCriticalSection` at `0x1802ae1d3`
- `KERNEL32!LeaveCriticalSection` at `0x1802ae24b`
- `KERNEL32!LeaveCriticalSection` at `0x1802ae24b`

## pseudocode

```c

```
