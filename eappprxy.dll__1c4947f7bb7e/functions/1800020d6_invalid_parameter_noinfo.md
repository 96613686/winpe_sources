# _invalid_parameter_noinfo

- ea: `0x1800020d6`
- end: `0x1800020dc`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008850`
- `0x180008cf0`
- `0x18000b36c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800020d6`

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
0x1800020d6  jmp     cs:__imp__invalid_parameter_noinfo
```
