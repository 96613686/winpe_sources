# _invalid_parameter_noinfo

- ea: `0x140002ca2`
- end: `0x140002ca8`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140008584`
- `0x14000ab34`
- `0x14000acf0`
- `0x14000b708`
- `0x14000dc5c`
- `0x14000fb88`
- `0x140010f78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x140002ca2`

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
0x140002ca2  jmp     cs:__imp__invalid_parameter_noinfo
```
