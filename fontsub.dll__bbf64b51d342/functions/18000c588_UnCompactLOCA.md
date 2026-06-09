# UnCompactLOCA

- ea: `0x18000c588`
- end: `0x18000c6ff`
- name: `UnCompactLOCA`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c874`

## callees

- `0x18000c588`
- `0x180019a40`
- `0x18001a620`
- `0x18001a680`
- `0x18001aa68`
- `0x18001aadc`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall UnCompactLOCA(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned __int16 v8; // si
  __int64 result; // rax
  unsigned int v13; // ebx
  unsigned __int16 v14; // di
  unsigned int v15; // ebx
  unsigned __int16 v16; // di
  __int16 v17[2]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-54h] BYREF
  int v19; // [rsp+28h] [rbp-50h]
  _OWORD v20[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+60h] [rbp-18h]

  v8 = 0;
  v19 = a4;
  v17[0] = 0;
  v18 = 0;
  *a8 = 0;
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( !(unsigned int)GetGeneric(a1, v20, 0) )
    return 1032;
  if ( WORD1(v21) )
  {
    result = ReadLong(a1, &v18, a3);
    if ( (_WORD)result )
      return result;
    v15 = a3 + 4;
    v16 = 0;
    while ( v8 <= a5 )
    {
      result = WriteLong(a2, v18, (unsigned int)(*a8 + v19));
      if ( (_WORD)result )
        return result;
      *a8 += 4;
      if ( v16 < a6 && v8 == *(_WORD *)(a7 + 2LL * v16) )
      {
        result = ReadLong(a1, &v18, v15);
        if ( (_WORD)result )
          return result;
        v15 += 4;
        ++v16;
      }
      ++v8;
    }
  }
  else
  {
    result = ReadWord(a1, (__int64)v17, a3);
    if ( (_WORD)result )
      return result;
    v13 = a3 + 2;
    v14 = 0;
    while ( v8 <= a5 )
    {
      result = WriteWord(a2, v17[0], *a8 + v19);
      if ( (_WORD)result )
        return result;
      *a8 += 2;
      if ( v14 < a6 && v8 == *(_WORD *)(a7 + 2LL * v14) )
      {
        result = ReadWord(a1, (__int64)v17, v13);
        if ( (_WORD)result )
          return result;
        v13 += 2;
        ++v14;
      }
      ++v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c588  push    rbp
0x18000c58a  push    rbx
0x18000c58b  push    rsi
0x18000c58c  push    rdi
0x18000c58d  push    r12
0x18000c58f  push    r13
0x18000c591  push    r14
0x18000c593  push    r15
0x18000c595  mov     rbp, rsp
0x18000c598  sub     rsp, 78h
0x18000c59c  mov     rax, cs:__security_cookie
0x18000c5a3  xor     rax, rsp
0x18000c5a6  mov     [rbp+var_10], rax
0x18000c5aa  mov     r14, [rbp+arg_38]
0x18000c5b1  xorps   xmm0, xmm0
0x18000c5b4  xor     esi, esi
0x18000c5b6  mov     [rbp+var_50], r9d
0x18000c5ba  mov     ebx, r8d
0x18000c5bd  mov     [rbp+var_58], si
0x18000c5c1  mov     r13, rdx
0x18000c5c4  mov     [rbp+var_54], esi
0x18000c5c7  xor     eax, eax
0x18000c5c9  mov     [r14], esi
0x18000c5cc  xor     r8d, r8d
0x18000c5cf  mov     [rbp+var_18], rax
0x18000c5d3  lea     rdx, [rbp+var_48]
0x18000c5d7  mov     r15, rcx
0x18000c5da  movups  [rbp+var_48], xmm0
0x18000c5de  movups  [rbp+var_38], xmm0
0x18000c5e2  movups  [rbp+var_28], xmm0
0x18000c5e6  call    GetGeneric
0x18000c5eb  test    eax, eax
0x18000c5ed  jnz     short loc_18000C5F9
0x18000c5ef  mov     eax, 408h
0x18000c5f4  jmp     loc_18000C6E2
0x18000c5f9  mov     r8d, ebx
0x18000c5fc  mov     rcx, r15
0x18000c5ff  cmp     word ptr [rbp+var_18+2], si
0x18000c603  jnz     short loc_18000C679
0x18000c605  lea     rdx, [rbp+var_58]
0x18000c609  call    ReadWord
0x18000c60e  test    ax, ax
0x18000c611  jnz     loc_18000C6E2
0x18000c617  mov     r12, [rbp+arg_30]
0x18000c61b  add     ebx, 2
0x18000c61e  mov     edi, esi
0x18000c620  cmp     si, [rbp+arg_20]
0x18000c624  ja      loc_18000C6E0
0x18000c62a  mov     r8d, [rbp+var_50]
0x18000c62e  mov     rcx, r13
0x18000c631  add     r8d, [r14]
0x18000c634  movzx   edx, [rbp+var_58]
0x18000c638  call    WriteWord
0x18000c63d  test    ax, ax
0x18000c640  jnz     loc_18000C6E2
0x18000c646  add     dword ptr [r14], 2
0x18000c64a  cmp     di, [rbp+arg_28]
0x18000c64e  jnb     short loc_18000C674
0x18000c650  movzx   eax, di
0x18000c653  cmp     si, [r12+rax*2]
0x18000c658  jnz     short loc_18000C674
0x18000c65a  mov     r8d, ebx
0x18000c65d  lea     rdx, [rbp+var_58]
0x18000c661  mov     rcx, r15
0x18000c664  call    ReadWord
0x18000c669  test    ax, ax
0x18000c66c  jnz     short loc_18000C6E2
0x18000c66e  add     ebx, 2
0x18000c671  inc     di
0x18000c674  inc     si
0x18000c677  jmp     short loc_18000C620
0x18000c679  lea     rdx, [rbp+var_54]
0x18000c67d  call    ReadLong
0x18000c682  test    ax, ax
0x18000c685  jnz     short loc_18000C6E2
0x18000c687  mov     r12, [rbp+arg_30]
0x18000c68b  add     ebx, 4
0x18000c68e  mov     edi, esi
0x18000c690  cmp     si, [rbp+arg_20]
0x18000c694  ja      short loc_18000C6E0
0x18000c696  mov     r8d, [rbp+var_50]
0x18000c69a  mov     rcx, r13
0x18000c69d  add     r8d, [r14]
0x18000c6a0  mov     edx, [rbp+var_54]
0x18000c6a3  call    WriteLong
0x18000c6a8  test    ax, ax
0x18000c6ab  jnz     short loc_18000C6E2
0x18000c6ad  add     dword ptr [r14], 4
0x18000c6b1  cmp     di, [rbp+arg_28]
0x18000c6b5  jnb     short loc_18000C6DB
0x18000c6b7  movzx   eax, di
0x18000c6ba  cmp     si, [r12+rax*2]
0x18000c6bf  jnz     short loc_18000C6DB
0x18000c6c1  mov     r8d, ebx
0x18000c6c4  lea     rdx, [rbp+var_54]
0x18000c6c8  mov     rcx, r15
0x18000c6cb  call    ReadLong
0x18000c6d0  test    ax, ax
0x18000c6d3  jnz     short loc_18000C6E2
0x18000c6d5  add     ebx, 4
0x18000c6d8  inc     di
0x18000c6db  inc     si
0x18000c6de  jmp     short loc_18000C690
0x18000c6e0  xor     eax, eax
0x18000c6e2  mov     rcx, [rbp+var_10]
0x18000c6e6  xor     rcx, rsp; StackCookie
0x18000c6e9  call    __security_check_cookie
0x18000c6ee  add     rsp, 78h
0x18000c6f2  pop     r15
0x18000c6f4  pop     r14
0x18000c6f6  pop     r13
0x18000c6f8  pop     r12
0x18000c6fa  pop     rdi
0x18000c6fb  pop     rsi
0x18000c6fc  pop     rbx
0x18000c6fd  pop     rbp
0x18000c6fe  retn
```
