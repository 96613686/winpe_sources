# __imp_load_Tbsi_Context_Create

- ea: `0x180003eaa`
- end: `0x180003eb6`
- name: `__imp_load_Tbsi_Context_Create`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003e19`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x180003eaa`

## pseudocode

```c
__int64 load_Tbsi_Context_Create()
{
  return _tailMerge_tbs_dll();
}

```

## disassembly

```asm
0x180003eaa  lea     rax, __imp_Tbsi_Context_Create
0x180003eb1  jmp     __tailMerge_tbs_dll
```
