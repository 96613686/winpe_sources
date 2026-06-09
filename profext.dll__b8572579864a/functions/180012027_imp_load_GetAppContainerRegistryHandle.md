# __imp_load_GetAppContainerRegistryHandle

- ea: `0x180012027`
- end: `0x180012033`
- name: `__imp_load_GetAppContainerRegistryHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetAppContainerRegistryHandle` at `0x180012027`

## pseudocode

```c
__int64 load_GetAppContainerRegistryHandle()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180012027  lea     rax, __imp_GetAppContainerRegistryHandle
0x18001202e  jmp     __tailMerge_profapi_dll
```
