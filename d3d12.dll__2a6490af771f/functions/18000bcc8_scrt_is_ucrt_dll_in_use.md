# __scrt_is_ucrt_dll_in_use

- ea: `0x18000bcc8`
- end: `0x18000bcd4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000b434`
- `0x18000b474`
- `0x18000b50c`
- `0x18000b55c`
- `0x18000b5f0`
- `0x18000b724`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000bcc8  xor     eax, eax
0x18000bcca  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000bcd0  setnz   al
0x18000bcd3  retn
```
