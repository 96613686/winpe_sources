# __imp_load_GetBasicProfileFolderPath

- ea: `0x18000f169`
- end: `0x18000f175`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f0ea`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000f169`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000f169  lea     rax, __imp_GetBasicProfileFolderPath
0x18000f170  jmp     __tailMerge_profapi_dll
```
