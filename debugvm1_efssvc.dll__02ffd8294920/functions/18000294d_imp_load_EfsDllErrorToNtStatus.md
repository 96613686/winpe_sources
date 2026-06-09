# __imp_load_EfsDllErrorToNtStatus

- ea: `0x18000294d`
- end: `0x180002959`
- name: `__imp_load_EfsDllErrorToNtStatus`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000294d`

## pseudocode

```c
__int64 load_EfsDllErrorToNtStatus()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000294d  lea     rax, __imp_EfsDllErrorToNtStatus
0x180002954  jmp     __tailMerge_efscore_dll
```
