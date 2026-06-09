# Fill_ushort_ELUT_from_ParameterizedCurveFunc

- ea: `0x180007bb4`
- end: `0x180007dd5`
- name: `Fill_ushort_ELUT_from_ParameterizedCurveFunc`
- size: `545`
- prototype: `__int64 __fastcall(_WORD *, char, char, double (__fastcall *)(__int64, double *), double *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079d4`
- `0x180007ddc`

## callees

- `0x180007bb4`
- `0x18003e010`

## pseudocode

```c
__int64 __fastcall Fill_ushort_ELUT_from_ParameterizedCurveFunc(
        _WORD *a1,
        char a2,
        char a3,
        double (__fastcall *a4)(__int64, double *),
        double *a5)
{
  char v6; // r12
  int v7; // edi
  __int64 v8; // rcx
  signed int v9; // r13d
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  __int64 v12; // rbp
  __m128i v13; // xmm6
  __int64 v14; // r13
  double v15; // xmm6_8
  double v16; // xmm0_8
  int v17; // r8d
  unsigned int v18; // edi
  __int64 v19; // r10
  unsigned int v20; // r11d
  int v21; // ebp
  int i; // r9d
  __int64 v23; // rcx
  int v24; // eax
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // ebx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v32; // rcx
  __int64 v33; // rdi
  unsigned int v34; // ebx

  v6 = a2;
  if ( a3 <= 8 )
    return 87;
  v8 = (unsigned int)a2;
  v7 = 1 << a2;
  LOBYTE(v8) = a3;
  v9 = (1 << a3) - 1;
  v10 = 1;
  v11 = (1 << a2) - 1;
  if ( a2 > 6 )
  {
    v8 = (unsigned int)(a2 - 6);
    v10 = 1 << (a2 - 6);
  }
  v12 = 0;
  *a1 = 0;
  if ( 1 << a2 != 1 )
  {
    do
    {
      v8 = (unsigned int)(int)(a4(v8, a5) * (double)v9);
      a1[v12] = v8;
      v12 = v10 + (unsigned int)v12;
    }
    while ( (unsigned int)v12 < v11 );
    v6 = a2;
  }
  v13 = _mm_cvtsi32_si128(v9);
  v14 = (unsigned int)(v7 - 1);
  v15 = _mm_cvtepi32_pd(v13).m128d_f64[0];
  v16 = a4(v8, a5);
  v17 = 0;
  a1[v14] = (int)(v16 * v15);
  v18 = v7 - v10;
  if ( v18 )
  {
    do
    {
      v19 = v17 + v10;
      v20 = 1;
      v21 = (unsigned __int16)a1[v17];
      for ( i = (unsigned __int16)a1[v19] - v21; v20 < v10; a1[v23] = v21 + (((v24 << 8) / v10 + 128) >> 8) )
      {
        v23 = v20 + v17;
        v24 = v20 * i;
        ++v20;
      }
      v17 += v10;
    }
    while ( (unsigned int)v19 < v18 );
  }
  v25 = (unsigned __int16)a1[v18];
  v26 = 1;
  v27 = (unsigned int)(unsigned __int16)a1[v14] - v25;
  v28 = v10 - 1;
  if ( v28 > 1 )
  {
    do
    {
      v29 = (unsigned int)v26 + v18;
      v30 = v26 * v27;
      v26 = (unsigned int)(v26 + 1);
      a1[v29] = v25 + (((v30 << 8) / v28 + 128) >> 8);
    }
    while ( (unsigned int)v26 < v28 );
  }
  if ( v6 > 6 && *a5 < 1.0 )
  {
    v32 = (unsigned int)(v6 - 6);
    v33 = 0;
    v34 = 1 << (v6 - 6);
    if ( v34 )
    {
      do
      {
        LODWORD(v32) = (int)(((double (__fastcall *)(__int64, double *, __int64, __int64))a4)(v32, a5, v26, v27) * v15);
        a1[v33] = v32;
        v33 = (unsigned int)(v33 + 1);
      }
      while ( (unsigned int)v33 < v34 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007bb4  mov     rax, rsp
0x180007bb7  mov     [rax+8], rbx
0x180007bbb  mov     [rax+20h], r9
0x180007bbf  mov     [rax+10h], dl
0x180007bc2  push    rbp
0x180007bc3  push    rsi
0x180007bc4  push    rdi
0x180007bc5  push    r12
0x180007bc7  push    r13
0x180007bc9  push    r14
0x180007bcb  push    r15
0x180007bcd  sub     rsp, 50h
0x180007bd1  movaps  xmmword ptr [rax-48h], xmm6
0x180007bd5  mov     rsi, rcx
0x180007bd8  movaps  xmmword ptr [rax-58h], xmm7
0x180007bdc  movaps  xmmword ptr [rax-68h], xmm8
0x180007be1  movsx   r12d, dl
0x180007be5  cmp     r8b, 8
0x180007be9  jle     loc_180007DCE
0x180007bef  movsd   xmm8, cs:__real@3ff0000000000000
0x180007bf8  mov     r9d, 1
0x180007bfe  mov     ecx, r12d
0x180007c01  mov     edi, r9d
0x180007c04  shl     edi, cl
0x180007c06  xorps   xmm0, xmm0
0x180007c09  mov     cl, r8b
0x180007c0c  mov     r13d, r9d
0x180007c0f  shl     r13d, cl
0x180007c12  movaps  xmm7, xmm8
0x180007c16  dec     r13d
0x180007c19  mov     ebx, r9d
0x180007c1c  lea     r14d, [rdi-1]
0x180007c20  mov     eax, r14d
0x180007c23  cvtsi2sd xmm0, rax
0x180007c28  divsd   xmm7, xmm0
0x180007c2c  cmp     r12b, 6
0x180007c30  jle     short loc_180007C39
0x180007c32  lea     ecx, [r12-6]
0x180007c37  shl     ebx, cl
0x180007c39  mov     r15, [rsp+88h+arg_20]
0x180007c41  xor     eax, eax
0x180007c43  xor     ebp, ebp
0x180007c45  mov     [rsi], ax
0x180007c48  test    r14d, r14d
0x180007c4b  jz      short loc_180007C92
0x180007c4d  mov     r12, [rsp+88h+arg_18]
0x180007c55  movd    xmm6, r13d
0x180007c5a  cvtdq2pd xmm6, xmm6
0x180007c5e  xorps   xmm0, xmm0
0x180007c61  mov     eax, ebp
0x180007c63  mov     rdx, r15
0x180007c66  cvtsi2sd xmm0, rax
0x180007c6b  mov     rax, r12
0x180007c6e  mulsd   xmm0, xmm7
0x180007c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c77  mulsd   xmm0, xmm6
0x180007c7b  cvttsd2si ecx, xmm0
0x180007c7f  mov     [rsi+rbp*2], cx
0x180007c83  add     ebp, ebx
0x180007c85  cmp     ebp, r14d
0x180007c88  jb      short loc_180007C5E
0x180007c8a  mov     r12b, [rsp+88h+arg_8]
0x180007c92  mov     r14, [rsp+88h+arg_18]
0x180007c9a  mov     rdx, r15
0x180007c9d  movd    xmm6, r13d
0x180007ca2  mov     rax, r14
0x180007ca5  movaps  xmm0, xmm8
0x180007ca9  lea     r13d, [rdi-1]
0x180007cad  cvtdq2pd xmm6, xmm6
0x180007cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb6  xor     r8d, r8d
0x180007cb9  mulsd   xmm0, xmm6
0x180007cbd  cvttsd2si eax, xmm0
0x180007cc1  mov     [rsi+r13*2], ax
0x180007cc6  sub     edi, ebx
0x180007cc8  jz      short loc_180007D17
0x180007cca  mov     eax, r8d
0x180007ccd  lea     r10d, [r8+rbx]
0x180007cd1  movzx   r9d, word ptr [rsi+r10*2]
0x180007cd6  mov     r11d, 1
0x180007cdc  movzx   ebp, word ptr [rsi+rax*2]
0x180007ce0  sub     r9d, ebp
0x180007ce3  cmp     ebx, r11d
0x180007ce6  jbe     short loc_180007D0F
0x180007ce8  xor     edx, edx
0x180007cea  lea     ecx, [r11+r8]
0x180007cee  mov     eax, r9d
0x180007cf1  imul    eax, r11d
0x180007cf5  inc     r11d
0x180007cf8  shl     eax, 8
0x180007cfb  div     ebx
0x180007cfd  sub     eax, 0FFFFFF80h
0x180007d00  shr     eax, 8
0x180007d03  add     ax, bp
0x180007d06  mov     [rsi+rcx*2], ax
0x180007d0a  cmp     r11d, ebx
0x180007d0d  jb      short loc_180007CE8
0x180007d0f  mov     r8d, r10d
0x180007d12  cmp     r10d, edi
0x180007d15  jb      short loc_180007CCA
0x180007d17  movzx   r10d, word ptr [rsi+rdi*2]
0x180007d1c  mov     ebp, 1
0x180007d21  movzx   r9d, word ptr [rsi+r13*2]
0x180007d26  mov     r8d, ebp
0x180007d29  sub     r9d, r10d
0x180007d2c  dec     ebx
0x180007d2e  cmp     ebx, ebp
0x180007d30  jbe     short loc_180007D5A
0x180007d32  xor     edx, edx
0x180007d34  lea     ecx, [r8+rdi]
0x180007d38  mov     eax, r9d
0x180007d3b  imul    eax, r8d
0x180007d3f  add     r8d, ebp
0x180007d42  shl     eax, 8
0x180007d45  div     ebx
0x180007d47  sub     eax, 0FFFFFF80h
0x180007d4a  shr     eax, 8
0x180007d4d  add     ax, r10w
0x180007d51  mov     [rsi+rcx*2], ax
0x180007d55  cmp     r8d, ebx
0x180007d58  jb      short loc_180007D32
0x180007d5a  cmp     r12b, 6
0x180007d5e  jg      short loc_180007D89
0x180007d60  xor     eax, eax
0x180007d62  movaps  xmm6, [rsp+88h+var_48]
0x180007d67  lea     r11, [rsp+88h+var_38]
0x180007d6c  mov     rbx, [r11+40h]
0x180007d70  movaps  xmm8, xmmword ptr [r11-30h]
0x180007d75  movaps  xmm7, [rsp+88h+var_58]
0x180007d7a  mov     rsp, r11
0x180007d7d  pop     r15
0x180007d7f  pop     r14
0x180007d81  pop     r13
0x180007d83  pop     r12
0x180007d85  pop     rdi
0x180007d86  pop     rsi
0x180007d87  pop     rbp
0x180007d88  retn
0x180007d89  comisd  xmm8, qword ptr [r15]
0x180007d8e  jbe     short loc_180007D60
0x180007d90  movsx   ecx, r12b
0x180007d94  mov     ebx, ebp
0x180007d96  add     ecx, 0FFFFFFFAh
0x180007d99  xor     edi, edi
0x180007d9b  shl     ebx, cl
0x180007d9d  test    ebx, ebx
0x180007d9f  jz      short loc_180007D60
0x180007da1  xorps   xmm0, xmm0
0x180007da4  mov     eax, edi
0x180007da6  mov     rdx, r15
0x180007da9  cvtsi2sd xmm0, rax
0x180007dae  mov     rax, r14
0x180007db1  mulsd   xmm0, xmm7
0x180007db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dba  mulsd   xmm0, xmm6
0x180007dbe  cvttsd2si ecx, xmm0
0x180007dc2  mov     [rsi+rdi*2], cx
0x180007dc6  add     edi, ebp
0x180007dc8  cmp     edi, ebx
0x180007dca  jb      short loc_180007DA1
0x180007dcc  jmp     short loc_180007D60
0x180007dce  mov     eax, 57h ; 'W'
0x180007dd3  jmp     short loc_180007D62
```
