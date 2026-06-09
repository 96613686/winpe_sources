# __imp_load_IriCreateFromString

- ea: `0x18000487d`
- end: `0x180004889`
- name: `__imp_load_IriCreateFromString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800047fe`

## import_xrefs

- `iri!__imp_IriCreateFromString` at `0x18000487d`

## pseudocode

```c
__int64 load_IriCreateFromString()
{
  return _tailMerge_iri_dll();
}

```

## disassembly

```asm
0x18000487d  lea     rax, __imp_IriCreateFromString
0x180004884  jmp     __tailMerge_iri_dll
```
