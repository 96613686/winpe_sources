# __imp_load_CoTaskMemRealloc

- ea: `0x180002033`
- end: `0x18000203f`
- name: `__imp_load_CoTaskMemRealloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001f90`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x180002033`

## pseudocode

```c
__int64 load_CoTaskMemRealloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180002033  lea     rax, __imp_CoTaskMemRealloc
0x18000203a  jmp     __tailMerge_ole32_dll
```
