# JetMove(x,x,x,x)

- ea: `0x1002b638`
- end: `0x1002b63e`
- name: `_JetMove@16`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, int cRow, JET_GRBIT grbit)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10018b90`

## import_xrefs

- `msjet40!__imp__JetMove@16` at `0x1002b638`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetMove(JET_SESID sesid, JET_TABLEID tableid, int cRow, JET_GRBIT grbit)
{
  return __imp__JetMove@16(sesid, tableid, cRow, grbit);
}

```

## disassembly

```asm
0x1002b638  jmp     ds:__imp__JetMove@16
```
