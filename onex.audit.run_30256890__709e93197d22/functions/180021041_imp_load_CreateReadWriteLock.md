# __imp_load_CreateReadWriteLock

- ea: `0x180021041`
- end: `0x18002104d`
- name: `__imp_load_CreateReadWriteLock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x180021041`

## pseudocode

```c
__int64 load_CreateReadWriteLock()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x180021041  lea     rax, __imp_CreateReadWriteLock
0x180021048  jmp     __tailMerge_mobilenetworking_dll
```
