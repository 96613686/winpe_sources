# __uncaught_exception(void)

- ea: `0x180002078`
- end: `0x180002084`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001814`
- `0x180001854`
- `0x1800018ec`
- `0x18000193c`
- `0x1800019d0`
- `0x180001b04`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_1800305F0 != 0;
}

```

## disassembly

```asm
0x180002078  xor     eax, eax
0x18000207a  cmp     cs:dword_1800305F0, eax
0x180002080  setnz   al
0x180002083  retn
```
