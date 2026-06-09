# __imp_load_CreateErrorInfo

- ea: `0x18000bc6a`
- end: `0x18000bc76`
- name: `__imp_load_CreateErrorInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bbd9`

## import_xrefs

- `OLEAUT32!__imp_CreateErrorInfo` at `0x18000bc6a`

## pseudocode

```c
__int64 load_CreateErrorInfo()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000bc6a  lea     rax, __imp_CreateErrorInfo
0x18000bc71  jmp     __tailMerge_oleaut32_dll
```
