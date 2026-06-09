# _o___acrt_iob_func_0

- ea: `0x140001bb2`
- end: `0x140001bb8`
- name: `_o___acrt_iob_func_0`
- size: `6`
- prototype: `FILE *__cdecl(unsigned int Ix)`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a28`
- `0x140002bc0`
- `0x140002f30`
- `0x1400030b8`
- `0x14000329c`
- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x1400055f8`
- `0x140005940`
- `0x140005bac`
- `0x140005e84`
- `0x140006394`
- `0x140006f9c`
- `0x140007170`
- `0x140007834`
- `0x140008788`
- `0x1400094a0`
- `0x140009574`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ec0`
- `0x14000a3f8`
- `0x14000dce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x140001bb2`

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
0x140001bb2  jmp     cs:__imp___acrt_iob_func
```
