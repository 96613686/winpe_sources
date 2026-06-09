# __scrt_is_ucrt_dll_in_use

- ea: `0x180002e70`
- end: `0x180002e7c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002650`
- `0x180002690`
- `0x180002728`
- `0x180002778`
- `0x18000280c`
- `0x180002940`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002e70  xor     eax, eax
0x180002e72  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002e78  setnz   al
0x180002e7b  retn
```
