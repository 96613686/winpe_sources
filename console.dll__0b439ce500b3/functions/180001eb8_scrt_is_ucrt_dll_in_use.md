# __scrt_is_ucrt_dll_in_use

- ea: `0x180001eb8`
- end: `0x180001ec4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015d4`
- `0x180001614`
- `0x1800016ac`
- `0x1800016fc`
- `0x180001790`
- `0x1800018c4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001eb8  xor     eax, eax
0x180001eba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ec0  setnz   al
0x180001ec3  retn
```
