# _o___std_exception_destroy_0

- ea: `0x180002812`
- end: `0x180002818`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003fe8`
- `0x1800043e0`
- `0x18000cd7c`
- `0x18000da2c`
- `0x18000dab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180002812`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x180002812  jmp     cs:__imp___std_exception_destroy
```
