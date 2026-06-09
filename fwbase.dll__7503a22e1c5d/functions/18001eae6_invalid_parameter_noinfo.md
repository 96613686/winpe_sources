# _invalid_parameter_noinfo

- ea: `0x18001eae6`
- end: `0x18001eaec`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180023aa0`
- `0x180023ea0`
- `0x180025130`
- `0x180025860`
- `0x180025fe0`
- `0x180026190`
- `0x180026b70`
- `0x180028210`
- `0x180028330`
- `0x180028b30`
- `0x180029210`
- `0x180029fd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18001eae6`

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
0x18001eae6  jmp     cs:__imp__invalid_parameter_noinfo
```
