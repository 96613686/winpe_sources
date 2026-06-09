# __imp_load_CDFindCommonCSystem

- ea: `0x180022640`
- end: `0x18002264c`
- name: `__imp_load_CDFindCommonCSystem`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180022579`

## import_xrefs

- `cryptdll!CDFindCommonCSystem` at `0x180022640`

## pseudocode

```c
__int64 load_CDFindCommonCSystem()
{
  return _tailMerge_cryptdll_dll();
}

```

## disassembly

```asm
0x180022640  lea     rax, __imp_CDFindCommonCSystem
0x180022647  jmp     __tailMerge_cryptdll_dll
```
