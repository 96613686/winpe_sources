# __imp_load_EdpDllRmsDecontainerizeFile

- ea: `0x180002603`
- end: `0x18000260f`
- name: `__imp_load_EdpDllRmsDecontainerizeFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000239e`

## import_xrefs

- `EFSCORE!EdpDllRmsDecontainerizeFile` at `0x180002603`

## pseudocode

```c
__int64 load_EdpDllRmsDecontainerizeFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002603  lea     rax, __imp_EdpDllRmsDecontainerizeFile
0x18000260a  jmp     __tailMerge_efscore_dll
```
