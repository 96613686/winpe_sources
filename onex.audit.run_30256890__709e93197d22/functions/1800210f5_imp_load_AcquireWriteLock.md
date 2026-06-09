# __imp_load_AcquireWriteLock

- ea: `0x1800210f5`
- end: `0x180021101`
- name: `__imp_load_AcquireWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!AcquireWriteLock` at `0x1800210f5`

## pseudocode

```c
__int64 load_AcquireWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800210f5  lea     rax, __imp_AcquireWriteLock
0x1800210fc  jmp     __tailMerge_mobilenetworking_dll
```
