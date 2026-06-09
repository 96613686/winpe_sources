# JetUpdate(x,x,x,x,x)

- ea: `0x1002b662`
- end: `0x1002b668`
- name: `_JetUpdate@20`
- size: `6`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvBookmark, unsigned int cbBookmark, unsigned int *pcbActual)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1001c680`

## import_xrefs

- `msjet40!__imp__JetUpdate@20` at `0x1002b662`

## pseudocode

```c
// attributes: thunk
JET_ERR __stdcall JetUpdate(
        JET_SESID sesid,
        JET_TABLEID tableid,
        void *pvBookmark,
        unsigned int cbBookmark,
        unsigned int *pcbActual)
{
  return __imp__JetUpdate@20(sesid, tableid, pvBookmark, cbBookmark, pcbActual);
}

```

## disassembly

```asm
0x1002b662  jmp     ds:__imp__JetUpdate@20
```
