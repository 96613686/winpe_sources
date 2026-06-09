# __imp_load_GetAppContainerPath

- ea: `0x180012093`
- end: `0x18001209f`
- name: `__imp_load_GetAppContainerPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetAppContainerPath` at `0x180012093`

## pseudocode

```c
__int64 load_GetAppContainerPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180012093  lea     rax, __imp_GetAppContainerPath
0x18001209a  jmp     __tailMerge_profapi_dll
```
