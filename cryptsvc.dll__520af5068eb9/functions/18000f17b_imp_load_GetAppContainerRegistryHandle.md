# __imp_load_GetAppContainerRegistryHandle

- ea: `0x18000f17b`
- end: `0x18000f187`
- name: `__imp_load_GetAppContainerRegistryHandle`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f0ea`

## import_xrefs

- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18000f17b`

## pseudocode

```c
__int64 load_GetAppContainerRegistryHandle()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18000f17b  lea     rax, __imp_GetAppContainerRegistryHandle
0x18000f182  jmp     __tailMerge_profapi_dll
```
