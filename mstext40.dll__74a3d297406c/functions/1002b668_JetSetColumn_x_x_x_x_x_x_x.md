# JetSetColumn(x,x,x,x,x,x,x)

- ea: `0x1002b668`
- end: `0x1002b66e`
- name: `_JetSetColumn@28`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, const void *pvData, unsigned int cbData, JET_GRBIT grbit, JET_SETINFO *psetinfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1001c680`

## import_xrefs

- `msjet40!__imp__JetSetColumn@28` at `0x1002b668`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetSetColumn(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        const void *pvData,
        unsigned int cbData,
        JET_GRBIT grbit,
        JET_SETINFO *psetinfo)
{
  return __imp__JetSetColumn@28(sesid, tableid, columnid, pvData, cbData, grbit, psetinfo);
}

```

## disassembly

```asm
0x1002b668  jmp     ds:__imp__JetSetColumn@28
```
