# __imp_load_CoTaskMemFree

- ea: `0x18000b2db`
- end: `0x18000b2e7`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b25c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000b2db`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000b2db  lea     rax, __imp_CoTaskMemFree
0x18000b2e2  jmp     __tailMerge_ole32_dll
```
