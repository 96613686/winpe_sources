# __imp_load_CreateTimer

- ea: `0x1800210e3`
- end: `0x1800210ef`
- name: `__imp_load_CreateTimer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020fc2`

## import_xrefs

- `MobileNetworking!CreateTimer` at `0x1800210e3`

## pseudocode

```c
__int64 load_CreateTimer()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800210e3  lea     rax, __imp_CreateTimer
0x1800210ea  jmp     __tailMerge_mobilenetworking_dll
```
