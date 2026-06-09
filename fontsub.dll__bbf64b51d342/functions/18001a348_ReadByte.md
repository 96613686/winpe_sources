# ReadByte

- ea: `0x18001a348`
- end: `0x18001a378`
- name: `ReadByte`
- size: `48`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b040`
- `0x18000b5d0`
- `0x18000b760`
- `0x18000c350`
- `0x18000c708`
- `0x18000fd08`
- `0x180010284`
- `0x1800118bc`
- `0x18001a3bc`

## callees

- `0x18001a208`
- `0x18001a348`

## pseudocode

```c
__int64 __fastcall ReadByte(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  _QWORD *v4; // rcx
  __int64 v5; // r9
  _BYTE *v6; // r11

  result = CheckInOffset(a1, a3, 1);
  if ( !(_WORD)result )
  {
    result = 0;
    *v6 = *(_BYTE *)(v5 + *v4);
  }
  return result;
}

```

## disassembly

```asm
0x18001a348  sub     rsp, 28h
0x18001a34c  mov     r9d, r8d
0x18001a34f  mov     r11, rdx
0x18001a352  mov     edx, r9d
0x18001a355  mov     r8d, 1
0x18001a35b  call    CheckInOffset
0x18001a360  xor     edx, edx
0x18001a362  test    ax, ax
0x18001a365  jnz     short loc_18001A373
0x18001a367  mov     rax, [rcx]
0x18001a36a  mov     cl, [r9+rax]
0x18001a36e  mov     eax, edx
0x18001a370  mov     [r11], cl
0x18001a373  add     rsp, 28h
0x18001a377  retn
```
