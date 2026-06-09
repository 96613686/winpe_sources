# _invalid_parameter_noinfo

- ea: `0x180002c36`
- end: `0x180002c3c`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800075ac`
- `0x180017284`
- `0x180017b94`
- `0x180017d34`
- `0x180018304`
- `0x18001beb4`
- `0x18001cc54`
- `0x18001e38c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180002c36`

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
0x180002c36  jmp     cs:__imp__invalid_parameter_noinfo
```
