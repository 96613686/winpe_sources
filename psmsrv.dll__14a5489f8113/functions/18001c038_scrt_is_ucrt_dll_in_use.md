# __scrt_is_ucrt_dll_in_use

- ea: `0x18001c038`
- end: `0x18001c044`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001b938`
- `0x18001b978`
- `0x18001ba10`
- `0x18001ba60`
- `0x18001baf4`
- `0x18001bc28`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18001c038  xor     eax, eax
0x18001c03a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001c040  setnz   al
0x18001c043  retn
```
