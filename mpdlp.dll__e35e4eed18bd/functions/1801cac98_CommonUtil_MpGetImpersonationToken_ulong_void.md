# CommonUtil::MpGetImpersonationToken(ulong,void * *)

- ea: `0x1801cac98`
- end: `0x1801cadc4`
- name: `?MpGetImpersonationToken@CommonUtil@@YAJKPEAPEAX@Z`
- size: `300`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800469e0`
- `0x18014e9b0`
- `0x1801ef00c`

## callees

- `0x1800809d0`
- `0x180105f50`
- `0x180106cc4`
- `0x18010cb40`
- `0x1801cac98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801cad0e`
- `KERNEL32!CloseHandle` at `0x1801cad7e`
- `KERNEL32!CloseHandle` at `0x1801cada4`
- `KERNEL32!CloseHandle` at `0x1801cad0e`
- `KERNEL32!CloseHandle` at `0x1801cad7e`
- `KERNEL32!CloseHandle` at `0x1801cada4`
- `WTSAPI32!WTSQueryUserToken` at `0x1801cacc2`
- `WTSAPI32!WTSQueryUserToken` at `0x1801cacc2`

## pseudocode

```c

```
