# __imp_load_EdpDllRmsContainerizeFile

- ea: `0x180002801`
- end: `0x18000280d`
- name: `__imp_load_EdpDllRmsContainerizeFile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000236e`

## import_xrefs

- `EFSCORE!EdpDllRmsContainerizeFile` at `0x180002801`

## pseudocode

```c
__int64 load_EdpDllRmsContainerizeFile()
{
  return _tailMerge_efscore_dll();
}

```

## disassembly

```asm
0x180002801  lea     rax, __imp_EdpDllRmsContainerizeFile
0x180002808  jmp     __tailMerge_efscore_dll
```
