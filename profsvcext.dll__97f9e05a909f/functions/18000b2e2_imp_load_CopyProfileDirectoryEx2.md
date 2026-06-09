# __imp_load_CopyProfileDirectoryEx2

- ea: `0x18000b2e2`
- end: `0x18000b2ee`
- name: `__imp_load_CopyProfileDirectoryEx2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000afdd`

## import_xrefs

- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x18000b2e2`

## pseudocode

```c
__int64 load_CopyProfileDirectoryEx2()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000b2e2  lea     rax, __imp_CopyProfileDirectoryEx2
0x18000b2e9  jmp     __tailMerge_userenv_dll
```
