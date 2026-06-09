# JetCloseTable(x,x)

- ea: `0x1002b620`
- end: `0x1002b626`
- name: `_JetCloseTable@8`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid)`
- caller_count: `5`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10018b90`
- `0x1001ba80`
- `0x1001c060`
- `0x1001c250`
- `0x1001ca20`

## import_xrefs

- `msjet40!__imp__JetCloseTable@8` at `0x1002b620`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetCloseTable(JET_SESID sesid, JET_TABLEID tableid)
{
  return __imp__JetCloseTable@8(sesid, tableid);
}

```

## disassembly

```asm
0x1002b620  jmp     ds:__imp__JetCloseTable@8
```
