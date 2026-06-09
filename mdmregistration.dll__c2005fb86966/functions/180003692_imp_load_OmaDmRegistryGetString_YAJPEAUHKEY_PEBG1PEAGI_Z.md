# __imp_load_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z

- ea: `0x180003692`
- end: `0x18000369e`
- name: `__imp_load_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x180003692`

## pseudocode

```c
__int64 load__OmaDmRegistryGetString__YAJPEAUHKEY____PEBG1PEAGI_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180003692  lea     rax, __imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180003699  jmp     __tailMerge_dmcmnutils_dll
```
