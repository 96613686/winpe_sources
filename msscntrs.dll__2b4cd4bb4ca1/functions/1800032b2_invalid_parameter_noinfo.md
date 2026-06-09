# _invalid_parameter_noinfo

- ea: `0x1800032b2`
- end: `0x1800032b8`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180005de0`
- `0x180007508`
- `0x1800076ac`
- `0x180007f38`
- `0x180009714`
- `0x18000991c`
- `0x18000a2cc`
- `0x18000ac08`
- `0x18000e928`
- `0x18000ffec`
- `0x180010314`
- `0x180010cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800032b2`

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
0x1800032b2  jmp     cs:__imp__invalid_parameter_noinfo
```
