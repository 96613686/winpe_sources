# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e50`
- end: `0x180001e5c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015b4`
- `0x1800015f4`
- `0x18000168c`
- `0x1800016dc`
- `0x180001770`
- `0x1800018a4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e50  xor     eax, eax
0x180001e52  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e58  setnz   al
0x180001e5b  retn
```
