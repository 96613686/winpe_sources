# __imp_load_DeleteReadWriteLock

- ea: `0x18000355f`
- end: `0x18000356b`
- name: `__imp_load_DeleteReadWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!DeleteReadWriteLock` at `0x18000355f`

## pseudocode

```c
__int64 load_DeleteReadWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18000355f  lea     rax, __imp_DeleteReadWriteLock
0x180003566  jmp     __tailMerge_mobilenetworking_dll
```
