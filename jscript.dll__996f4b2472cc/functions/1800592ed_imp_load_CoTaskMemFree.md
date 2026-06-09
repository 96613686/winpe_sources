# __imp_load_CoTaskMemFree

- ea: `0x1800592ed`
- end: `0x1800592f9`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180059150`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800592ed`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800592ed  lea     rax, __imp_CoTaskMemFree
0x1800592f4  jmp     __tailMerge_ole32_dll
```
