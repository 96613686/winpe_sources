# __imp_load_GetLongProfilePathName

- ea: `0x18000b221`
- end: `0x18000b22d`
- name: `__imp_load_GetLongProfilePathName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000afdd`

## import_xrefs

- `USERENV!__imp_GetLongProfilePathName` at `0x18000b221`

## pseudocode

```c
__int64 load_GetLongProfilePathName()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000b221  lea     rax, __imp_GetLongProfilePathName
0x18000b228  jmp     __tailMerge_userenv_dll
```
