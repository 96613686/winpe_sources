# _o___std_exception_copy_0

- ea: `0x180002886`
- end: `0x18000288c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000399c`
- `0x180003ab0`
- `0x1800085fc`
- `0x1800087f4`
- `0x180008848`
- `0x18000888c`
- `0x1800088f8`
- `0x180008b3c`
- `0x180008b80`
- `0x180008be0`
- `0x180008c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002886`

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
0x180002886  jmp     cs:__imp__o___std_exception_copy
```
