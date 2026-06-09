# _o___std_exception_destroy_0

- ea: `0x18000205e`
- end: `0x180002064`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ef0`
- `0x180003230`
- `0x18000d52c`
- `0x18000d5d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000205e`

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
0x18000205e  jmp     cs:__imp___std_exception_destroy
```
