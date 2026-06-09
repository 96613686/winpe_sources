# CRdlsSqlTableRdlsSecrets::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x180093bd0`
- end: `0x180093cf5`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableRdlsSecrets@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `293`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableRdlsSecrets *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x180078be4`
- `0x180086778`
- `0x180093bd0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180093ca2`
- `msvcrt!wprintf_s` at `0x180093cb7`
- `msvcrt!wprintf_s` at `0x180093ca2`
- `msvcrt!wprintf_s` at `0x180093cb7`

## string_xrefs

- `0x180093c9b`: `"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement"`
- `0x180093c23`: `DELETE FROM [Rdls].[RdlsSecrets] `
- `0x180093c39`: `DELETE TOP (1) FROM [Rdls].[RdlsSecrets] `

## pseudocode

```c

```
