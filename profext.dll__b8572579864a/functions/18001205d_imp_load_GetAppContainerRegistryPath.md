# __imp_load_GetAppContainerRegistryPath

- ea: `0x18001205d`
- end: `0x180012069`
- name: `__imp_load_GetAppContainerRegistryPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_GetAppContainerRegistryPath` at `0x18001205d`

## pseudocode

```c
__int64 load_GetAppContainerRegistryPath()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18001205d  lea     rax, __imp_GetAppContainerRegistryPath
0x180012064  jmp     __tailMerge_profapi_dll
```
