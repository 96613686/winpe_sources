# _GetThrowImageBase

- ea: `0x1800026c8`
- end: `0x1800026da`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003064`
- `0x180003234`
- `0x1800033d8`
- `0x180003bf4`
- `0x180003d0c`
- `0x180003e28`
- `0x180004ac0`

## callees

- `0x180002e18`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x1800026c8  sub     rsp, 28h
0x1800026cc  call    __vcrt_getptd
0x1800026d1  mov     rax, [rax+68h]
0x1800026d5  add     rsp, 28h
0x1800026d9  retn
```
