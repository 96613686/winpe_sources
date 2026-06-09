# __scrt_is_ucrt_dll_in_use

- ea: `0x180013724`
- end: `0x180013730`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180012c90`
- `0x180012ccc`
- `0x180012d58`
- `0x180012db8`
- `0x180012e48`
- `0x180012f6c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180013724  xor     eax, eax
0x180013726  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001372c  setnz   al
0x18001372f  retn
```
