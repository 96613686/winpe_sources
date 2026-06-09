# _o___std_exception_destroy_0

- ea: `0x140001d4e`
- end: `0x140001d54`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002bc0`
- `0x140002e30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140001d4e`

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
0x140001d4e  jmp     cs:__imp___std_exception_destroy
```
