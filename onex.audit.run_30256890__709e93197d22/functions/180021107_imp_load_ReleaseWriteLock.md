# __imp_load_ReleaseWriteLock

- ea: `0x180021107`
- end: `0x180021113`
- name: `__imp_load_ReleaseWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180021107`

## pseudocode

```c
__int64 load_ReleaseWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180021107  lea     rax, __imp_ReleaseWriteLock
0x18002110e  jmp     __tailMerge_mobilenetworking_dll
```
