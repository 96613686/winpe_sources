# _o___std_exception_copy

- ea: `0x1800022ea`
- end: `0x1800022f0`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002098`
- `0x180002104`
- `0x180002170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800022ea`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1800022ea  jmp     cs:__imp__o___std_exception_copy
```
