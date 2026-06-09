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

- `0x140002b6c`
- `0x140002d40`
- `0x140003068`
- `0x1400031f4`
- `0x1400033d8`
- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005910`
- `0x140005c78`
- `0x140005ef0`
- `0x1400061e4`
- `0x14000672c`
- `0x1400073d4`
- `0x1400075ac`
- `0x140007cbc`
- `0x140008cbc`
- `0x140009a50`
- `0x140009b2c`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`
- `0x14000aa4c`
- `0x14000e864`

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
