# _invalid_parameter_noinfo

- ea: `0x18000288a`
- end: `0x180002890`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800051d0`
- `0x180006980`
- `0x180006b24`
- `0x1800073b8`
- `0x180008dc0`
- `0x180008fc8`
- `0x18000995c`
- `0x180009fe8`
- `0x18000b6ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000288a`

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
0x18000288a  jmp     cs:__imp__invalid_parameter_noinfo
```
