# __scrt_is_ucrt_dll_in_use

- ea: `0x1800037f4`
- end: `0x180003800`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002edc`
- `0x180002f1c`
- `0x180002fb4`
- `0x180003004`
- `0x180003098`
- `0x1800031cc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800037f4  xor     eax, eax
0x1800037f6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800037fc  setnz   al
0x1800037ff  retn
```
