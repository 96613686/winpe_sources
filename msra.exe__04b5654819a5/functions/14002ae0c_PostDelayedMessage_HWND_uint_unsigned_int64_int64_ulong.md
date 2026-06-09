# PostDelayedMessage(HWND__ *,uint,unsigned __int64,__int64,ulong)

- ea: `0x14002ae0c`
- end: `0x14002aee4`
- name: `?PostDelayedMessage@@YAHPEAUHWND__@@I_K_JK@Z`
- size: `216`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140021d04`
- `0x1400223c4`
- `0x140031918`

## callees

- `0x14002ae0c`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!QueueUserWorkItem` at `0x14002aeb5`
- `KERNEL32!QueueUserWorkItem` at `0x14002aeb5`
- `KERNEL32!GetProcessHeap` at `0x14002ae20`
- `KERNEL32!GetProcessHeap` at `0x14002ae20`
- `KERNEL32!HeapAlloc` at `0x14002ae35`
- `KERNEL32!HeapAlloc` at `0x14002ae35`

## string_xrefs

- `0x14002ae5e`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c

```
