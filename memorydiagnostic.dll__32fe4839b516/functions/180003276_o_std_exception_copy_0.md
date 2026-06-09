# _o___std_exception_copy_0

- ea: `0x180003276`
- end: `0x18000327c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800071d4`
- `0x1800073a8`
- `0x1800073ec`
- `0x180007458`
- `0x180020010`
- `0x180020054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003276`

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
0x180003276  jmp     cs:__imp__o___std_exception_copy
```
