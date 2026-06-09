# __imp_load_CoTaskMemFree

- ea: `0x180003375`
- end: `0x180003381`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800032c0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003375`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180003375  lea     rax, __imp_CoTaskMemFree
0x18000337c  jmp     __tailMerge_ole32_dll
```
