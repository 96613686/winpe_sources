# __scrt_is_ucrt_dll_in_use

- ea: `0x180007f18`
- end: `0x180007f24`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000786c`
- `0x1800078ac`
- `0x180007944`
- `0x180007994`
- `0x180007a28`
- `0x180007b5c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180007f18  xor     eax, eax
0x180007f1a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180007f20  setnz   al
0x180007f23  retn
```
