# __imp_load_SetTokenInformation

- ea: `0x1800172ed`
- end: `0x1800172f9`
- name: `__imp_load_SetTokenInformation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180017196`

## import_xrefs

- `ADVAPI32!SetTokenInformation` at `0x1800172ed`

## pseudocode

```c
__int64 load_SetTokenInformation()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800172ed  lea     rax, __imp_SetTokenInformation
0x1800172f4  jmp     __tailMerge_advapi32_dll
```
