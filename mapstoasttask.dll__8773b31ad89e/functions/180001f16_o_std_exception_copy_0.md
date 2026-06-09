# _o___std_exception_copy_0

- ea: `0x180001f16`
- end: `0x180001f1c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000257c`
- `0x180002690`
- `0x1800026d4`
- `0x180002740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001f16`

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
0x180001f16  jmp     cs:__imp__o___std_exception_copy
```
