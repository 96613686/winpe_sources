# _o___std_exception_copy_0

- ea: `0x180001d8e`
- end: `0x180001d94`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c58`
- `0x180002d6c`
- `0x1800061f4`
- `0x180006238`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001d8e`

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
0x180001d8e  jmp     cs:__imp__o___std_exception_copy
```
