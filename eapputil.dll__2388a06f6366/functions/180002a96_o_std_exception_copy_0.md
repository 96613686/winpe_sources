# _o___std_exception_copy_0

- ea: `0x180002a96`
- end: `0x180002a9c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800043ec`
- `0x180004500`
- `0x180007fc0`
- `0x18000802c`
- `0x180008070`
- `0x18000e60c`
- `0x180016ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002a96`

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
0x180002a96  jmp     cs:__imp__o___std_exception_copy
```
