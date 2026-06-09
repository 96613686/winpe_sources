# AggregateWaitHandle::RemoveHandle(void *)

- ea: `0x180143800`
- end: `0x180143883`
- name: `?RemoveHandle@AggregateWaitHandle@@QEAAJPEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180141930`

## callees

- `0x1800f0df0`
- `0x180143800`

## import_xrefs

- `ntdll!NtCancelWaitCompletionPacket` at `0x18014382a`
- `ntdll!NtCancelWaitCompletionPacket` at `0x18014382a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180143838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180143838`

## pseudocode

```c

```
