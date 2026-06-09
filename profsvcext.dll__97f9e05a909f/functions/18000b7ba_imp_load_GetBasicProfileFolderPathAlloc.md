# __imp_load_GetBasicProfileFolderPathAlloc

- ea: `0x18000b7ba`
- end: `0x18000b7c6`
- name: `__imp_load_GetBasicProfileFolderPathAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b73b`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000b7ba`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPathAlloc()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000b7ba  lea     rax, __imp_GetBasicProfileFolderPathAlloc
0x18000b7c1  jmp     __tailMerge_profapi_dll
```
