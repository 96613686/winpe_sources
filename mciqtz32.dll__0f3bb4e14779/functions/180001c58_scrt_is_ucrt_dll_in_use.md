# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c58`
- end: `0x180001c64`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015b8`
- `0x1800015f8`
- `0x180001690`
- `0x1800016e0`
- `0x180001774`
- `0x1800018a8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c58  xor     eax, eax
0x180001c5a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c60  setnz   al
0x180001c63  retn
```
