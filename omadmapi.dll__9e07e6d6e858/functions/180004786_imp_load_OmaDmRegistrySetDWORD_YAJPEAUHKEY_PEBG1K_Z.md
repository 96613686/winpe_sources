# __imp_load_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z

- ea: `0x180004786`
- end: `0x180004792`
- name: `__imp_load_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180004786`

## pseudocode

```c
__int64 load__OmaDmRegistrySetDWORD__YAJPEAUHKEY____PEBG1K_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004786  lea     rax, __imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000478d  jmp     __tailMerge_dmcmnutils_dll
```
