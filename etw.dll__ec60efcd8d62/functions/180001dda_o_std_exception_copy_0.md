# _o___std_exception_copy_0

- ea: `0x180001dda`
- end: `0x180001de0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020a0`
- `0x18000210c`
- `0x180002178`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001dda`

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
0x180001dda  jmp     cs:__imp__o___std_exception_copy
```
