# _invalid_parameter_noinfo

- ea: `0x140002b82`
- end: `0x140002b88`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140006d8c`
- `0x140009124`
- `0x1400092c8`
- `0x1400099d8`
- `0x14000be54`
- `0x14000cc58`
- `0x14000d778`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140002b82`

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
0x140002b82  jmp     cs:__imp__invalid_parameter_noinfo
```
