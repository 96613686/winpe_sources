# __imp_load_AcquireReadLock

- ea: `0x18002113d`
- end: `0x180021149`
- name: `__imp_load_AcquireReadLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!AcquireReadLock` at `0x18002113d`

## pseudocode

```c
__int64 load_AcquireReadLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18002113d  lea     rax, __imp_AcquireReadLock
0x180021144  jmp     __tailMerge_mobilenetworking_dll
```
