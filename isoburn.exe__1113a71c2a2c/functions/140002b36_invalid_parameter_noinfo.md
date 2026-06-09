# _invalid_parameter_noinfo

- ea: `0x140002b36`
- end: `0x140002b3c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a570`
- `0x14000e20c`
- `0x14000e534`
- `0x14000eb64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140002b36`

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
0x140002b36  jmp     cs:__imp__invalid_parameter_noinfo
```
