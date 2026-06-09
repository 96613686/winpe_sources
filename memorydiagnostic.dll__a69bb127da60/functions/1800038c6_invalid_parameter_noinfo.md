# _invalid_parameter_noinfo

- ea: `0x1800038c6`
- end: `0x1800038cc`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c004`
- `0x18000eacc`
- `0x18000ec70`
- `0x18000ee48`
- `0x18000f6d8`
- `0x1800135a0`
- `0x1800137a8`
- `0x180015504`
- `0x1800196f0`
- `0x18001ff50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800038c6`

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
0x1800038c6  jmp     cs:__imp__invalid_parameter_noinfo
```
