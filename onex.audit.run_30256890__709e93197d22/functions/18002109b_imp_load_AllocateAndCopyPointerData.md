# __imp_load_AllocateAndCopyPointerData

- ea: `0x18002109b`
- end: `0x1800210a7`
- name: `__imp_load_AllocateAndCopyPointerData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x18002109b`

## pseudocode

```c
__int64 load_AllocateAndCopyPointerData()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18002109b  lea     rax, __imp_AllocateAndCopyPointerData
0x1800210a2  jmp     __tailMerge_mobilenetworking_dll
```
