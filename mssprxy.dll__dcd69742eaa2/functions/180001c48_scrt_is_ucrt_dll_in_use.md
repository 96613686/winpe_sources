# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c48`
- end: `0x180001c54`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000159c`
- `0x1800015dc`
- `0x180001674`
- `0x1800016c4`
- `0x180001758`
- `0x18000188c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c48  xor     eax, eax
0x180001c4a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c50  setnz   al
0x180001c53  retn
```
