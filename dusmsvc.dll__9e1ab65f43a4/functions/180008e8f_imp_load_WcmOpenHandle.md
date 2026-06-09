# __imp_load_WcmOpenHandle

- ea: `0x180008e8f`
- end: `0x180008e9b`
- name: `__imp_load_WcmOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008dfe`

## import_xrefs

- `wcmapi!WcmOpenHandle` at `0x180008e8f`

## pseudocode

```c
__int64 load_WcmOpenHandle()
{
  return _tailMerge_wcmapi_dll();
}

```

## disassembly

```asm
0x180008e8f  lea     rax, __imp_WcmOpenHandle
0x180008e96  jmp     __tailMerge_wcmapi_dll
```
