# _invalid_parameter_noinfo

- ea: `0x1800024ea`
- end: `0x1800024f0`
- name: `_invalid_parameter_noinfo`
- size: `6`
- prototype: `void __cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003808`
- `0x180006094`
- `0x18000a8c8`
- `0x1800110e8`
- `0x1800115bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1800024ea`

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
0x1800024ea  jmp     cs:__imp__invalid_parameter_noinfo
```
