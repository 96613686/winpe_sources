# __imp_load_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z

- ea: `0x18000377c`
- end: `0x180003788`
- name: `__imp_load_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x18000377c`

## pseudocode

```c
__int64 load__OmDmRegistryAllocAndGetString__YAJPEAUHKEY____PEBGW4AllocFunction__PEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000377c  lea     rax, __imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x180003783  jmp     __tailMerge_dmcmnutils_dll
```
