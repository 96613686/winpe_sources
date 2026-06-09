# CTdsParser::OpenServerConnection(_LOGINSTRUCT *,void *,ulong,CConnection * volatile *)

- ea: `0x180195410`
- end: `0x180195667`
- name: `?OpenServerConnection@CTdsParser@@QEAAJPEAU_LOGINSTRUCT@@PEAXKPECREAVCConnection@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(CTdsParser *__hidden this, struct _LOGINSTRUCT *, void *, unsigned int, struct CConnection *volatile *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180010b00`
- `0x18001bd40`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003824`
- `0x180012010`
- `0x180195030`
- `0x180195410`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180195553`
- `KERNEL32!GetLastError` at `0x18019557d`
- `KERNEL32!GetLastError` at `0x180195553`
- `KERNEL32!GetLastError` at `0x18019557d`
- `KERNEL32!QueueUserWorkItem` at `0x18019553c`
- `KERNEL32!QueueUserWorkItem` at `0x18019553c`
- `KERNEL32!CloseHandle` at `0x1801955a4`
- `KERNEL32!CloseHandle` at `0x1801955a4`

## pseudocode

```c

```
