# __imp_load_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z

- ea: `0x180003758`
- end: `0x180003764`
- name: `__imp_load_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180003758`

## pseudocode

```c
__int64 load__OmaDmRegistryGetDWORD__YAJPEAUHKEY____PEBG1PEAK_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180003758  lea     rax, __imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000375f  jmp     __tailMerge_dmcmnutils_dll
```
