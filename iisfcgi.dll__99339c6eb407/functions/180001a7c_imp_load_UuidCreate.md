# __imp_load_UuidCreate

- ea: `0x180001a7c`
- end: `0x180001a88`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019fd`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180001a7c`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001a7c  lea     rax, __imp_UuidCreate
0x180001a83  jmp     __tailMerge_rpcrt4_dll
```
