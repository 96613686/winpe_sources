# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c20`
- end: `0x180001c2c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001594`
- `0x1800015d4`
- `0x18000166c`
- `0x1800016bc`
- `0x180001750`
- `0x180001884`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c20  xor     eax, eax
0x180001c22  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c28  setnz   al
0x180001c2b  retn
```
