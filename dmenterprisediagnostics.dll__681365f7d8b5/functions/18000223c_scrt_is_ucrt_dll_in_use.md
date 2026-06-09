# __scrt_is_ucrt_dll_in_use

- ea: `0x18000223c`
- end: `0x180002248`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001950`
- `0x180001990`
- `0x180001a28`
- `0x180001a78`
- `0x180001b0c`
- `0x180001c40`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000223c  xor     eax, eax
0x18000223e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002244  setnz   al
0x180002247  retn
```
