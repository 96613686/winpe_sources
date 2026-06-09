# __imp_load_RaInitSidList

- ea: `0x180003499`
- end: `0x1800034a5`
- name: `__imp_load_RaInitSidList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!RaInitSidList` at `0x180003499`

## pseudocode

```c
__int64 load_RaInitSidList()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180003499  lea     rax, __imp_RaInitSidList
0x1800034a0  jmp     __tailMerge_mobilenetworking_dll
```
