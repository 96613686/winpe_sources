# __imp_load_GetBasicProfileFolderPath

- ea: `0x180005b9f`
- end: `0x180005bab`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005b20`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180005b9f`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180005b9f  lea     rax, __imp_GetBasicProfileFolderPath
0x180005ba6  jmp     __tailMerge_profapi_dll
```
