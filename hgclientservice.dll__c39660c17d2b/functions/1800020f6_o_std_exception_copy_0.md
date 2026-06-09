# _o___std_exception_copy_0

- ea: `0x1800020f6`
- end: `0x1800020fc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003fac`
- `0x1800040c0`
- `0x180004104`
- `0x180004170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800020f6`

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
0x1800020f6  jmp     cs:__imp__o___std_exception_copy
```
