# _invalid_parameter_noinfo

- ea: `0x180001eae`
- end: `0x180001eb4`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003eec`
- `0x180005500`
- `0x1800056a0`
- `0x180005ce0`
- `0x180006ea8`
- `0x18000773c`
- `0x180007de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180001eae`

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
0x180001eae  jmp     cs:__imp__invalid_parameter_noinfo
```
