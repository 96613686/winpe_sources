# __imp_load_CoCreateInstance

- ea: `0x180001b0f`
- end: `0x180001b1b`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001a90`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001b0f`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180001b0f  lea     rax, __imp_CoCreateInstance
0x180001b16  jmp     __tailMerge_ole32_dll
```
