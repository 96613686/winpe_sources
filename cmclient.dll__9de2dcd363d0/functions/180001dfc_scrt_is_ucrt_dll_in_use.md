# __scrt_is_ucrt_dll_in_use

- ea: `0x180001dfc`
- end: `0x180001e08`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001598`
- `0x1800015d8`
- `0x180001670`
- `0x1800016c0`
- `0x180001754`
- `0x180001888`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001dfc  xor     eax, eax
0x180001dfe  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e04  setnz   al
0x180001e07  retn
```
