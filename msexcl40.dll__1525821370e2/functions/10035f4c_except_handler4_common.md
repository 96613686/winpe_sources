# __except_handler4_common

- ea: `0x10035f4c`
- end: `0x10035f52`
- name: `__except_handler4_common`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10035b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_except_handler4_common` at `0x10035f4c`

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
0x10035f4c  jmp     ds:__imp___except_handler4_common
```
