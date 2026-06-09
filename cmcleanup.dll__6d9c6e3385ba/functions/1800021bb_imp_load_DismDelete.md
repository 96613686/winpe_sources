# __imp_load_DismDelete

- ea: `0x1800021bb`
- end: `0x1800021c7`
- name: `__imp_load_DismDelete`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000212a`

## import_xrefs

- `DismApi!DismDelete` at `0x1800021bb`

## pseudocode

```c
__int64 load_DismDelete()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x1800021bb  lea     rax, __imp_DismDelete
0x1800021c2  jmp     __tailMerge_dismapi_dll
```
