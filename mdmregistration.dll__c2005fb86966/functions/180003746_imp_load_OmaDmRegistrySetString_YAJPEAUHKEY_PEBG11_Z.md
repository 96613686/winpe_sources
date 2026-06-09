# __imp_load_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z

- ea: `0x180003746`
- end: `0x180003752`
- name: `__imp_load_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetString` at `0x180003746`

## pseudocode

```c
__int64 load__OmaDmRegistrySetString__YAJPEAUHKEY____PEBG11_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180003746  lea     rax, __imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000374d  jmp     __tailMerge_dmcmnutils_dll
```
