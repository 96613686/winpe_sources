# _invalid_parameter_noinfo

- ea: `0x1800029f6`
- end: `0x1800029fc`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d2c`
- `0x180006054`
- `0x1800063d4`
- `0x1800105a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800029f6`

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
0x1800029f6  jmp     cs:__imp__invalid_parameter_noinfo
```
