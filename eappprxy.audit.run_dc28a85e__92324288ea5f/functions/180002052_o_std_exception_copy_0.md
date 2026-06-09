# _o___std_exception_copy_0

- ea: `0x180002052`
- end: `0x180002058`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002cd4`
- `0x180002de8`
- `0x18000b518`
- `0x18000d468`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002052`

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
0x180002052  jmp     cs:__imp__o___std_exception_copy
```
