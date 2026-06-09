# __imp_load_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z

- ea: `0x18000376a`
- end: `0x180003776`
- name: `__imp_load_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x18000376a`

## pseudocode

```c
__int64 load__OmaDmRegistryDeleteValue__YAJPEAUHKEY____PEBG1_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000376a  lea     rax, __imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180003771  jmp     __tailMerge_dmcmnutils_dll
```
