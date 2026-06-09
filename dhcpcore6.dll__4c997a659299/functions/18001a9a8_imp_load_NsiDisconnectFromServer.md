# __imp_load_NsiDisconnectFromServer

- ea: `0x18001a9a8`
- end: `0x18001a9b4`
- name: `__imp_load_NsiDisconnectFromServer`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001a917`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18001a9a8`

## pseudocode

```c
__int64 load_NsiDisconnectFromServer()
{
  return _tailMerge_winnsi_dll();
}

```

## disassembly

```asm
0x18001a9a8  lea     rax, __imp_NsiDisconnectFromServer
0x18001a9af  jmp     __tailMerge_winnsi_dll
```
