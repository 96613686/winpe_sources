# __scrt_is_ucrt_dll_in_use

- ea: `0x140002a64`
- end: `0x140002a70`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001fd0`
- `0x140002050`
- `0x140002184`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002a64  xor     eax, eax
0x140002a66  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002a6c  setnz   al
0x140002a6f  retn
```
