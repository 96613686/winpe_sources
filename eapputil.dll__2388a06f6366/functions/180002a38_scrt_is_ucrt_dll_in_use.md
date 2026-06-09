# __scrt_is_ucrt_dll_in_use

- ea: `0x180002a38`
- end: `0x180002a44`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800021f4`
- `0x180002234`
- `0x1800022cc`
- `0x18000231c`
- `0x1800023b0`
- `0x1800024e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002a38  xor     eax, eax
0x180002a3a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002a40  setnz   al
0x180002a43  retn
```
