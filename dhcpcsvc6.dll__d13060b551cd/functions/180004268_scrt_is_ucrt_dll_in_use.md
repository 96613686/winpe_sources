# __scrt_is_ucrt_dll_in_use

- ea: `0x180004268`
- end: `0x180004274`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003bbc`
- `0x180003bfc`
- `0x180003c94`
- `0x180003ce4`
- `0x180003d78`
- `0x180003eac`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004268  xor     eax, eax
0x18000426a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004270  setnz   al
0x180004273  retn
```
