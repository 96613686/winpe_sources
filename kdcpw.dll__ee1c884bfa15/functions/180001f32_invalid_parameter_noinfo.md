# _invalid_parameter_noinfo

- ea: `0x180001f32`
- end: `0x180001f38`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047e0`
- `0x1800062e8`
- `0x180006488`
- `0x180006644`
- `0x180006e74`
- `0x180008250`
- `0x180008458`
- `0x180008dbc`
- `0x1800094bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x180001f32`

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
0x180001f32  jmp     cs:__imp__invalid_parameter_noinfo
```
