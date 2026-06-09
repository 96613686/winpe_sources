# CRdlsSqlTableBackupSource::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x180092bf0`
- end: `0x180092d41`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableBackupSource@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `337`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableBackupSource *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180078be4`
- `0x180086778`
- `0x180092bf0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180092ceb`
- `msvcrt!wprintf_s` at `0x180092d00`
- `msvcrt!wprintf_s` at `0x180092ceb`
- `msvcrt!wprintf_s` at `0x180092d00`

## string_xrefs

- `0x180092ce4`: `"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement"`
- `0x180092c58`: `DELETE TOP (1) FROM [Rdls].[BackupSource] `
- `0x180092c42`: `DELETE FROM [Rdls].[BackupSource] `

## pseudocode

```c

```
