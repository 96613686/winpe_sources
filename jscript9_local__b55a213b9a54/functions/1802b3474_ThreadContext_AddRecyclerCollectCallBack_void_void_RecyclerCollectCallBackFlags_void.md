# ThreadContext::AddRecyclerCollectCallBack(void (*)(void *,RecyclerCollectCallBackFlags),void *)

- ea: `0x1802b3474`
- end: `0x1802b353a`
- name: `?AddRecyclerCollectCallBack@ThreadContext@@QEAAPEAUCollectCallBack@1@P6AXPEAXW4RecyclerCollectCallBackFlags@@@Z0@Z`
- size: `198`
- prototype: `struct ThreadContext::CollectCallBack *__fastcall(ThreadContext *__hidden this, void (__high *)(void *, enum RecyclerCollectCallBackFlags), void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1802003a0`
- `0x18020dfb8`

## callees

- `0x18012dca4`
- `0x1802b3474`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1802b34a3`
- `KERNEL32!EnterCriticalSection` at `0x1802b34a3`
- `KERNEL32!LeaveCriticalSection` at `0x1802b3521`
- `KERNEL32!LeaveCriticalSection` at `0x1802b3521`

## pseudocode

```c

```
