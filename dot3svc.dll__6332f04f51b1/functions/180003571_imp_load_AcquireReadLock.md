# __imp_load_AcquireReadLock

- ea: `0x180003571`
- end: `0x18000357d`
- name: `__imp_load_AcquireReadLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!AcquireReadLock` at `0x180003571`

## pseudocode

```c
__int64 load_AcquireReadLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180003571  lea     rax, __imp_AcquireReadLock
0x180003578  jmp     __tailMerge_mobilenetworking_dll
```
