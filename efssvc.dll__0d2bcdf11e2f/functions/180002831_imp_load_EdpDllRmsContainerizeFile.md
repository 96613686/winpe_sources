# __imp_load_EdpDllRmsContainerizeFile

- ea: `0x180002831`
- end: `0x18000283d`
- name: `__imp_load_EdpDllRmsContainerizeFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180002831`

## pseudocode

```c
__int64 __fastcall load_EdpDllRmsContainerizeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_efscore_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002831  lea     rax, __imp_EdpDllRmsContainerizeFile
0x180002838  jmp     __tailMerge_efscore_dll
```
