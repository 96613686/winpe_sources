# __imp_load_EfsDllDecryptFek

- ea: `0x18000293b`
- end: `0x180002947`
- name: `__imp_load_EfsDllDecryptFek`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EfsDllDecryptFek` at `0x18000293b`

## pseudocode

```c
__int64 load_EfsDllDecryptFek()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x18000293b  lea     rax, __imp_EfsDllDecryptFek
0x180002942  jmp     __tailMerge_efscore_dll
```
