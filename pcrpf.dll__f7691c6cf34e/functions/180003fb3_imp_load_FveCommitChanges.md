# __imp_load_FveCommitChanges

- ea: `0x180003fb3`
- end: `0x180003fbf`
- name: `__imp_load_FveCommitChanges`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003eec`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x180003fb3`

## pseudocode

```c
__int64 load_FveCommitChanges()
{
  return _tailMerge_fveapi_dll();
}

```

## disassembly

```asm
0x180003fb3  lea     rax, __imp_FveCommitChanges
0x180003fba  jmp     __tailMerge_fveapi_dll
```
