# __except_handler4_common

- ea: `0x10013487`
- end: `0x1001348d`
- name: `__except_handler4_common`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10013070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_except_handler4_common` at `0x10013487`

## pseudocode

```c
// attributes: thunk
int _except_handler4_common()
{
  return __except_handler4_common();
}

```

## disassembly

```asm
0x10013487  jmp     ds:__imp___except_handler4_common
```
