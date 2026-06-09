# _o___std_exception_copy_0

- ea: `0x140001d42`
- end: `0x140001d48`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000298c`
- `0x140002aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140001d42`

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
0x140001d42  jmp     cs:__imp__o___std_exception_copy
```
