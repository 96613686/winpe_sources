# __except_handler4_common

- ea: `0x1003b5cc`
- end: `0x1003b5d2`
- name: `__except_handler4_common`
- size: `6`
- prototype: `int __cdecl(int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1003ab60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_except_handler4_common` at `0x1003b5cc`

## pseudocode

```c
// attributes: thunk
int __cdecl _except_handler4_common(int a1, int a2, int a3, int a4, int a5, int a6)
{
  return __except_handler4_common(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1003b5cc  jmp     ds:__imp___except_handler4_common
```
