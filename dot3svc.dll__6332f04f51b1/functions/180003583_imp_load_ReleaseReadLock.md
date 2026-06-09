# __imp_load_ReleaseReadLock

- ea: `0x180003583`
- end: `0x18000358f`
- name: `__imp_load_ReleaseReadLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800033c0`

## import_xrefs

- `MobileNetworking!ReleaseReadLock` at `0x180003583`

## pseudocode

```c
__int64 load_ReleaseReadLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180003583  lea     rax, __imp_ReleaseReadLock
0x18000358a  jmp     __tailMerge_mobilenetworking_dll
```
