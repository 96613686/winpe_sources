# __scrt_is_ucrt_dll_in_use

- ea: `0x180009a40`
- end: `0x180009a4c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800093b8`
- `0x1800093f8`
- `0x180009490`
- `0x1800094e0`
- `0x180009574`
- `0x1800096a8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180009a40  xor     eax, eax
0x180009a42  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180009a48  setnz   al
0x180009a4b  retn
```
