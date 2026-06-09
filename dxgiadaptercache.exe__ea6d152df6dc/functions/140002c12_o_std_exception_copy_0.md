# _o___std_exception_copy_0

- ea: `0x140002c12`
- end: `0x140002c18`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140005b88`
- `0x140005d64`
- `0x140005da8`
- `0x140005e14`
- `0x140005e80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002c12`

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
0x140002c12  jmp     cs:__imp__o___std_exception_copy
```
