# __imp_load_AcquireWriteLock

- ea: `0x180003529`
- end: `0x180003535`
- name: `__imp_load_AcquireWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!AcquireWriteLock` at `0x180003529`

## pseudocode

```c
__int64 load_AcquireWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180003529  lea     rax, __imp_AcquireWriteLock
0x180003530  jmp     __tailMerge_mobilenetworking_dll
```
