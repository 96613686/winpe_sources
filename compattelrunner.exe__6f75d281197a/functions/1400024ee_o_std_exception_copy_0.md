# _o___std_exception_copy_0

- ea: `0x1400024ee`
- end: `0x1400024f4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003a70`
- `0x140003c4c`
- `0x14000e8ec`
- `0x14000e930`
- `0x14000e99c`
- `0x14000e9e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400024ee`

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
0x1400024ee  jmp     cs:__imp__o___std_exception_copy
```
