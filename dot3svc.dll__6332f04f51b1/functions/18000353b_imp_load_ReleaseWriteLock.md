# __imp_load_ReleaseWriteLock

- ea: `0x18000353b`
- end: `0x180003547`
- name: `__imp_load_ReleaseWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000353b`

## pseudocode

```c
__int64 load_ReleaseWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18000353b  lea     rax, __imp_ReleaseWriteLock
0x180003542  jmp     __tailMerge_mobilenetworking_dll
```
