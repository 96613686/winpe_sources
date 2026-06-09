# _o__set_new_mode_0

- ea: `0x140001c5a`
- end: `0x140001c60`
- name: `_o__set_new_mode_0`
- size: `6`
- prototype: `int __cdecl(int NewMode)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_new_mode` at `0x140001c5a`

## pseudocode

```c
// attributes: thunk
int __cdecl o__set_new_mode_0(int NewMode)
{
  return _set_new_mode(NewMode);
}

```

## disassembly

```asm
0x140001c5a  jmp     cs:__imp__set_new_mode
```
