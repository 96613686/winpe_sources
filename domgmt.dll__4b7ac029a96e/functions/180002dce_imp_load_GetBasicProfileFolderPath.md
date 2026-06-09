# __imp_load_GetBasicProfileFolderPath

- ea: `0x180002dce`
- end: `0x180002dda`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002d4f`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180002dce`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180002dce  lea     rax, __imp_GetBasicProfileFolderPath
0x180002dd5  jmp     __tailMerge_profapi_dll
```
