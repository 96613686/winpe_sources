# _o___std_exception_copy_0

- ea: `0x18000209e`
- end: `0x1800020a4`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a7b0`
- `0x18000a8b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000209e`

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
0x18000209e  jmp     cs:__imp__o___std_exception_copy
```
