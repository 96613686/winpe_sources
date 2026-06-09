# __imp_load_DafCreateAssociationContext

- ea: `0x180002b18`
- end: `0x180002b24`
- name: `__imp_load_DafCreateAssociationContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002a99`

## import_xrefs

- `deviceassociation!DafCreateAssociationContext` at `0x180002b18`

## pseudocode

```c
__int64 load_DafCreateAssociationContext()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x180002b18  lea     rax, __imp_DafCreateAssociationContext
0x180002b1f  jmp     __tailMerge_deviceassociation_dll
```
