# _o___acrt_iob_func_0

- ea: `0x14000265e`
- end: `0x140002664`
- name: `_o___acrt_iob_func_0`
- size: `6`
- prototype: `FILE *__cdecl(unsigned int Ix)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140002870`
- `0x140002c2c`
- `0x140006198`
- `0x140007534`
- `0x140009dcc`
- `0x140009ee0`
- `0x14000ba74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x14000265e`

## pseudocode

```c
// attributes: thunk
FILE *__cdecl o___acrt_iob_func_0(unsigned int Ix)
{
  return __acrt_iob_func(Ix);
}

```

## disassembly

```asm
0x14000265e  jmp     cs:__imp___acrt_iob_func
```
