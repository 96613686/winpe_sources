# __imp_load_DeleteTimer

- ea: `0x1800210d1`
- end: `0x1800210dd`
- name: `__imp_load_DeleteTimer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!DeleteTimer` at `0x1800210d1`

## pseudocode

```c
__int64 load_DeleteTimer()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800210d1  lea     rax, __imp_DeleteTimer
0x1800210d8  jmp     __tailMerge_mobilenetworking_dll
```
