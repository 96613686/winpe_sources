# __imp_load_UuidCreate

- ea: `0x1800098b3`
- end: `0x1800098bf`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800087cd`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800098b3`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800098b3  lea     rax, __imp_UuidCreate
0x1800098ba  jmp     __tailMerge_rpcrt4_dll
```
