# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c10`
- end: `0x180001c1c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001584`
- `0x1800015c4`
- `0x18000165c`
- `0x1800016ac`
- `0x180001740`
- `0x180001874`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c10  xor     eax, eax
0x180001c12  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c18  setnz   al
0x180001c1b  retn
```
