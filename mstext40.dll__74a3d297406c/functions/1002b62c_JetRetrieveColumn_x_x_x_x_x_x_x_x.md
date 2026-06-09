# JetRetrieveColumn(x,x,x,x,x,x,x,x)

- ea: `0x1002b62c`
- end: `0x1002b632`
- name: `_JetRetrieveColumn@32`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, void *pvData, unsigned int cbData, unsigned int *pcbActual, JET_GRBIT grbit, JET_RETINFO *pretinfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10018b90`

## import_xrefs

- `msjet40!__imp__JetRetrieveColumn@32` at `0x1002b62c`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetRetrieveColumn(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        void *pvData,
        unsigned int cbData,
        unsigned int *pcbActual,
        JET_GRBIT grbit,
        JET_RETINFO *pretinfo)
{
  return __imp__JetRetrieveColumn@32(sesid, tableid, columnid, pvData, cbData, pcbActual, grbit, pretinfo);
}

```

## disassembly

```asm
0x1002b62c  jmp     ds:__imp__JetRetrieveColumn@32
```
