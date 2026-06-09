# __imp_load_CoCreateInstance

- ea: `0x180057f56`
- end: `0x180057f62`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180057ed7`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180057f56`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180057f56  lea     rax, __imp_CoCreateInstance
0x180057f5d  jmp     __tailMerge_ole32_dll
```
