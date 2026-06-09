# _o___std_exception_copy_0

- ea: `0x1800144f2`
- end: `0x1800144f8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180014a24`
- `0x180014a90`
- `0x18001ef0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800144f2`

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
0x1800144f2  jmp     cs:__imp__o___std_exception_copy
```
