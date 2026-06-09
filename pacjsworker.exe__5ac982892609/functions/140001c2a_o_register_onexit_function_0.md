# _o__register_onexit_function_0

- ea: `0x140001c2a`
- end: `0x140001c30`
- name: `_o__register_onexit_function_0`
- size: `6`
- prototype: `int __cdecl(_onexit_table_t *Table, _onexit_t Function)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__register_onexit_function` at `0x140001c2a`

## pseudocode

```c
// attributes: thunk
int __cdecl o__register_onexit_function_0(_onexit_table_t *Table, _onexit_t Function)
{
  return _register_onexit_function(Table, Function);
}

```

## disassembly

```asm
0x140001c2a  jmp     cs:__imp__register_onexit_function
```
