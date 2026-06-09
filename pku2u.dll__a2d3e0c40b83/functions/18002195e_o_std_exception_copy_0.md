# _o___std_exception_copy_0

- ea: `0x18002195e`
- end: `0x180021964`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180022800`
- `0x18002286c`
- `0x18002524c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18002195e`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x18002195e  jmp     cs:__imp__o___std_exception_copy
```
