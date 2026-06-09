# __imp_load_EdpDllPurgeAppLearningEvents

- ea: `0x18000252b`
- end: `0x180002537`
- name: `__imp_load_EdpDllPurgeAppLearningEvents`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllPurgeAppLearningEvents` at `0x18000252b`

## pseudocode

```c
__int64 __fastcall load_EdpDllPurgeAppLearningEvents(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000252b  lea     rax, __imp_EdpDllPurgeAppLearningEvents
0x180002532  jmp     __tailMerge_efscore_dll
```
