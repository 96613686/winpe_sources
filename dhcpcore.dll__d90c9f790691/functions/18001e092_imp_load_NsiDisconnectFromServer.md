# __imp_load_NsiDisconnectFromServer

- ea: `0x18001e092`
- end: `0x18001e09e`
- name: `__imp_load_NsiDisconnectFromServer`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001e001`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18001e092`

## pseudocode

```c
__int64 load_NsiDisconnectFromServer()
{
  return _tailMerge_winnsi_dll();
}

```

## disassembly

```asm
0x18001e092  lea     rax, __imp_NsiDisconnectFromServer
0x18001e099  jmp     __tailMerge_winnsi_dll
```
