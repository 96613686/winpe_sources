# __imp_load_StgOpenStorage

- ea: `0x18000207b`
- end: `0x180002087`
- name: `__imp_load_StgOpenStorage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001f90`

## import_xrefs

- `ole32!StgOpenStorage` at `0x18000207b`

## pseudocode

```c
__int64 load_StgOpenStorage()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000207b  lea     rax, __imp_StgOpenStorage
0x180002082  jmp     __tailMerge_ole32_dll
```
