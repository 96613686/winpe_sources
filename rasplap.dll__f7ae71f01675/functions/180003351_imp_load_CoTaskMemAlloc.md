# __imp_load_CoTaskMemAlloc

- ea: `0x180003351`
- end: `0x18000335d`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800032c0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180003351`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180003351  lea     rax, __imp_CoTaskMemAlloc
0x180003358  jmp     __tailMerge_ole32_dll
```
