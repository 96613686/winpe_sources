# __imp_load_EdpDllAllowFileAccessForProcess

- ea: `0x180002567`
- end: `0x180002573`
- name: `__imp_load_EdpDllAllowFileAccessForProcess`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180002567`

## pseudocode

```c
__int64 load_EdpDllAllowFileAccessForProcess()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002567  lea     rax, __imp_EdpDllAllowFileAccessForProcess
0x18000256e  jmp     __tailMerge_efscore_dll
```
