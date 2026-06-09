# _o___std_exception_copy_0

- ea: `0x180002546`
- end: `0x18000254c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003148`
- `0x18000325c`
- `0x180007b38`
- `0x180007b7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002546`

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
0x180002546  jmp     cs:__imp__o___std_exception_copy
```
