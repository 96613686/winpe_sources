# __imp_load_EdpDllServiceFileEncryptionQueue

- ea: `0x1800027e9`
- end: `0x1800027f5`
- name: `__imp_load_EdpDllServiceFileEncryptionQueue`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x1800027e9`

## pseudocode

```c
__int64 __fastcall load_EdpDllServiceFileEncryptionQueue(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027e9  lea     rax, __imp_EdpDllServiceFileEncryptionQueue
0x1800027f0  jmp     __tailMerge_efscore_dll
```
