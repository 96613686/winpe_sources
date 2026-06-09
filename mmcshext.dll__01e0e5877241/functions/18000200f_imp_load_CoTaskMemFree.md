# __imp_load_CoTaskMemFree

- ea: `0x18000200f`
- end: `0x18000201b`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001f90`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000200f`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000200f  lea     rax, __imp_CoTaskMemFree
0x180002016  jmp     __tailMerge_ole32_dll
```
