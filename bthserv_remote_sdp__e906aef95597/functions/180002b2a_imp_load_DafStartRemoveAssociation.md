# __imp_load_DafStartRemoveAssociation

- ea: `0x180002b2a`
- end: `0x180002b36`
- name: `__imp_load_DafStartRemoveAssociation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002a99`

## import_xrefs

- `deviceassociation!DafStartRemoveAssociation` at `0x180002b2a`

## pseudocode

```c
__int64 load_DafStartRemoveAssociation()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x180002b2a  lea     rax, __imp_DafStartRemoveAssociation
0x180002b31  jmp     __tailMerge_deviceassociation_dll
```
