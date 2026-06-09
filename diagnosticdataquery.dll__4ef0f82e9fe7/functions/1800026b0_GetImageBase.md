# _GetImageBase

- ea: `0x1800026b0`
- end: `0x1800026c2`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003064`
- `0x1800032f4`
- `0x1800038f4`
- `0x180003bf4`
- `0x180003d0c`
- `0x1800047a0`
- `0x180004ac0`
- `0x180004ba8`

## callees

- `0x180002e18`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x1800026b0  sub     rsp, 28h
0x1800026b4  call    __vcrt_getptd
0x1800026b9  mov     rax, [rax+60h]
0x1800026bd  add     rsp, 28h
0x1800026c1  retn
```
