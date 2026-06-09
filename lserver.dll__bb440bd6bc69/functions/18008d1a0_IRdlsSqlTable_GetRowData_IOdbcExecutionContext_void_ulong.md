# IRdlsSqlTable::GetRowData(IOdbcExecutionContext *,void *,ulong)

- ea: `0x18008d1a0`
- end: `0x18008d2a1`
- name: `?GetRowData@IRdlsSqlTable@@IEAAJPEAVIOdbcExecutionContext@@PEAXK@Z`
- size: `257`
- prototype: `__int64 __fastcall(IRdlsSqlTable *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18008d110`
- `0x18008f5c0`
- `0x180091040`
- `0x180091c50`
- `0x180092a70`
- `0x180093950`
- `0x180094f00`

## callees

- `0x180005665`
- `0x18008d1a0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18008d255`
- `msvcrt!wprintf_s` at `0x18008d26a`
- `msvcrt!wprintf_s` at `0x18008d255`
- `msvcrt!wprintf_s` at `0x18008d26a`
- `KERNEL32!LocalAlloc` at `0x18008d1d8`
- `KERNEL32!LocalAlloc` at `0x18008d1d8`
- `KERNEL32!LocalFree` at `0x18008d279`
- `KERNEL32!LocalFree` at `0x18008d279`

## string_xrefs

- `0x18008d24e`: `"m_pOdbcExecContext->GetNextRow, ReadData"`
- `0x18008d226`: `"MapColumnBindingInfo, ReadData"`

## pseudocode

```c

```
