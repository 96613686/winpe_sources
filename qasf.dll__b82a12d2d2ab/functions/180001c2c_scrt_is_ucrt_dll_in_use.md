# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c2c`
- end: `0x180001c38`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000158c`
- `0x1800015cc`
- `0x180001664`
- `0x1800016b4`
- `0x180001748`
- `0x18000187c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c2c  xor     eax, eax
0x180001c2e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c34  setnz   al
0x180001c37  retn
```
