# _invalid_parameter_noinfo

- ea: `0x1400030aa`
- end: `0x1400030b0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140006ae8`
- `0x14000849c`
- `0x140008640`
- `0x140008c88`
- `0x14000a494`
- `0x14000ae68`
- `0x14000c160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400030aa`

## pseudocode

```c
// attributes: thunk
void __cdecl invalid_parameter_noinfo()
{
  _invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x1400030aa  jmp     cs:__imp__invalid_parameter_noinfo
```
