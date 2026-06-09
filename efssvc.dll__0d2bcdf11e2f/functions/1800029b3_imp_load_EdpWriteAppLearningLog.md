# __imp_load_EdpWriteAppLearningLog

- ea: `0x1800029b3`
- end: `0x1800029bf`
- name: `__imp_load_EdpWriteAppLearningLog`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpWriteAppLearningLog` at `0x1800029b3`

## pseudocode

```c
__int64 __fastcall load_EdpWriteAppLearningLog(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800029b3  lea     rax, __imp_EdpWriteAppLearningLog
0x1800029ba  jmp     __tailMerge_efscore_dll
```
