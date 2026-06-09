# WriteTableFromStructure

- ea: `0x180016e9c`
- end: `0x1800175ee`
- name: `WriteTableFromStructure`
- size: `1874`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800154a4`

## callees

- `0x18001544c`
- `0x180016dd8`
- `0x180016e9c`
- `0x18001986c`
- `0x18001a060`
- `0x18001a2cc`
- `0x18001a808`
- `0x18001aadc`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall WriteTableFromStructure(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int16 *a5,
        _DWORD *a6,
        unsigned int *a7,
        _WORD *a8,
        unsigned __int16 *a9)
{
  int v9; // edi
  int v10; // r15d
  __int64 v11; // rax
  __int16 v12; // r11
  __int16 v13; // r8
  unsigned __int16 v14; // r9
  __int16 v15; // cx
  __int16 v16; // bx
  __int64 v17; // r12
  __int16 v18; // r11
  unsigned int v19; // esi
  __int64 v20; // rax
  int v21; // r13d
  unsigned int v22; // ebx
  unsigned __int16 i; // r15
  __int64 v24; // r12
  __int16 result; // ax
  unsigned __int16 v26; // cx
  unsigned int v27; // r15d
  unsigned int v28; // ebx
  unsigned __int16 j; // r15
  __int64 v30; // rax
  __int64 v31; // r12
  __int64 v32; // rdx
  int v33; // r13d
  unsigned __int16 v34; // cx
  __int64 v35; // r15
  unsigned int v36; // r15d
  unsigned __int16 v37; // r12
  unsigned int v38; // ebx
  __int64 v39; // rdx
  __int64 v40; // r15
  int v41; // r13d
  unsigned __int16 v42; // di
  unsigned int v43; // r15d
  int v44; // r12d
  int v45; // r13d
  unsigned __int16 v46; // r15
  size_t Size; // [rsp+20h] [rbp-A1h]
  size_t Sizea; // [rsp+20h] [rbp-A1h]
  size_t Sizeb; // [rsp+20h] [rbp-A1h]
  size_t Sizec; // [rsp+20h] [rbp-A1h]
  _WORD v51[2]; // [rsp+30h] [rbp-91h] BYREF
  unsigned int v52; // [rsp+34h] [rbp-8Dh] BYREF
  unsigned int v53; // [rsp+38h] [rbp-89h]
  int v54; // [rsp+3Ch] [rbp-85h]
  __int64 v55; // [rsp+40h] [rbp-81h]
  int v56; // [rsp+48h] [rbp-79h]
  __int64 v57; // [rsp+50h] [rbp-71h] BYREF
  int v58; // [rsp+58h] [rbp-69h]
  unsigned int v59; // [rsp+60h] [rbp-61h]
  int v60[2]; // [rsp+68h] [rbp-59h]
  unsigned __int16 *v61; // [rsp+70h] [rbp-51h]
  _WORD *v62; // [rsp+78h] [rbp-49h]
  unsigned int *v63; // [rsp+80h] [rbp-41h]
  _DWORD *v64; // [rsp+88h] [rbp-39h]
  __int16 v65; // [rsp+90h] [rbp-31h] BYREF
  __int16 v66; // [rsp+92h] [rbp-2Fh]
  int v67; // [rsp+94h] [rbp-2Dh]
  _BYTE v68[12]; // [rsp+98h] [rbp-29h]
  __int64 v69; // [rsp+A4h] [rbp-1Dh]

  v9 = 0;
  v55 = a1;
  v10 = a4;
  v56 = a4;
  v57 = 0;
  *a6 = 0;
  v58 = 0;
  *a7 = 0;
  v11 = *((_QWORD *)a5 + 2);
  v53 = a2;
  *(_QWORD *)v60 = a3;
  v64 = a6;
  *a8 = *(_WORD *)(v11 + 16);
  *a9 = 0;
  v12 = *a5;
  v63 = a7;
  v62 = a8;
  v61 = a9;
  v51[0] = 0;
  if ( v12 == 2 || v12 == 5 )
  {
    if ( (unsigned __int16)a5[4] <= 1u )
      goto LABEL_10;
    v13 = 1;
    v14 = 1;
    do
    {
      v15 = 0;
      if ( *(unsigned __int16 *)(32LL * v14 + *((_QWORD *)a5 + 2) + 16) <= (unsigned int)*(unsigned __int16 *)(32LL * v14 + *((_QWORD *)a5 + 2) - 16)
                                                                         + 1 )
        v15 = v13;
      ++v14;
      v13 = v15;
    }
    while ( v14 < (unsigned __int16)a5[4] );
    if ( v15 )
LABEL_10:
      *a5 = 2;
    else
      *a5 = 5;
  }
  v16 = a5[1];
  v17 = (__int64)a5;
  if ( (unsigned int)LookupGlyphOffset(
                       *(_QWORD *)(*((_QWORD *)a5 + 2) + 24LL),
                       *(unsigned int *)(*((_QWORD *)a5 + 2) + 8LL),
                       &v57) )
  {
    if ( (_WORD)v58 != v16 )
      return 0;
    v10 = v57;
    v59 = HIDWORD(v57);
    v56 = v57;
    v54 = 0;
  }
  else
  {
    LOWORD(v54) = 1;
    LODWORD(v57) = v10;
    v59 = 0;
    HIWORD(v58) = v18;
    LOWORD(v58) = v16;
  }
  v19 = 0;
  switch ( v18 )
  {
    case 1:
      return 1006;
    case 2:
      *(_DWORD *)v68 = *((_DWORD *)a5 + 1);
      *(_QWORD *)&v68[4] = *((_QWORD *)a5 + 3);
      v67 = v10;
      v43 = v53;
      v65 = v18;
      v66 = v16;
      result = WriteGeneric(v55, (__int64)&v65, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, v53, v51);
      if ( result )
        return result;
      v44 = *(_DWORD *)v68;
      v22 = v43 + v51[0];
      v45 = v67;
      v46 = 0;
      v52 = v22;
      while ( v46 < (unsigned __int16)a5[4] )
      {
        if ( !v46
          || *(_WORD *)(32LL * v46 + *((_QWORD *)a5 + 2) + 16) != *(_WORD *)(32LL * v46 + *((_QWORD *)a5 + 2) - 16) )
        {
          if ( (_WORD)v54 )
          {
            LODWORD(Sizec) = v44;
            result = CopyBlockOver(
                       v60[0],
                       *(_QWORD *)(32LL * v46 + *((_QWORD *)a5 + 2)),
                       v19 + v45,
                       *(_DWORD *)(32LL * v46 + *((_QWORD *)a5 + 2) + 8),
                       Sizec);
            if ( result )
              return result;
          }
          v19 += v44;
          LOWORD(v9) = v9 + 1;
        }
        ++v46;
      }
      v42 = *v62 + v9 - 1;
LABEL_69:
      *v61 = v42;
      goto LABEL_70;
    case 3:
      v67 = v10;
      v36 = v53;
      *(_DWORD *)v68 = 0;
      v65 = v18;
      v66 = v16;
      result = WriteGeneric(v55, (__int64)&v65, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, v53, v51);
      if ( result )
        return result;
      v37 = 0;
      v38 = v36 + v51[0];
      while ( v37 < (unsigned __int16)a5[4] )
      {
        if ( !v37
          || *(_WORD *)(32LL * v37 + *((_QWORD *)a5 + 2) + 16) != *(_WORD *)(32LL * v37 + *((_QWORD *)a5 + 2) - 16) )
        {
          result = WriteWord(v55, (unsigned __int16)v19, v38);
          if ( result )
            return result;
          v39 = *((_QWORD *)a5 + 2);
          v38 += 2;
          v40 = 32LL * v37;
          v41 = *(_DWORD *)(v40 + v39 + 12);
          if ( (_WORD)v54 )
          {
            LODWORD(Sizeb) = *(_DWORD *)(v40 + v39 + 12);
            result = CopyBlockOver(v60[0], *(_QWORD *)(v40 + v39), v19 + v67, *(_DWORD *)(v40 + v39 + 8), Sizeb);
            if ( result )
              return result;
          }
          LOWORD(v9) = v9 + 1;
          v19 += v41;
        }
        ++v37;
      }
      result = WriteWord(v55, (unsigned __int16)v19, v38);
      if ( result )
        return result;
      v22 = v38 + 2;
      v52 = v22;
      v42 = *v62 + v9 - 1;
      goto LABEL_69;
  }
  if ( v18 != 4 )
  {
    if ( v18 != 5 )
      return 0;
    v20 = *((_QWORD *)a5 + 3);
    v21 = *((_DWORD *)a5 + 1);
    v69 = 0;
    v65 = v18;
    v66 = v16;
    v67 = v10;
    *(_DWORD *)v68 = v21;
    *(_QWORD *)&v68[4] = v20;
    v22 = v53 + (unsigned __int16)GetGenericSize(INDEXSUBTABLE5_CONTROL);
    v52 = v22;
    for ( i = 0; i < *(_WORD *)(v17 + 8); ++i )
    {
      if ( !i || *(_WORD *)(32LL * i + *((_QWORD *)a5 + 2) + 16) != *(_WORD *)(32LL * i + *((_QWORD *)a5 + 2) - 16) )
      {
        v24 = 32LL * i;
        result = WriteWord(v55, *(unsigned __int16 *)(*((_QWORD *)a5 + 2) + v24 + 16), v22);
        if ( result )
          return result;
        v22 += 2;
        v52 = v22;
        if ( (_WORD)v54 )
        {
          LODWORD(Size) = v21;
          result = CopyBlockOver(
                     v60[0],
                     *(_QWORD *)(v24 + *((_QWORD *)a5 + 2)),
                     v19 + v56,
                     *(_DWORD *)(v24 + *((_QWORD *)a5 + 2) + 8),
                     Size);
          if ( result )
            return result;
        }
        ++v9;
        v19 += v21;
        v26 = *(_WORD *)(v24 + *((_QWORD *)a5 + 2) + 16);
        v17 = (__int64)a5;
        if ( v26 <= *v61 )
          v26 = *v61;
        *v61 = v26;
      }
    }
    v27 = v53;
    LODWORD(v69) = v9;
    result = WriteGeneric(v55, (__int64)&v65, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, v53, v51);
    if ( result )
      return result;
    goto LABEL_71;
  }
  v65 = v18;
  *(_QWORD *)v68 = 0;
  v52 = 0;
  v66 = v16;
  v67 = v10;
  v28 = v53 + (unsigned __int16)GetGenericSize(&INDEXSUBTABLE4_CONTROL);
  for ( j = 0; j < *(_WORD *)(v17 + 8); ++j )
  {
    if ( !j || *(_WORD *)(32LL * j + *((_QWORD *)a5 + 2) + 16) != *(_WORD *)(32LL * j + *((_QWORD *)a5 + 2) - 16) )
    {
      v30 = *((_QWORD *)a5 + 2);
      v31 = 32LL * j;
      HIWORD(v52) = v19;
      LOWORD(v52) = *(_WORD *)(v30 + v31 + 16);
      result = WriteGeneric(v55, (__int64)&v52, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v28, v51);
      if ( result )
        return result;
      v32 = *((_QWORD *)a5 + 2);
      v28 += v51[0];
      v33 = *(_DWORD *)(v31 + v32 + 12);
      if ( (_WORD)v54 )
      {
        LODWORD(Sizea) = *(_DWORD *)(v31 + v32 + 12);
        result = CopyBlockOver(v60[0], *(_QWORD *)(v31 + v32), v19 + v56, *(_DWORD *)(v31 + v32 + 8), Sizea);
        if ( result )
          return result;
      }
      v19 += v33;
      ++v9;
      v34 = *(_WORD *)(v31 + *((_QWORD *)a5 + 2) + 16);
      v17 = (__int64)a5;
      if ( v34 <= *v61 )
        v34 = *v61;
      *v61 = v34;
    }
  }
  v35 = v55;
  LOWORD(v52) = 0;
  HIWORD(v52) = v19;
  result = WriteGeneric(v55, (__int64)&v52, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v28, v51);
  if ( !result )
  {
    v22 = v51[0] + v28;
    *(_DWORD *)v68 = v9;
    v52 = v22;
    result = WriteGeneric(v35, (__int64)&v65, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, v53, v51);
    if ( !result )
    {
LABEL_70:
      v27 = v53;
LABEL_71:
      result = ZeroLongWordAlign(v55, v22, &v52);
      if ( result )
        return result;
      if ( !v19 )
        return 0;
      if ( (_WORD)v54 )
      {
        HIDWORD(v57) = v19;
        *v63 = v19;
        result = RecordGlyphOffset_0(
                   *(_QWORD *)(*((_QWORD *)a5 + 2) + 24LL),
                   *(unsigned int *)(*((_QWORD *)a5 + 2) + 8LL),
                   &v57);
        if ( result )
          return result;
        goto LABEL_77;
      }
      if ( v19 <= v59 )
LABEL_77:
        *v64 = v52 - v27;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016e9c  push    rbp
0x180016e9e  push    rbx
0x180016e9f  push    rsi
0x180016ea0  push    rdi
0x180016ea1  push    r12
0x180016ea3  push    r13
0x180016ea5  push    r14
0x180016ea7  push    r15
0x180016ea9  lea     rbp, [rsp-7]
0x180016eae  sub     rsp, 0C8h
0x180016eb5  mov     rax, cs:__security_cookie
0x180016ebc  xor     rax, rsp
0x180016ebf  mov     [rbp+3Fh+var_50], rax
0x180016ec3  mov     r14, [rbp+3Fh+arg_20]
0x180016ec7  xor     edi, edi
0x180016ec9  xor     eax, eax
0x180016ecb  mov     [rsp+100h+var_C0], rcx
0x180016ed0  mov     rcx, [rbp+3Fh+arg_28]
0x180016ed4  mov     r15d, r9d
0x180016ed7  mov     [rbp+3Fh+var_B8], r9d
0x180016edb  mov     r9, [rbp+3Fh+arg_30]
0x180016edf  lea     r12d, [rdi+2]
0x180016ee3  mov     [rbp+3Fh+var_B0], rax
0x180016ee7  lea     esi, [rdi+1]
0x180016eea  mov     [rcx], edi
0x180016eec  lea     ebx, [rdi+5]
0x180016eef  mov     [rbp+3Fh+var_A8], eax
0x180016ef2  mov     [r9], edi
0x180016ef5  mov     rax, [r14+10h]
0x180016ef9  mov     [rsp+100h+var_C8], edx
0x180016efd  mov     rdx, [rbp+3Fh+arg_38]
0x180016f04  mov     qword ptr [rbp+3Fh+var_98], r8
0x180016f08  mov     r8, [rbp+3Fh+arg_40]
0x180016f0f  mov     [rbp+3Fh+var_78], rcx
0x180016f13  movzx   ecx, word ptr [rax+10h]
0x180016f17  mov     [rdx], cx
0x180016f1a  mov     [r8], di
0x180016f1e  movzx   r11d, word ptr [r14]
0x180016f22  mov     [rbp+3Fh+var_80], r9
0x180016f26  mov     [rbp+3Fh+var_88], rdx
0x180016f2a  mov     [rbp+3Fh+var_90], r8
0x180016f2e  mov     [rsp+100h+var_D0], di
0x180016f33  cmp     r11w, r12w
0x180016f37  jz      short loc_180016F3F
0x180016f39  cmp     r11w, bx
0x180016f3d  jnz     short loc_180016F9C
0x180016f3f  cmp     si, [r14+8]
0x180016f44  jnb     short loc_180016F94
0x180016f46  mov     r10, [r14+10h]
0x180016f4a  movzx   r8d, si
0x180016f4e  movzx   r9d, si
0x180016f52  movzx   ecx, r9w
0x180016f56  mov     eax, ecx
0x180016f58  shl     rcx, 5
0x180016f5c  shl     rax, 5
0x180016f60  movzx   edx, word ptr [rax+r10-10h]
0x180016f66  movzx   eax, word ptr [rcx+r10+10h]
0x180016f6c  add     edx, esi
0x180016f6e  cmp     eax, edx
0x180016f70  mov     ecx, edi
0x180016f72  cmovbe  cx, r8w
0x180016f77  add     r9w, si
0x180016f7b  movzx   r8d, cx
0x180016f7f  cmp     r9w, [r14+8]
0x180016f84  jb      short loc_180016F52
0x180016f86  test    cx, cx
0x180016f89  jnz     short loc_180016F94
0x180016f8b  mov     [r14], bx
0x180016f8f  mov     r11d, ebx
0x180016f92  jmp     short loc_180016F9C
0x180016f94  mov     [r14], r12w
0x180016f98  movzx   r11d, r12w
0x180016f9c  mov     rcx, [r14+10h]
0x180016fa0  lea     r8, [rbp+3Fh+var_B0]
0x180016fa4  movzx   ebx, word ptr [r14+2]
0x180016fa9  mov     r12, r14
0x180016fac  mov     r13d, 8
0x180016fb2  mov     edx, [rcx+8]
0x180016fb5  mov     rcx, [rcx+18h]
0x180016fb9  call    LookupGlyphOffset
0x180016fbe  test    eax, eax
0x180016fc0  jnz     short loc_180016FD9
0x180016fc2  mov     word ptr [rsp+100h+var_C4], si
0x180016fc7  mov     dword ptr [rbp+3Fh+var_B0], r15d
0x180016fcb  mov     [rbp+3Fh+var_A0], edi
0x180016fce  mov     word ptr [rbp+3Fh+var_A8+2], r11w
0x180016fd3  mov     word ptr [rbp+3Fh+var_A8], bx
0x180016fd7  jmp     short loc_180016FF5
0x180016fd9  cmp     word ptr [rbp+3Fh+var_A8], bx
0x180016fdd  jnz     loc_1800175C5
0x180016fe3  mov     r15d, dword ptr [rbp+3Fh+var_B0]
0x180016fe7  mov     eax, dword ptr [rbp+3Fh+var_B0+4]
0x180016fea  mov     [rbp+3Fh+var_B8], r15d
0x180016fee  mov     [rbp+3Fh+var_A0], eax
0x180016ff1  mov     [rsp+100h+var_C4], edi
0x180016ff5  movzx   ecx, r11w
0x180016ff9  mov     esi, edi
0x180016ffb  sub     ecx, 1
0x180016ffe  jz      loc_1800175E7
0x180017004  sub     ecx, 1
0x180017007  jz      loc_18001745F
0x18001700d  sub     ecx, 1
0x180017010  jz      loc_180017323
0x180017016  sub     ecx, 1
0x180017019  jz      loc_180017173
0x18001701f  cmp     ecx, 1
0x180017022  jnz     loc_1800175C5
0x180017028  mov     rax, [r14+18h]
0x18001702c  xor     ecx, ecx
0x18001702e  mov     r13d, [r14+4]
0x180017032  mov     [rbp+3Fh+var_5C], rcx
0x180017036  lea     rcx, INDEXSUBTABLE5_CONTROL
0x18001703d  mov     [rbp+3Fh+var_70], r11w
0x180017042  mov     [rbp+3Fh+var_6E], bx
0x180017046  mov     [rbp+3Fh+var_6C], r15d
0x18001704a  mov     dword ptr [rbp+3Fh+var_68], r13d
0x18001704e  mov     qword ptr [rbp+3Fh+var_68+4], rax
0x180017052  call    GetGenericSize
0x180017057  movzx   ebx, ax
0x18001705a  add     ebx, [rsp+100h+var_C8]
0x18001705e  xor     r8d, r8d
0x180017061  mov     [rsp+100h+var_CC], ebx
0x180017065  mov     r15d, r8d
0x180017068  mov     eax, 8
0x18001706d  cmp     r15w, [r12+rax]
0x180017072  jnb     loc_180017131
0x180017078  test    r15w, r15w
0x18001707c  jz      short loc_1800170A0
0x18001707e  mov     rcx, [r14+10h]
0x180017082  movzx   edx, r15w
0x180017086  mov     eax, edx
0x180017088  shl     rdx, 5
0x18001708c  shl     rax, 5
0x180017090  movzx   eax, word ptr [rax+rcx-10h]
0x180017095  cmp     [rdx+rcx+10h], ax
0x18001709a  jz      loc_180017128
0x1800170a0  mov     rdx, [r14+10h]
0x1800170a4  mov     r8d, ebx
0x1800170a7  mov     rcx, [rsp+100h+var_C0]
0x1800170ac  movzx   r12d, r15w
0x1800170b0  shl     r12, 5
0x1800170b4  movzx   edx, word ptr [rdx+r12+10h]
0x1800170ba  call    WriteWord
0x1800170bf  xor     r8d, r8d
0x1800170c2  test    ax, ax
0x1800170c5  jnz     loc_1800175C7
0x1800170cb  add     ebx, 2
0x1800170ce  mov     [rsp+100h+var_CC], ebx
0x1800170d2  cmp     word ptr [rsp+100h+var_C4], r8w
0x1800170d8  jz      short loc_180017108
0x1800170da  mov     rdx, [r14+10h]
0x1800170de  mov     r8d, [rbp+3Fh+var_B8]
0x1800170e2  mov     rcx, qword ptr [rbp+3Fh+var_98]; int
0x1800170e6  add     r8d, esi; int
0x1800170e9  mov     dword ptr [rsp+100h+Size], r13d; Size
0x1800170ee  mov     r9d, [r12+rdx+8]; int
0x1800170f3  mov     rdx, [r12+rdx]; int
0x1800170f7  call    CopyBlockOver
0x1800170fc  xor     r8d, r8d
0x1800170ff  test    ax, ax
0x180017102  jnz     loc_1800175C7
0x180017108  mov     rax, [r14+10h]
0x18001710c  inc     edi
0x18001710e  add     esi, r13d
0x180017111  movzx   ecx, word ptr [r12+rax+10h]
0x180017117  mov     r12, r14
0x18001711a  mov     rax, [rbp+3Fh+var_90]
0x18001711e  cmp     cx, [rax]
0x180017121  cmovbe  cx, [rax]
0x180017125  mov     [rax], cx
0x180017128  inc     r15w
0x18001712c  jmp     loc_180017068
0x180017131  mov     r15d, [rsp+100h+var_C8]
0x180017136  lea     rax, [rsp+100h+var_D0]
0x18001713b  mov     rcx, [rsp+100h+var_C0]
0x180017140  lea     r9, INDEXSUBTABLE5_CONTROL
0x180017147  mov     [rsp+100h+var_D8], rax
0x18001714c  lea     rdx, [rbp+3Fh+var_70]
0x180017150  mov     r8d, 18h
0x180017156  mov     dword ptr [rsp+100h+Size], r15d
0x18001715b  mov     dword ptr [rbp+3Fh+var_5C], edi
0x18001715e  call    WriteGeneric
0x180017163  xor     edi, edi
0x180017165  test    ax, ax
0x180017168  jz      loc_18001756E
0x18001716e  jmp     loc_1800175C7
0x180017173  xor     ecx, ecx
0x180017175  mov     [rbp+3Fh+var_70], r11w
0x18001717a  mov     qword ptr [rbp+3Fh+var_68], rcx
0x18001717e  mov     [rsp+100h+var_CC], ecx
0x180017182  lea     rcx, INDEXSUBTABLE4_CONTROL
0x180017189  mov     [rbp+3Fh+var_6E], bx
0x18001718d  mov     [rbp+3Fh+var_6C], r15d
0x180017191  call    GetGenericSize
0x180017196  movzx   ebx, ax
0x180017199  add     ebx, [rsp+100h+var_C8]
0x18001719d  xor     r8d, r8d
0x1800171a0  mov     r15d, r8d
0x1800171a3  cmp     r15w, [r12+r13]
0x1800171a8  jnb     loc_180017299
0x1800171ae  test    r15w, r15w
0x1800171b2  jz      short loc_1800171D6
0x1800171b4  mov     rcx, [r14+10h]
0x1800171b8  movzx   edx, r15w
0x1800171bc  mov     eax, edx
0x1800171be  shl     rdx, 5
0x1800171c2  shl     rax, 5
0x1800171c6  movzx   eax, word ptr [rax+rcx-10h]
0x1800171cb  cmp     [rdx+rcx+10h], ax
0x1800171d0  jz      loc_180017290
0x1800171d6  mov     rax, [r14+10h]
0x1800171da  lea     r9, CODEOFFSETPAIR_CONTROL
0x1800171e1  movzx   r12d, r15w
0x1800171e5  lea     rdx, [rsp+100h+var_CC]
0x1800171ea  shl     r12, 5
0x1800171ee  mov     r8d, 4
0x1800171f4  mov     word ptr [rsp+100h+var_CC+2], si
0x1800171f9  movzx   ecx, word ptr [rax+r12+10h]
0x1800171ff  lea     rax, [rsp+100h+var_D0]
0x180017204  mov     word ptr [rsp+100h+var_CC], cx
0x180017209  mov     rcx, [rsp+100h+var_C0]
0x18001720e  mov     [rsp+100h+var_D8], rax
0x180017213  mov     dword ptr [rsp+100h+Size], ebx
0x180017217  call    WriteGeneric
0x18001721c  xor     r8d, r8d
0x18001721f  test    ax, ax
0x180017222  jnz     loc_1800175C7
0x180017228  movzx   eax, [rsp+100h+var_D0]
0x18001722d  mov     rdx, [r14+10h]
0x180017231  add     ebx, eax
0x180017233  mov     r13d, [r12+rdx+0Ch]
0x180017238  cmp     word ptr [rsp+100h+var_C4], r8w
0x18001723e  jz      short loc_18001726A
0x180017240  mov     r8d, [rbp+3Fh+var_B8]
0x180017244  mov     r9d, [r12+rdx+8]; int
0x180017249  add     r8d, esi; int
0x18001724c  mov     rdx, [r12+rdx]; int
0x180017250  mov     rcx, qword ptr [rbp+3Fh+var_98]; int
0x180017254  mov     dword ptr [rsp+100h+Size], r13d; Size
0x180017259  call    CopyBlockOver
0x18001725e  xor     r8d, r8d
0x180017261  test    ax, ax
0x180017264  jnz     loc_1800175C7
0x18001726a  mov     rax, [r14+10h]
0x18001726e  add     esi, r13d
0x180017271  inc     edi
0x180017273  mov     r13d, 8
0x180017279  movzx   ecx, word ptr [r12+rax+10h]
0x18001727f  mov     r12, r14
0x180017282  mov     rax, [rbp+3Fh+var_90]
0x180017286  cmp     cx, [rax]
0x180017289  cmovbe  cx, [rax]
0x18001728d  mov     [rax], cx
0x180017290  inc     r15w
0x180017294  jmp     loc_1800171A3
0x180017299  mov     r15, [rsp+100h+var_C0]
0x18001729e  lea     rax, [rsp+100h+var_D0]
0x1800172a3  mov     word ptr [rsp+100h+var_CC], r8w
0x1800172a9  lea     r9, CODEOFFSETPAIR_CONTROL
0x1800172b0  mov     [rsp+100h+var_D8], rax
0x1800172b5  lea     rdx, [rsp+100h+var_CC]
0x1800172ba  mov     rcx, r15
0x1800172bd  mov     dword ptr [rsp+100h+Size], ebx
0x1800172c1  mov     r8d, 4
0x1800172c7  mov     word ptr [rsp+100h+var_CC+2], si
0x1800172cc  call    WriteGeneric
0x1800172d1  test    ax, ax
0x1800172d4  jnz     loc_1800175C7
0x1800172da  movzx   eax, [rsp+100h+var_D0]
0x1800172df  lea     r9, INDEXSUBTABLE4_CONTROL
0x1800172e6  add     ebx, eax
0x1800172e8  mov     dword ptr [rbp+3Fh+var_68], edi
0x1800172eb  lea     rax, [rsp+100h+var_D0]
0x1800172f0  mov     [rsp+100h+var_CC], ebx
0x1800172f4  mov     [rsp+100h+var_D8], rax
0x1800172f9  lea     rdx, [rbp+3Fh+var_70]
0x1800172fd  mov     eax, [rsp+100h+var_C8]
0x180017301  mov     r8d, 0Ch
0x180017307  mov     rcx, r15
0x18001730a  mov     dword ptr [rsp+100h+Size], eax
0x18001730e  call    WriteGeneric
0x180017313  xor     edi, edi
0x180017315  test    ax, ax
0x180017318  jz      loc_180017569
0x18001731e  jmp     loc_1800175C7
0x180017323  xor     ecx, ecx
0x180017325  mov     [rbp+3Fh+var_6C], r15d
0x180017329  mov     r15d, [rsp+100h+var_C8]
0x18001732e  lea     rax, [rsp+100h+var_D0]
0x180017333  mov     dword ptr [rbp+3Fh+var_68], ecx
0x180017336  lea     r9, INDEXSUBTABLE3_CONTROL
0x18001733d  mov     [rsp+100h+var_D8], rax
0x180017342  lea     rdx, [rbp+3Fh+var_70]
0x180017346  lea     r8d, [rcx+8]
0x18001734a  mov     [rbp+3Fh+var_70], r11w
0x18001734f  mov     rcx, [rsp+100h+var_C0]
0x180017354  mov     [rbp+3Fh+var_6E], bx
0x180017358  mov     dword ptr [rsp+100h+Size], r15d
0x18001735d  call    WriteGeneric
0x180017362  xor     r8d, r8d
  ... truncated ...
```
