# decodeLPC

- ea: `0x180003cc4`
- end: `0x180003f83`
- name: `decodeLPC`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004f60`

## callees

- `0x180001400`
- `0x180003250`
- `0x180003320`
- `0x180003cc4`

## pseudocode

```c
void __fastcall decodeLPC(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 i; // r8
  int v9; // edx
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // eax
  __int64 j; // rdx
  int v15; // r8d
  int v16; // eax
  __int64 k; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 m; // rdx
  int v22; // r8d
  int v23; // eax
  __int128 v24; // xmm0
  __int64 v25; // rcx
  __int16 v26; // [rsp+30h] [rbp-50h] BYREF
  __int128 v27; // [rsp+32h] [rbp-4Eh]
  __int16 v28; // [rsp+48h] [rbp-38h]
  __int128 v29; // [rsp+4Ah] [rbp-36h]
  _BYTE v30[24]; // [rsp+60h] [rbp-20h] BYREF

  for ( i = 1; i != 9; ++i )
  {
    v9 = MIC[i] + *(__int16 *)(a2 + 2 * i);
    if ( v9 >= -32768 )
    {
      if ( v9 > 0x7FFF )
        LOWORD(v9) = 0x7FFF;
    }
    else
    {
      LOWORD(v9) = 0x8000;
    }
    v10 = (__int16)((_WORD)v9 << 10) - (__int16)(2 * B[i]);
    if ( v10 >= -32768 )
    {
      if ( v10 > 0x7FFF )
        LOWORD(v10) = 0x7FFF;
    }
    else
    {
      LOWORD(v10) = 0x8000;
    }
    v11 = (__int16)v10 * INVA[i] + 0x4000;
    if ( v11 >= 0x40000000 )
      v11 = 0x3FFFFFFF;
    v12 = (unsigned int)v11 >> 15;
    v13 = 2 * (__int16)v12;
    if ( v13 >= -32768 )
    {
      if ( v13 > 0x7FFF )
        LOWORD(v13) = 0x7FFF;
    }
    else
    {
      LOWORD(v13) = 0x8000;
    }
    *(&v28 + i) = v13;
  }
  for ( j = 1; j != 9; ++j )
  {
    v15 = (*(__int16 *)(a1 + 2 * j + 616) >> 2) + (*(&v28 + j) >> 2);
    if ( v15 >= -32768 )
    {
      if ( v15 > 0x7FFF )
        LOWORD(v15) = 0x7FFF;
    }
    else
    {
      LOWORD(v15) = 0x8000;
    }
    v16 = (*(__int16 *)(a1 + 2 * j + 616) >> 1) + (__int16)v15;
    if ( v16 >= -32768 )
    {
      if ( v16 > 0x7FFF )
        LOWORD(v16) = 0x7FFF;
    }
    else
    {
      LOWORD(v16) = 0x8000;
    }
    *(&v26 + j) = v16;
  }
  Comprp(v12, (__int64)&v26, (__int64)v30);
  Compsr(a1, a3, (__int64)v30, 0, 0xCu, a4);
  for ( k = 1; k != 9; ++k )
  {
    v18 = (unsigned int)(*(__int16 *)(a1 + 2 * k + 616) >> 1);
    v19 = v18 + (*(&v28 + k) >> 1);
    if ( v19 >= -32768 )
    {
      if ( v19 > 0x7FFF )
        LOWORD(v19) = 0x7FFF;
    }
    else
    {
      LOWORD(v19) = 0x8000;
    }
    *(&v26 + k) = v19;
  }
  Comprp(v18, (__int64)&v26, (__int64)v30);
  Compsr(a1, a3, (__int64)v30, 0xDu, 0x1Au, a4);
  for ( m = 1; m != 9; ++m )
  {
    v22 = (*(&v28 + m) >> 2) + (*(__int16 *)(a1 + 2 * m + 616) >> 2);
    if ( v22 >= -32768 )
    {
      if ( v22 > 0x7FFF )
        LOWORD(v22) = 0x7FFF;
    }
    else
    {
      LOWORD(v22) = 0x8000;
    }
    v23 = (*(&v28 + m) >> 1) + (__int16)v22;
    if ( v23 >= -32768 )
    {
      if ( v23 > 0x7FFF )
        LOWORD(v23) = 0x7FFF;
    }
    else
    {
      LOWORD(v23) = 0x8000;
    }
    *(&v26 + m) = v23;
  }
  Comprp(v20, (__int64)&v26, (__int64)v30);
  Compsr(a1, a3, (__int64)v30, 0x1Bu, 0x27u, a4);
  v24 = v29;
  v27 = v29;
  Comprp(v25, (__int64)&v26, (__int64)v30);
  Compsr(a1, a3, (__int64)v30, 0x28u, 0x9Fu, a4);
  *(_OWORD *)(a1 + 618) = v24;
}

```

## disassembly

```asm
0x180003cc4  push    rbp
0x180003cc6  push    rbx
0x180003cc7  push    rsi
0x180003cc8  push    rdi
0x180003cc9  push    r12
0x180003ccb  push    r14
0x180003ccd  push    r15
0x180003ccf  mov     rbp, rsp
0x180003cd2  sub     rsp, 80h
0x180003cd9  mov     rax, cs:__security_cookie
0x180003ce0  xor     rax, rsp
0x180003ce3  mov     [rbp+var_8], rax
0x180003ce7  mov     r12d, 1
0x180003ced  mov     rsi, r9
0x180003cf0  mov     rdi, r8
0x180003cf3  lea     r9, __ImageBase
0x180003cfa  mov     r8d, r12d
0x180003cfd  mov     r10, rdx
0x180003d00  mov     rbx, rcx
0x180003d03  mov     r15d, 0FFFF8000h
0x180003d09  mov     r14d, 7FFFh
0x180003d0f  movsx   edx, word ptr [r10+r8*2]
0x180003d14  movsx   eax, ds:rva MIC[r9+r8*2]
0x180003d1d  add     edx, eax
0x180003d1f  cmp     edx, r15d
0x180003d22  jge     short loc_180003D2A
0x180003d24  movzx   edx, r15w
0x180003d28  jmp     short loc_180003D32
0x180003d2a  cmp     edx, r14d
0x180003d2d  jle     short loc_180003D32
0x180003d2f  mov     edx, r14d
0x180003d32  movzx   eax, ds:rva B[r9+r8*2]
0x180003d3b  add     ax, ax
0x180003d3e  shl     dx, 0Ah
0x180003d42  movsx   ecx, ax
0x180003d45  movsx   eax, dx
0x180003d48  sub     eax, ecx
0x180003d4a  cmp     eax, r15d
0x180003d4d  jge     short loc_180003D55
0x180003d4f  movzx   eax, r15w
0x180003d53  jmp     short loc_180003D5D
0x180003d55  cmp     eax, r14d
0x180003d58  jle     short loc_180003D5D
0x180003d5a  mov     eax, r14d
0x180003d5d  movsx   ecx, ds:rva INVA[r9+r8*2]
0x180003d66  cwde
0x180003d67  imul    ecx, eax
0x180003d6a  mov     eax, 3FFFFFFFh
0x180003d6f  add     ecx, 4000h
0x180003d75  cmp     ecx, 40000000h
0x180003d7b  cmovge  ecx, eax
0x180003d7e  shr     ecx, 0Fh
0x180003d81  movsx   eax, cx
0x180003d84  add     eax, eax
0x180003d86  cmp     eax, r15d
0x180003d89  jge     short loc_180003D91
0x180003d8b  movzx   eax, r15w
0x180003d8f  jmp     short loc_180003D99
0x180003d91  cmp     eax, r14d
0x180003d94  jle     short loc_180003D99
0x180003d96  mov     eax, r14d
0x180003d99  mov     [rbp+r8*2+var_38], ax
0x180003d9f  add     r8, r12
0x180003da2  cmp     r8, 9
0x180003da6  jnz     loc_180003D0F
0x180003dac  mov     rdx, r12
0x180003daf  movsx   r9d, word ptr [rbx+rdx*2+268h]
0x180003db8  movsx   r8d, [rbp+rdx*2+var_38]
0x180003dbe  mov     eax, r9d
0x180003dc1  sar     eax, 2
0x180003dc4  sar     r8d, 2
0x180003dc8  add     r8d, eax
0x180003dcb  cmp     r8d, r15d
0x180003dce  jge     short loc_180003DD6
0x180003dd0  movzx   r8d, r15w
0x180003dd4  jmp     short loc_180003DDE
0x180003dd6  cmp     r8d, r14d
0x180003dd9  jle     short loc_180003DDE
0x180003ddb  mov     r8d, r14d
0x180003dde  sar     r9d, 1
0x180003de1  movsx   eax, r8w
0x180003de5  add     eax, r9d
0x180003de8  cmp     eax, r15d
0x180003deb  jge     short loc_180003DF3
0x180003ded  movzx   eax, r15w
0x180003df1  jmp     short loc_180003DFB
0x180003df3  cmp     eax, r14d
0x180003df6  jle     short loc_180003DFB
0x180003df8  mov     eax, r14d
0x180003dfb  mov     [rbp+rdx*2+var_50], ax
0x180003e00  add     rdx, r12
0x180003e03  cmp     rdx, 9
0x180003e07  jnz     short loc_180003DAF
0x180003e09  lea     r8, [rbp+var_20]
0x180003e0d  lea     rdx, [rbp+var_50]
0x180003e11  call    Comprp
0x180003e16  xor     r9d, r9d
0x180003e19  mov     [rsp+80h+var_58], rsi
0x180003e1e  lea     r8, [rbp+var_20]
0x180003e22  mov     [rsp+80h+var_60], 0Ch
0x180003e2a  mov     rcx, rbx
0x180003e2d  mov     rdx, rdi
0x180003e30  call    Compsr
0x180003e35  mov     rdx, r12
0x180003e38  movsx   ecx, word ptr [rbx+rdx*2+268h]
0x180003e40  movsx   eax, [rbp+rdx*2+var_38]
0x180003e45  sar     ecx, 1
0x180003e47  sar     eax, 1
0x180003e49  add     eax, ecx
0x180003e4b  cmp     eax, r15d
0x180003e4e  jge     short loc_180003E56
0x180003e50  movzx   eax, r15w
0x180003e54  jmp     short loc_180003E5E
0x180003e56  cmp     eax, r14d
0x180003e59  jle     short loc_180003E5E
0x180003e5b  mov     eax, r14d
0x180003e5e  mov     [rbp+rdx*2+var_50], ax
0x180003e63  add     rdx, r12
0x180003e66  cmp     rdx, 9
0x180003e6a  jnz     short loc_180003E38
0x180003e6c  lea     r8, [rbp+var_20]
0x180003e70  lea     rdx, [rbp+var_50]
0x180003e74  call    Comprp
0x180003e79  mov     r9d, 0Dh
0x180003e7f  mov     [rsp+80h+var_58], rsi
0x180003e84  lea     r8, [rbp+var_20]
0x180003e88  mov     [rsp+80h+var_60], 1Ah
0x180003e90  mov     rcx, rbx
0x180003e93  mov     rdx, rdi
0x180003e96  call    Compsr
0x180003e9b  mov     rdx, r12
0x180003e9e  movsx   r9d, [rbp+rdx*2+var_38]
0x180003ea4  movsx   r8d, word ptr [rbx+rdx*2+268h]
0x180003ead  mov     eax, r9d
0x180003eb0  sar     eax, 2
0x180003eb3  sar     r8d, 2
0x180003eb7  add     r8d, eax
0x180003eba  cmp     r8d, r15d
0x180003ebd  jge     short loc_180003EC5
0x180003ebf  movzx   r8d, r15w
0x180003ec3  jmp     short loc_180003ECD
0x180003ec5  cmp     r8d, r14d
0x180003ec8  jle     short loc_180003ECD
0x180003eca  mov     r8d, r14d
0x180003ecd  sar     r9d, 1
0x180003ed0  movsx   eax, r8w
0x180003ed4  add     eax, r9d
0x180003ed7  cmp     eax, r15d
0x180003eda  jge     short loc_180003EE2
0x180003edc  movzx   eax, r15w
0x180003ee0  jmp     short loc_180003EEA
0x180003ee2  cmp     eax, r14d
0x180003ee5  jle     short loc_180003EEA
0x180003ee7  mov     eax, r14d
0x180003eea  mov     [rbp+rdx*2+var_50], ax
0x180003eef  add     rdx, r12
0x180003ef2  cmp     rdx, 9
0x180003ef6  jnz     short loc_180003E9E
0x180003ef8  lea     r8, [rbp+var_20]
0x180003efc  lea     rdx, [rbp+var_50]
0x180003f00  call    Comprp
0x180003f05  mov     r9d, 1Bh
0x180003f0b  mov     [rsp+80h+var_58], rsi
0x180003f10  lea     r8, [rbp+var_20]
0x180003f14  mov     [rsp+80h+var_60], 27h ; '''
0x180003f1c  mov     rcx, rbx
0x180003f1f  mov     rdx, rdi
0x180003f22  call    Compsr
0x180003f27  movups  xmm0, [rbp+var_36]
0x180003f2b  lea     r8, [rbp+var_20]
0x180003f2f  lea     rdx, [rbp+var_50]
0x180003f33  movups  [rbp+var_4E], xmm0
0x180003f37  call    Comprp
0x180003f3c  mov     r9d, 28h ; '('
0x180003f42  mov     [rsp+80h+var_58], rsi
0x180003f47  lea     r8, [rbp+var_20]
0x180003f4b  mov     [rsp+80h+var_60], 9Fh
0x180003f53  mov     rcx, rbx
0x180003f56  mov     rdx, rdi
0x180003f59  call    Compsr
0x180003f5e  movups  xmmword ptr [rbx+26Ah], xmm0
0x180003f65  mov     rcx, [rbp+var_8]
0x180003f69  xor     rcx, rsp; StackCookie
0x180003f6c  call    __security_check_cookie
0x180003f71  add     rsp, 80h
0x180003f78  pop     r15
0x180003f7a  pop     r14
0x180003f7c  pop     r12
0x180003f7e  pop     rdi
0x180003f7f  pop     rsi
0x180003f80  pop     rbx
0x180003f81  pop     rbp
0x180003f82  retn
```
