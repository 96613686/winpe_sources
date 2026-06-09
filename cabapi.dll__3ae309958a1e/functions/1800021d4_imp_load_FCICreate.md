# __imp_load_FCICreate

- ea: `0x1800021d4`
- end: `0x1800021e0`
- name: `__imp_load_FCICreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000210d`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x1800021d4`

## pseudocode

```c
__int64 load_FCICreate()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x1800021d4  lea     rax, __imp_FCICreate
0x1800021db  jmp     __tailMerge_cabinet_dll
```
