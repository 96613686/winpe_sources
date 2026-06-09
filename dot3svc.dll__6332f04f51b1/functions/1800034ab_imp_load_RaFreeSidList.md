# __imp_load_RaFreeSidList

- ea: `0x1800034ab`
- end: `0x1800034b7`
- name: `__imp_load_RaFreeSidList`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!RaFreeSidList` at `0x1800034ab`

## pseudocode

```c
__int64 load_RaFreeSidList()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800034ab  lea     rax, __imp_RaFreeSidList
0x1800034b2  jmp     __tailMerge_mobilenetworking_dll
```
