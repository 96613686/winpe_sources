# _invalid_parameter_noinfo

- ea: `0x14000202e`
- end: `0x140002034`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000463c`
- `0x1400058dc`
- `0x140005a80`
- `0x1400060f8`
- `0x1400079d4`
- `0x1400082bc`
- `0x140008948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x14000202e`

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
0x14000202e  jmp     cs:__imp__invalid_parameter_noinfo
```
