# _o___std_exception_copy_0

- ea: `0x180002ade`
- end: `0x180002ae4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c80`
- `0x180003e5c`
- `0x18000db68`
- `0x18000dbac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002ade`

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
0x180002ade  jmp     cs:__imp__o___std_exception_copy
```
