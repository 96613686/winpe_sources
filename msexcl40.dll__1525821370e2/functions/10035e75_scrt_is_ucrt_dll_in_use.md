# ___scrt_is_ucrt_dll_in_use

- ea: `0x10035e75`
- end: `0x10035e81`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x10035586`
- `0x100355c0`
- `0x10035638`
- `0x10035674`
- `0x100356f1`
- `0x1003581d`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return __scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x10035e75  xor     eax, eax
0x10035e77  cmp     ___scrt_ucrt_dll_is_in_use, eax
0x10035e7d  setnz   al
0x10035e80  retn
```
