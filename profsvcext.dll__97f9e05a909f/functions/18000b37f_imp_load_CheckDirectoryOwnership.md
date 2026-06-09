# __imp_load_CheckDirectoryOwnership

- ea: `0x18000b37f`
- end: `0x18000b38b`
- name: `__imp_load_CheckDirectoryOwnership`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000afdd`

## import_xrefs

- `USERENV!__imp_CheckDirectoryOwnership` at `0x18000b37f`

## pseudocode

```c
__int64 load_CheckDirectoryOwnership()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000b37f  lea     rax, __imp_CheckDirectoryOwnership
0x18000b386  jmp     __tailMerge_userenv_dll
```
