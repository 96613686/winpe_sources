# __scrt_is_ucrt_dll_in_use

- ea: `0x180003be0`
- end: `0x180003bec`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800032dc`
- `0x18000331c`
- `0x1800033b4`
- `0x180003404`
- `0x180003498`
- `0x1800035cc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003be0  xor     eax, eax
0x180003be2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003be8  setnz   al
0x180003beb  retn
```
