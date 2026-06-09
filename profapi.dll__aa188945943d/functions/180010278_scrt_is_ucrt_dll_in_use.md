# __scrt_is_ucrt_dll_in_use

- ea: `0x180010278`
- end: `0x180010284`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000fa34`
- `0x18000fa74`
- `0x18000fb0c`
- `0x18000fb5c`
- `0x18000fbf0`
- `0x18000fd24`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180010278  xor     eax, eax
0x18001027a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010280  setnz   al
0x180010283  retn
```
