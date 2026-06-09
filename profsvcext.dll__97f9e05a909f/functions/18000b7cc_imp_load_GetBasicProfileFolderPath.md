# __imp_load_GetBasicProfileFolderPath

- ea: `0x18000b7cc`
- end: `0x18000b7d8`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b73b`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000b7cc`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000b7cc  lea     rax, __imp_GetBasicProfileFolderPath
0x18000b7d3  jmp     __tailMerge_profapi_dll
```
