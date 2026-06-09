# _invalid_parameter_noinfo

- ea: `0x180002b62`
- end: `0x180002b68`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ac0`
- `0x180007fb8`
- `0x18000815c`
- `0x18000831c`
- `0x180008b68`
- `0x18000b7c8`
- `0x18000b9d0`
- `0x18000c48c`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002b62`

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
0x180002b62  jmp     cs:__imp__invalid_parameter_noinfo
```
