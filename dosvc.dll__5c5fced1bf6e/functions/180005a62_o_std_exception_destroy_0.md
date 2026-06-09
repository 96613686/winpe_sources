# _o___std_exception_destroy_0

- ea: `0x180005a62`
- end: `0x180005a68`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000673c`
- `0x180006810`
- `0x180009a80`
- `0x180009a9c`
- `0x180009b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180005a62`

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
0x180005a62  jmp     cs:__imp___std_exception_destroy
```
