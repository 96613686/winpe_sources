# __scrt_is_ucrt_dll_in_use

- ea: `0x180002998`
- end: `0x1800029a4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002124`
- `0x180002164`
- `0x1800021fc`
- `0x18000224c`
- `0x1800022e0`
- `0x180002414`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002998  xor     eax, eax
0x18000299a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800029a0  setnz   al
0x1800029a3  retn
```
