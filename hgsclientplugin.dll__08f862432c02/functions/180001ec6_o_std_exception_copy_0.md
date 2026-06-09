# _o___std_exception_copy_0

- ea: `0x180001ec6`
- end: `0x180001ecc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a34`
- `0x180002b48`
- `0x1800061b0`
- `0x1800061f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001ec6`

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
0x180001ec6  jmp     cs:__imp__o___std_exception_copy
```
