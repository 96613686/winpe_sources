# __scrt_is_ucrt_dll_in_use

- ea: `0x180001fe8`
- end: `0x180001ff4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800017dc`
- `0x18000181c`
- `0x1800018b4`
- `0x180001904`
- `0x180001998`
- `0x180001acc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001fe8  xor     eax, eax
0x180001fea  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ff0  setnz   al
0x180001ff3  retn
```
