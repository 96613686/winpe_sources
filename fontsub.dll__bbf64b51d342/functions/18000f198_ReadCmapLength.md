# ReadCmapLength

- ea: `0x18000f198`
- end: `0x18000f25c`
- name: `ReadCmapLength`
- size: `196`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180009010`
- `0x18000e4c8`
- `0x1800115ac`
- `0x1800118bc`
- `0x1800143f0`

## callees

- `0x18000f198`
- `0x18001a620`
- `0x18001a680`

## pseudocode

```c
__int64 __fastcall ReadCmapLength(__int64 a1, __int64 a2, unsigned int a3, _WORD *a4)
{
  __int64 result; // rax
  _WORD *v8; // r10
  unsigned int v9; // ebx
  __int64 v10; // r10
  unsigned __int16 v11; // [rsp+50h] [rbp+18h] BYREF

  result = ReadWord(a1, a2, a3);
  if ( (_WORD)result )
    return result;
  v9 = a3 + 2;
  if ( !*v8 || *v8 == 1 || *v8 == 2 || *v8 == 3 || *v8 == 4 || *v8 == 5 || *v8 == 6 || *v8 == 7 )
  {
    v11 = 0;
    result = ReadWord(a1, (__int64)&v11, v9);
    if ( (_WORD)result )
      return result;
    *(_DWORD *)(v10 + 4) = v11;
    goto LABEL_16;
  }
  if ( *v8 != 14 )
    v9 = a3 + 4;
  result = ReadLong(a1, v8 + 2, v9);
  if ( !(_WORD)result )
  {
LABEL_16:
    if ( a4 )
      *a4 = v9 - a3 + 4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f198  mov     [rsp+arg_0], rbx
0x18000f19d  mov     [rsp+arg_8], rbp
0x18000f1a2  push    rsi
0x18000f1a3  push    rdi
0x18000f1a4  push    r14
0x18000f1a6  sub     rsp, 20h
0x18000f1aa  mov     rsi, r9
0x18000f1ad  mov     ebp, r8d
0x18000f1b0  mov     r10, rdx
0x18000f1b3  mov     rdi, rcx
0x18000f1b6  call    ReadWord
0x18000f1bb  xor     r14d, r14d
0x18000f1be  test    ax, ax
0x18000f1c1  jnz     loc_18000F249
0x18000f1c7  movzx   ecx, word ptr [r10]
0x18000f1cb  lea     ebx, [rbp+2]
0x18000f1ce  test    ecx, ecx
0x18000f1d0  jz      short loc_18000F213
0x18000f1d2  sub     ecx, 1
0x18000f1d5  jz      short loc_18000F213
0x18000f1d7  sub     ecx, 1
0x18000f1da  jz      short loc_18000F213
0x18000f1dc  sub     ecx, 1
0x18000f1df  jz      short loc_18000F213
0x18000f1e1  sub     ecx, 1
0x18000f1e4  jz      short loc_18000F213
0x18000f1e6  sub     ecx, 1
0x18000f1e9  jz      short loc_18000F213
0x18000f1eb  sub     ecx, 1
0x18000f1ee  jz      short loc_18000F213
0x18000f1f0  sub     ecx, 1
0x18000f1f3  jz      short loc_18000F213
0x18000f1f5  cmp     ecx, 7
0x18000f1f8  lea     rdx, [r10+4]
0x18000f1fc  mov     rcx, rdi
0x18000f1ff  jz      short loc_18000F204
0x18000f201  add     ebx, 2
0x18000f204  mov     r8d, ebx
0x18000f207  call    ReadLong
0x18000f20c  test    ax, ax
0x18000f20f  jz      short loc_18000F237
0x18000f211  jmp     short loc_18000F249
0x18000f213  mov     r8d, ebx
0x18000f216  mov     [rsp+38h+arg_10], r14w
0x18000f21c  lea     rdx, [rsp+38h+arg_10]
0x18000f221  mov     rcx, rdi
0x18000f224  call    ReadWord
0x18000f229  test    ax, ax
0x18000f22c  jnz     short loc_18000F249
0x18000f22e  movzx   eax, [rsp+38h+arg_10]
0x18000f233  mov     [r10+4], eax
0x18000f237  test    rsi, rsi
0x18000f23a  jz      short loc_18000F246
0x18000f23c  sub     bx, bp
0x18000f23f  add     bx, 4
0x18000f243  mov     [rsi], bx
0x18000f246  mov     eax, r14d
0x18000f249  mov     rbx, [rsp+38h+arg_0]
0x18000f24e  mov     rbp, [rsp+38h+arg_8]
0x18000f253  add     rsp, 20h
0x18000f257  pop     r14
0x18000f259  pop     rdi
0x18000f25a  pop     rsi
0x18000f25b  retn
```
