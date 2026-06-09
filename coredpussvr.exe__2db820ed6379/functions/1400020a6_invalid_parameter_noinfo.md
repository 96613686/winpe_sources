# _invalid_parameter_noinfo

- ea: `0x1400020a6`
- end: `0x1400020ac`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400059dc`
- `0x140008460`
- `0x14000878c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400020a6`

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
0x1400020a6  jmp     cs:__imp__invalid_parameter_noinfo
```
