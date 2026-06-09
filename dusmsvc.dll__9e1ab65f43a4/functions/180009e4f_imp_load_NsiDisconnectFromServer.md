# __imp_load_NsiDisconnectFromServer

- ea: `0x180009e4f`
- end: `0x180009e5b`
- name: `__imp_load_NsiDisconnectFromServer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180009cfd`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x180009e4f`

## pseudocode

```c
__int64 load_NsiDisconnectFromServer()
{
  return _tailMerge_winnsi_dll();
}

```

## disassembly

```asm
0x180009e4f  lea     rax, __imp_NsiDisconnectFromServer
0x180009e56  jmp     __tailMerge_winnsi_dll
```
