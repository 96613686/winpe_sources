# __imp_load_CreateStreamOnHGlobal

- ea: `0x180002069`
- end: `0x180002075`
- name: `__imp_load_CreateStreamOnHGlobal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001f90`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180002069`

## pseudocode

```c
__int64 load_CreateStreamOnHGlobal()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180002069  lea     rax, __imp_CreateStreamOnHGlobal
0x180002070  jmp     __tailMerge_ole32_dll
```
