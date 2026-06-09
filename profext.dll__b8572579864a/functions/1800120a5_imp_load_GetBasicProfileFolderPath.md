# __imp_load_GetBasicProfileFolderPath

- ea: `0x1800120a5`
- end: `0x1800120b1`
- name: `__imp_load_GetBasicProfileFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800120a5`

## pseudocode

```c
__int64 load_GetBasicProfileFolderPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x1800120a5  lea     rax, __imp_GetBasicProfileFolderPath
0x1800120ac  jmp     __tailMerge_profapi_dll
```
