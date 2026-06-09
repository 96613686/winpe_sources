# __p__commode

- ea: `0x140001d36`
- end: `0x140001d3c`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400011b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x140001d36`

## pseudocode

```c
// attributes: thunk
int *__cdecl _p__commode()
{
  return __p__commode();
}

```

## disassembly

```asm
0x140001d36  jmp     cs:__imp___p__commode
```
