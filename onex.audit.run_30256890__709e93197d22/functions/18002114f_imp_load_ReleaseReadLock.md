# __imp_load_ReleaseReadLock

- ea: `0x18002114f`
- end: `0x18002115b`
- name: `__imp_load_ReleaseReadLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!ReleaseReadLock` at `0x18002114f`

## pseudocode

```c
__int64 load_ReleaseReadLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x18002114f  lea     rax, __imp_ReleaseReadLock
0x180021156  jmp     __tailMerge_mobilenetworking_dll
```
