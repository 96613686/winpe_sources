# __scrt_is_ucrt_dll_in_use

- ea: `0x180015594`
- end: `0x1800155a0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180014f18`
- `0x180014f58`
- `0x180014ff0`
- `0x180015040`
- `0x1800150d4`
- `0x180015208`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180015594  xor     eax, eax
0x180015596  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001559c  setnz   al
0x18001559f  retn
```
