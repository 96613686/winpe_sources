# _o___std_exception_copy_0

- ea: `0x1800037b4`
- end: `0x1800037ba`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003570`
- `0x1800035dc`
- `0x180003648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800037b4`

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
0x1800037b4  jmp     cs:__imp__o___std_exception_copy
```
