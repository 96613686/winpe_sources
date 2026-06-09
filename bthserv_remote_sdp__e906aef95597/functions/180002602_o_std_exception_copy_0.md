# _o___std_exception_copy_0

- ea: `0x180002602`
- end: `0x180002608`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037a0`
- `0x180003974`
- `0x18000af24`
- `0x18000af68`
- `0x18001fa50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002602`

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
0x180002602  jmp     cs:__imp__o___std_exception_copy
```
