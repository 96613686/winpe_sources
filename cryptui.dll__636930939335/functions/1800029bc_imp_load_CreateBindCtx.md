# __imp_load_CreateBindCtx

- ea: `0x1800029bc`
- end: `0x1800029c8`
- name: `__imp_load_CreateBindCtx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002907`

## import_xrefs

- `ole32!CreateBindCtx` at `0x1800029bc`

## pseudocode

```c
__int64 load_CreateBindCtx()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800029bc  lea     rax, __imp_CreateBindCtx
0x1800029c3  jmp     __tailMerge_ole32_dll
```
