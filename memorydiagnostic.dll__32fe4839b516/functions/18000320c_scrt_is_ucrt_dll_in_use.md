# __scrt_is_ucrt_dll_in_use

- ea: `0x18000320c`
- end: `0x180003218`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000273c`
- `0x18000277c`
- `0x180002820`
- `0x180002888`
- `0x18000291c`
- `0x180002a50`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000320c  xor     eax, eax
0x18000320e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003214  setnz   al
0x180003217  retn
```
