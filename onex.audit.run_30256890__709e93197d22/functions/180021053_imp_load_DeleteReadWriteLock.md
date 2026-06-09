# __imp_load_DeleteReadWriteLock

- ea: `0x180021053`
- end: `0x18002105f`
- name: `__imp_load_DeleteReadWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!DeleteReadWriteLock` at `0x180021053`

## pseudocode

```c
__int64 load_DeleteReadWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180021053  lea     rax, __imp_DeleteReadWriteLock
0x18002105a  jmp     __tailMerge_mobilenetworking_dll
```
