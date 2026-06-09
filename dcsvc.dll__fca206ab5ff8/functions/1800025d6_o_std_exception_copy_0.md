# _o___std_exception_copy_0

- ea: `0x1800025d6`
- end: `0x1800025dc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003840`
- `0x180003a1c`
- `0x18000f8d0`
- `0x18000f914`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800025d6`

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
0x1800025d6  jmp     cs:__imp__o___std_exception_copy
```
