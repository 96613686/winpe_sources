# __imp_load_EfsDllOefsReleaseExclusiveOperation

- ea: `0x180002625`
- end: `0x180002631`
- name: `__imp_load_EfsDllOefsReleaseExclusiveOperation`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800025a6`

## import_xrefs

- `EFSCORE!EfsDllOefsReleaseExclusiveOperation` at `0x180002625`

## pseudocode

```c
__int64 load_EfsDllOefsReleaseExclusiveOperation()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002625  lea     rax, __imp_EfsDllOefsReleaseExclusiveOperation
0x18000262c  jmp     __tailMerge_efscore_dll
```
