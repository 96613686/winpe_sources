# _o___std_exception_copy_0

- ea: `0x180003be6`
- end: `0x180003bec`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004dc4`
- `0x180004fa0`
- `0x18000c51c`
- `0x18000c560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003be6`

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
0x180003be6  jmp     cs:__imp__o___std_exception_copy
```
