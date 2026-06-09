# __imp_load_UuidCreate

- ea: `0x180014456`
- end: `0x180014462`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800143d7`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180014456`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180014456  lea     rax, __imp_UuidCreate
0x18001445d  jmp     __tailMerge_rpcrt4_dll
```
