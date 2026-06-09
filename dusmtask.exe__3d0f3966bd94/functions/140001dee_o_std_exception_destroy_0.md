# _o___std_exception_destroy_0

- ea: `0x140001dee`
- end: `0x140001df4`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140003b54`
- `0x140003cc4`
- `0x140003d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140001dee`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x140001dee  jmp     cs:__imp___std_exception_destroy
```
