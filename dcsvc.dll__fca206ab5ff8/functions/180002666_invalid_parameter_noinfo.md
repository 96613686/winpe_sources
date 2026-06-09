# _invalid_parameter_noinfo

- ea: `0x180002666`
- end: `0x18000266c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180005160`
- `0x1800069f8`
- `0x180006b9c`
- `0x1800073e8`
- `0x180009138`
- `0x180009340`
- `0x18000a03c`
- `0x18000a8b4`
- `0x18000bcf0`
- `0x18000d0b0`
- `0x18000d160`
- `0x18000ef24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002666`

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
0x180002666  jmp     cs:__imp__invalid_parameter_noinfo
```
