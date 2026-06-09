# _GetImageBase

- ea: `0x1800193a4`
- end: `0x1800193b6`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180019794`
- `0x180019a24`
- `0x180019b08`
- `0x180019fc4`
- `0x18001a204`
- `0x18001a31c`
- `0x18001a8f8`
- `0x18001ab28`
- `0x18001ac10`

## callees

- `0x1800194ec`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x1800193a4  sub     rsp, 28h
0x1800193a8  call    __vcrt_getptd
0x1800193ad  mov     rax, [rax+60h]
0x1800193b1  add     rsp, 28h
0x1800193b5  retn
```
