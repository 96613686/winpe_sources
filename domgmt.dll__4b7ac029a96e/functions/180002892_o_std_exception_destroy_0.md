# _o___std_exception_destroy_0

- ea: `0x180002892`
- end: `0x180002898`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003bb4`
- `0x180003d70`
- `0x180008e88`
- `0x180008ea4`
- `0x180009660`
- `0x1800096b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180002892`

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
0x180002892  jmp     cs:__imp___std_exception_destroy
```
