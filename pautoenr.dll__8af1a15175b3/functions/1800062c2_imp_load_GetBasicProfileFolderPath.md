# __imp_load_GetBasicProfileFolderPath

- ea: `0x1800062c2`
- end: `0x1800062ce`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006243`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800062c2`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x1800062c2  lea     rax, __imp_GetBasicProfileFolderPath
0x1800062c9  jmp     __tailMerge_profapi_dll
```
