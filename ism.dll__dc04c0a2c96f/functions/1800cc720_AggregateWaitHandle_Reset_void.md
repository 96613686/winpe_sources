# AggregateWaitHandle::Reset(void)

- ea: `0x1800cc720`
- end: `0x1800cc782`
- name: `?Reset@AggregateWaitHandle@@QEAAXXZ`
- size: `98`
- prototype: `void __fastcall(AggregateWaitHandle *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801418e0`
- `0x180142f90`

## callees

- `0x1800cc720`
- `0x1800cc788`
- `0x1800f0df0`

## import_xrefs

- `ntdll!NtCancelWaitCompletionPacket` at `0x1800cc744`
- `ntdll!NtCancelWaitCompletionPacket` at `0x1800cc744`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc74e`

## pseudocode

```c

```
