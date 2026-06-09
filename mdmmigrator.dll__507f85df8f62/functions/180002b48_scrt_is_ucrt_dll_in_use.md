# __scrt_is_ucrt_dll_in_use

- ea: `0x180002b48`
- end: `0x180002b54`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002304`
- `0x180002344`
- `0x1800023dc`
- `0x18000242c`
- `0x1800024c0`
- `0x1800025f4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002b48  xor     eax, eax
0x180002b4a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002b50  setnz   al
0x180002b53  retn
```
