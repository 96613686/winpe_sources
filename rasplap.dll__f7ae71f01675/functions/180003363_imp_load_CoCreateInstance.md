# __imp_load_CoCreateInstance

- ea: `0x180003363`
- end: `0x18000336f`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800032c0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003363`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180003363  lea     rax, __imp_CoCreateInstance
0x18000336a  jmp     __tailMerge_ole32_dll
```
