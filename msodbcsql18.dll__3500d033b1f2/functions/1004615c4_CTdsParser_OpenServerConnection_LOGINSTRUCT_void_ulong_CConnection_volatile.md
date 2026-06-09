# CTdsParser::OpenServerConnection(_LOGINSTRUCT *,void *,ulong,CConnection * volatile *)

- ea: `0x1004615c4`
- end: `0x100461761`
- name: `?OpenServerConnection@CTdsParser@@QEAAJPEAU_LOGINSTRUCT@@PEAXKPECREAVCConnection@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(CTdsParser *__hidden this, struct _LOGINSTRUCT *, void *, unsigned int, struct CConnection *volatile *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x10048c98c`
- `0x1004e5b60`

## callees

- `0x1004611d0`
- `0x1004615c4`
- `0x100546a24`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!QueueUserWorkItem` at `0x100461682`
- `KERNEL32!QueueUserWorkItem` at `0x100461682`
- `KERNEL32!GetLastError` at `0x100461695`
- `KERNEL32!GetLastError` at `0x1004616bc`
- `KERNEL32!GetLastError` at `0x100461695`
- `KERNEL32!GetLastError` at `0x1004616bc`

## pseudocode

```c

```
