# HsmiOpCompleteOperation

- ea: `0x14006f1a0`
- end: `0x14006f251`
- name: `HsmiOpCompleteOperation`
- size: `177`
- prototype: `void __fastcall(__int64, struct _KEVENT *, __int64, __int64, struct _KEVENT *Context, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140047c20`

## callees

- `0x14006f1a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14006f1e8`
- `ntoskrnl!KeSetEvent` at `0x14006f22e`
- `ntoskrnl!KeSetEvent` at `0x14006f1e8`
- `ntoskrnl!KeSetEvent` at `0x14006f22e`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f240`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f240`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f20d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006f20d`
- `FLTMGR!FltReleaseContext` at `0x14006f1f9`
- `FLTMGR!FltReleaseContext` at `0x14006f1f9`

## pseudocode

```c

```
