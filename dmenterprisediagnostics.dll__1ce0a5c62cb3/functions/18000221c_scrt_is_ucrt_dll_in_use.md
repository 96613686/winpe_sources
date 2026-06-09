# __scrt_is_ucrt_dll_in_use

- ea: `0x18000221c`
- end: `0x180002228`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001930`
- `0x180001970`
- `0x180001a08`
- `0x180001a58`
- `0x180001aec`
- `0x180001c20`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000221c  xor     eax, eax
0x18000221e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002224  setnz   al
0x180002227  retn
```
