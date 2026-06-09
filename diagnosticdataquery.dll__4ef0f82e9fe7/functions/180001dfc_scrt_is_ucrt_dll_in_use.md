# __scrt_is_ucrt_dll_in_use

- ea: `0x180001dfc`
- end: `0x180001e08`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001524`
- `0x180001564`
- `0x1800015fc`
- `0x18000164c`
- `0x1800016e0`
- `0x180001814`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001dfc  xor     eax, eax
0x180001dfe  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e04  setnz   al
0x180001e07  retn
```
