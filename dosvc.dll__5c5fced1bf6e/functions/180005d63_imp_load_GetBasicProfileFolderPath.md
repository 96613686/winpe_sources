# __imp_load_GetBasicProfileFolderPath

- ea: `0x180005d63`
- end: `0x180005d6f`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005ce4`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180005d63`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180005d63  lea     rax, __imp_GetBasicProfileFolderPath
0x180005d6a  jmp     __tailMerge_profapi_dll
```
