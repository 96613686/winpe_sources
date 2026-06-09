# __imp_load_?DmImpersonate@@YAJPEBG@Z

- ea: `0x1800036c8`
- end: `0x1800036d4`
- name: `__imp_load_?DmImpersonate@@YAJPEBG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmImpersonate` at `0x1800036c8`

## pseudocode

```c
__int64 load__DmImpersonate__YAJPEBG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x1800036c8  lea     rax, __imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800036cf  jmp     __tailMerge_dmcmnutils_dll
```
