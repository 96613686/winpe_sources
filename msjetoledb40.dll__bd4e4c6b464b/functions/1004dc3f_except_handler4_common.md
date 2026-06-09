# __except_handler4_common

- ea: `0x1004dc3f`
- end: `0x1004dc45`
- name: `__except_handler4_common`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1004dbf0`

## import_xrefs

- `msvcrt!_except_handler4_common` at `0x1004dc3f`

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
0x1004dc3f  jmp     ds:__imp___except_handler4_common
```
