# JetPrepareUpdate(x,x,x)

- ea: `0x1002b66e`
- end: `0x1002b674`
- name: `_JetPrepareUpdate@12`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, unsigned int prep)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1001c680`

## import_xrefs

- `msjet40!__imp__JetPrepareUpdate@12` at `0x1002b66e`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetPrepareUpdate(JET_SESID sesid, JET_TABLEID tableid, unsigned int prep)
{
  return __imp__JetPrepareUpdate@12(sesid, tableid, prep);
}

```

## disassembly

```asm
0x1002b66e  jmp     ds:__imp__JetPrepareUpdate@12
```
