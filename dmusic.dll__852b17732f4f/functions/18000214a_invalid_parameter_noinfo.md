# _invalid_parameter_noinfo

- ea: `0x18000214a`
- end: `0x180002150`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180004800`
- `0x18000617c`
- `0x1800063a8`
- `0x180006be8`
- `0x180008218`
- `0x180008420`
- `0x180008dcc`
- `0x180009458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000214a`

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
0x18000214a  jmp     cs:__imp__invalid_parameter_noinfo
```
