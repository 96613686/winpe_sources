# __scrt_is_ucrt_dll_in_use

- ea: `0x180001ff8`
- end: `0x180002004`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001734`
- `0x180001774`
- `0x18000180c`
- `0x18000185c`
- `0x1800018f0`
- `0x180001a24`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001ff8  xor     eax, eax
0x180001ffa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002000  setnz   al
0x180002003  retn
```
