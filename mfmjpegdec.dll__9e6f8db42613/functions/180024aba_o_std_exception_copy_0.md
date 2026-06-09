# _o___std_exception_copy_0

- ea: `0x180024aba`
- end: `0x180024ac0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800465f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180024aba`

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
0x180024aba  jmp     cs:__imp__o___std_exception_copy
```
