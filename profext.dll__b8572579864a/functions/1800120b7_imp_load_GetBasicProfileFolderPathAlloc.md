# __imp_load_GetBasicProfileFolderPathAlloc

- ea: `0x1800120b7`
- end: `0x1800120c3`
- name: `__imp_load_GetBasicProfileFolderPathAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800120b7`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPathAlloc()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x1800120b7  lea     rax, __imp_GetBasicProfileFolderPathAlloc
0x1800120be  jmp     __tailMerge_profapi_dll
```
