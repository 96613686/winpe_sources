# __imp_load_EdpDllAllowFileAccessForProcess

- ea: `0x180002597`
- end: `0x1800025a3`
- name: `__imp_load_EdpDllAllowFileAccessForProcess`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180002597`

## pseudocode

```c
__int64 load_EdpDllAllowFileAccessForProcess()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002597  lea     rax, __imp_EdpDllAllowFileAccessForProcess
0x18000259e  jmp     __tailMerge_efscore_dll
```
