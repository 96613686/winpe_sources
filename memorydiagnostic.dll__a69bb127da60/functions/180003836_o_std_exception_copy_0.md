# _o___std_exception_copy_0

- ea: `0x180003836`
- end: `0x18000383c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180007158`
- `0x180007334`
- `0x180007378`
- `0x1800073e4`
- `0x18001ec14`
- `0x18001ec58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003836`

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
0x180003836  jmp     cs:__imp__o___std_exception_copy
```
