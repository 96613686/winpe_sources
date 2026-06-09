# __scrt_is_ucrt_dll_in_use

- ea: `0x180020a30`
- end: `0x180020a3c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800203a4`
- `0x1800203e4`
- `0x18002047c`
- `0x1800204cc`
- `0x180020560`
- `0x180020694`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180020a30  xor     eax, eax
0x180020a32  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180020a38  setnz   al
0x180020a3b  retn
```
