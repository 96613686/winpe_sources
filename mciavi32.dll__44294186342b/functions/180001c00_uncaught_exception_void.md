# __uncaught_exception(void)

- ea: `0x180001c00`
- end: `0x180001c0c`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001574`
- `0x1800015b4`
- `0x18000164c`
- `0x18000169c`
- `0x180001730`
- `0x180001864`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_180018070 != 0;
}

```

## disassembly

```asm
0x180001c00  xor     eax, eax
0x180001c02  cmp     cs:dword_180018070, eax
0x180001c08  setnz   al
0x180001c0b  retn
```
