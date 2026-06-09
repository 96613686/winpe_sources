# __imp_load_UuidCreate

- ea: `0x18001537d`
- end: `0x180015389`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800152ec`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001537d`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001537d  lea     rax, __imp_UuidCreate
0x180015384  jmp     __tailMerge_rpcrt4_dll
```
