# __imp_load_CreateReadWriteLock

- ea: `0x18000354d`
- end: `0x180003559`
- name: `__imp_load_CreateReadWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x18000354d`

## pseudocode

```c
__int64 load_CreateReadWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18000354d  lea     rax, __imp_CreateReadWriteLock
0x180003554  jmp     __tailMerge_mobilenetworking_dll
```
