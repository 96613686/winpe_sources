# JetSeek(x,x,x)

- ea: `0x1002b644`
- end: `0x1002b64a`
- name: `_JetSeek@12`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_GRBIT grbit)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10018b90`
- `0x1001c060`

## import_xrefs

- `msjet40!__imp__JetSeek@12` at `0x1002b644`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetSeek(JET_SESID sesid, JET_TABLEID tableid, JET_GRBIT grbit)
{
  return __imp__JetSeek@12(sesid, tableid, grbit);
}

```

## disassembly

```asm
0x1002b644  jmp     ds:__imp__JetSeek@12
```
