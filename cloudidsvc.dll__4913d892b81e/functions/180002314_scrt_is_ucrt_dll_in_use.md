# __scrt_is_ucrt_dll_in_use

- ea: `0x180002314`
- end: `0x180002320`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001a80`
- `0x180001ac0`
- `0x180001b58`
- `0x180001ba8`
- `0x180001c3c`
- `0x180001d70`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002314  xor     eax, eax
0x180002316  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000231c  setnz   al
0x18000231f  retn
```
