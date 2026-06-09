# _o__set_fmode_0

- ea: `0x140001c4e`
- end: `0x140001c54`
- name: `_o__set_fmode_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_fmode` at `0x140001c4e`

## pseudocode

```c
// attributes: thunk
__int64 o__set_fmode_0()
{
  return _o__set_fmode();
}

```

## disassembly

```asm
0x140001c4e  jmp     cs:__imp__o__set_fmode
```
