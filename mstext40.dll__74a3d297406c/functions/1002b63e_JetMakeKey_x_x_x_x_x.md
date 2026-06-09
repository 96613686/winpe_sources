# JetMakeKey(x,x,x,x,x)

- ea: `0x1002b63e`
- end: `0x1002b644`
- name: `_JetMakeKey@20`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, const void *pvData, unsigned int cbData, JET_GRBIT grbit)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10018b90`
- `0x1001c060`

## import_xrefs

- `msjet40!__imp__JetMakeKey@20` at `0x1002b63e`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetMakeKey(
        JET_SESID sesid,
        JET_TABLEID tableid,
        const void *pvData,
        unsigned int cbData,
        JET_GRBIT grbit)
{
  return __imp__JetMakeKey@20(sesid, tableid, pvData, cbData, grbit);
}

```

## disassembly

```asm
0x1002b63e  jmp     ds:__imp__JetMakeKey@20
```
