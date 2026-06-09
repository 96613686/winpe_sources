# CRdlsSqlTableVersion::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x180091180`
- end: `0x1800912b3`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableVersion@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `307`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableVersion *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180078be4`
- `0x180086778`
- `0x180091180`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180091260`
- `msvcrt!wprintf_s` at `0x180091275`
- `msvcrt!wprintf_s` at `0x180091260`
- `msvcrt!wprintf_s` at `0x180091275`

## string_xrefs

- `0x180091259`: `"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement"`
- `0x1800911d6`: `DELETE FROM [Rdls].[RdlsVersion] WHERE `
- `0x1800911ec`: `DELETE TOP (1) FROM [Rdls].[RdlsVersion] WHERE `

## pseudocode

```c

```
