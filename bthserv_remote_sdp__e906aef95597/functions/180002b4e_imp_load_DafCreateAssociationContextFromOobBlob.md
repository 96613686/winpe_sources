# __imp_load_DafCreateAssociationContextFromOobBlob

- ea: `0x180002b4e`
- end: `0x180002b5a`
- name: `__imp_load_DafCreateAssociationContextFromOobBlob`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002a99`

## import_xrefs

- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x180002b4e`

## pseudocode

```c
__int64 load_DafCreateAssociationContextFromOobBlob()
{
  return _tailMerge_deviceassociation_dll();
}

```

## disassembly

```asm
0x180002b4e  lea     rax, __imp_DafCreateAssociationContextFromOobBlob
0x180002b55  jmp     __tailMerge_deviceassociation_dll
```
