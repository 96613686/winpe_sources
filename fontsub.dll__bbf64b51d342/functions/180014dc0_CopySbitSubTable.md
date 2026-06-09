# CopySbitSubTable

- ea: `0x180014dc0`
- end: `0x180015443`
- name: `CopySbitSubTable`
- size: `1667`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800154a4`

## callees

- `0x180014dc0`
- `0x18001544c`
- `0x180016dd8`
- `0x18001986c`
- `0x18001a060`
- `0x18001a3bc`
- `0x18001a680`
- `0x18001a808`
- `0x18001aadc`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall CopySbitSubTable(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 a5,
        __int64 a6,
        int a7,
        int a8,
        __int64 a9,
        _DWORD *a10,
        unsigned int *a11)
{
  __int64 v11; // r15
  __int16 result; // ax
  unsigned int v16; // r12d
  unsigned int v17; // r11d
  int v18; // ebx
  unsigned int v19; // r13d
  int v20; // r15d
  int v21; // ebx
  int v22; // r12d
  unsigned int v23; // edi
  unsigned int v24; // ebx
  __int64 v25; // rcx
  unsigned __int16 v26; // r13
  unsigned int v27; // r15d
  unsigned int v28; // r12d
  unsigned __int16 v29; // r15
  unsigned __int16 v30; // r12
  __int64 v31; // r8
  int v32; // r10d
  unsigned __int16 v33; // ax
  unsigned int v34; // r13d
  int v35; // r10d
  unsigned __int16 v36; // r15
  size_t Size; // [rsp+20h] [rbp-A1h]
  size_t Sizea; // [rsp+20h] [rbp-A1h]
  size_t Sizeb; // [rsp+20h] [rbp-A1h]
  size_t Sizec; // [rsp+20h] [rbp-A1h]
  size_t Sized; // [rsp+20h] [rbp-A1h]
  _WORD v42[2]; // [rsp+30h] [rbp-91h] BYREF
  _WORD v43[2]; // [rsp+34h] [rbp-8Dh] BYREF
  unsigned __int16 v44[2]; // [rsp+38h] [rbp-89h] BYREF
  unsigned int v45; // [rsp+3Ch] [rbp-85h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v47; // [rsp+44h] [rbp-7Dh]
  __int64 v48; // [rsp+48h] [rbp-79h] BYREF
  __int64 v49; // [rsp+50h] [rbp-71h] BYREF
  int v50; // [rsp+58h] [rbp-69h]
  int v51[2]; // [rsp+60h] [rbp-61h]
  unsigned int v52; // [rsp+68h] [rbp-59h]
  int v53[2]; // [rsp+70h] [rbp-51h]
  _DWORD *v54; // [rsp+78h] [rbp-49h]
  unsigned int *v55; // [rsp+80h] [rbp-41h]
  __int64 v56; // [rsp+88h] [rbp-39h]
  int v57[8]; // [rsp+90h] [rbp-31h] BYREF

  v11 = a1;
  *(_QWORD *)v53 = a6;
  *(_QWORD *)v51 = a1;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  v42[0] = 0;
  v43[0] = 0;
  v56 = a9;
  v54 = a10;
  v55 = a11;
  result = ReadGeneric(a2, (__int64)&v48, 8u, (unsigned __int8 *)INDEXSUBHEADER_CONTROL, a4, v42);
  if ( result )
    return result;
  *a10 = 0;
  *a11 = 0;
  v16 = HIDWORD(v48);
  if ( (unsigned int)LookupGlyphOffset(a9, HIDWORD(v48), &v49) )
  {
    if ( (_WORD)v50 != WORD1(v48) )
      return v17;
    v19 = v17;
    v18 = v49;
    v52 = HIDWORD(v49);
  }
  else
  {
    v18 = a7;
    v19 = v17 + 1;
    LODWORD(v49) = a7;
    v52 = v17;
    LOWORD(v50) = WORD1(v48);
    HIWORD(v50) = v48;
  }
  v47 = v19;
  switch ( (unsigned __int16)v48 )
  {
    case 1u:
      return 1006;
    case 2u:
      memset(v57, 0, 20);
      result = ReadGeneric(a2, (__int64)v57, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, a4, v42);
      if ( result )
        return result;
      v57[1] = v18;
      result = WriteGeneric(v11, (__int64)v57, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, a3, v43);
      if ( result )
        return result;
      v23 = a3 + v43[0];
      v24 = v57[2] * a5;
      v46 = v23;
      if ( v19 )
      {
        LODWORD(Sized) = v57[2] * a5;
        result = CopyBlockOver(v53[0], a2, v57[1], v16 + a8, Sized);
        if ( result )
          return result;
      }
LABEL_17:
      result = ZeroLongWordAlign(v11, v23, &v46);
      LOWORD(v17) = 0;
      if ( result )
        return result;
      if ( v24 )
      {
        *v54 = v46 - a3;
        if ( !v19 )
          return v52 < v24 ? 0x3E8 : 0;
        v25 = v56;
        HIDWORD(v49) = v24;
        *v55 = v24;
        return RecordGlyphOffset_0(v25, v16, &v49);
      }
      return v17;
    case 3u:
      LOWORD(v45) = v17;
      *(_QWORD *)v57 = 0;
      v57[2] = 0;
      v44[0] = v17;
      result = ReadGeneric(a2, (__int64)v57, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, a4, v42);
      v30 = 0;
      if ( result )
        return result;
      v57[1] = v18;
      result = WriteGeneric(v11, (__int64)v57, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, a3, v43);
      if ( result )
        return result;
      v31 = a4 + v42[0];
      v23 = a3 + v43[0];
      v46 = v23;
      result = ReadWord(a2, &v45, v31);
      if ( result )
        return result;
      v33 = v45;
      v34 = v32 + 2;
      LOWORD(v24) = 0;
      while ( 1 )
      {
        LOWORD(v45) = v33;
        if ( v30 > a5 )
          break;
        result = WriteWord(v11, (unsigned __int16)v24, v23);
        if ( result )
          return result;
        v23 += 2;
        v46 = v23;
        if ( v30 == a5 )
          break;
        result = ReadWord(a2, v44, v34);
        if ( result )
          return result;
        v36 = v44[0] - v45;
        if ( v47 != v35 )
        {
          LODWORD(Sizec) = v36;
          result = CopyBlockOver(
                     v53[0],
                     a2,
                     v57[1] + (unsigned int)(unsigned __int16)v24,
                     a8 + HIDWORD(v48) + (unsigned int)(unsigned __int16)v45,
                     Sizec);
          if ( result )
            return result;
        }
        v33 = v44[0];
        LOWORD(v24) = v36 + v24;
        v11 = *(_QWORD *)v51;
        v34 += 2;
        ++v30;
      }
      goto LABEL_43;
    case 4u:
      v45 = v17;
      *(_OWORD *)v57 = 0;
      result = ReadGeneric(a2, (__int64)v57, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, a4, v42);
      v26 = 0;
      if ( result )
        return result;
      v57[1] = v18;
      result = WriteGeneric(v11, (__int64)v57, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, a3, v43);
      if ( result )
        return result;
      v27 = v42[0] + a4;
      v23 = v42[0] + a3;
      v46 = v23;
      result = ReadGeneric(a2, (__int64)&v45, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v27, v42);
      if ( result )
        return result;
      LOWORD(v24) = 0;
      v28 = v27 + v42[0];
      while ( 1 )
      {
        v11 = *(_QWORD *)v51;
        v44[0] = HIWORD(v45);
        if ( v26 > LOWORD(v57[2]) )
          break;
        HIWORD(v45) = v24;
        result = WriteGeneric(*(__int64 *)v51, (__int64)&v45, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v23, v43);
        if ( result )
          return result;
        v23 += v43[0];
        v46 = v23;
        if ( v26 == LOWORD(v57[2]) )
          break;
        result = ReadGeneric(a2, (__int64)&v45, 4u, (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL, v28, v42);
        if ( result )
          return result;
        v29 = HIWORD(v45) - v44[0];
        if ( v47 )
        {
          LODWORD(Sizeb) = v29;
          result = CopyBlockOver(
                     v53[0],
                     a2,
                     v57[1] + (unsigned int)(unsigned __int16)v24,
                     a8 + HIDWORD(v48) + (unsigned int)v44[0],
                     Sizeb);
          if ( result )
            return result;
        }
        LOWORD(v24) = v29 + v24;
        v28 += v42[0];
        ++v26;
      }
LABEL_43:
      v19 = v47;
      v16 = HIDWORD(v48);
      v24 = (unsigned __int16)v24;
      goto LABEL_17;
  }
  if ( (unsigned __int16)v48 != 5 )
    return v17;
  memset(v57, 0, 28);
  result = ReadGeneric(a2, (__int64)v57, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, a4, v42);
  if ( !result )
  {
    v57[1] = v18;
    result = WriteGeneric(v11, (__int64)v57, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, a3, v43);
    if ( !result )
    {
      v20 = v57[5];
      v21 = a3 + v43[0];
      v22 = 2 * v57[5];
      LODWORD(Size) = 2 * v57[5];
      result = CopyBlockOver(v51[0], a2, v21, a4 + v42[0], Size);
      if ( !result )
      {
        v23 = v21 + v22;
        v16 = HIDWORD(v48);
        v24 = v20 * v57[2];
        v46 = v23;
        if ( !v19
          || (LODWORD(Sizea) = v20 * v57[2], (result = CopyBlockOver(v53[0], a2, v57[1], HIDWORD(v48) + a8, Sizea)) == 0) )
        {
          v11 = *(_QWORD *)v51;
          goto LABEL_17;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014dc0  push    rbp
0x180014dc2  push    rbx
0x180014dc3  push    rsi
0x180014dc4  push    rdi
0x180014dc5  push    r12
0x180014dc7  push    r13
0x180014dc9  push    r14
0x180014dcb  push    r15
0x180014dcd  lea     rbp, [rsp-7]
0x180014dd2  sub     rsp, 0C8h
0x180014dd9  mov     rax, cs:__security_cookie
0x180014de0  xor     rax, rsp
0x180014de3  mov     [rbp+3Fh+var_50], rax
0x180014de7  mov     rax, [rbp+3Fh+arg_28]
0x180014deb  mov     r15, rcx
0x180014dee  mov     r13, [rbp+3Fh+arg_40]
0x180014df5  mov     rsi, rdx
0x180014df8  mov     rbx, [rbp+3Fh+arg_48]
0x180014dff  lea     rdx, [rbp+3Fh+var_B8]
0x180014e03  mov     r12, [rbp+3Fh+arg_50]
0x180014e0a  mov     r14d, r8d
0x180014e0d  mov     qword ptr [rbp+3Fh+var_90], rax
0x180014e11  mov     edi, r9d
0x180014e14  xor     eax, eax
0x180014e16  mov     qword ptr [rbp+3Fh+var_A0], rcx
0x180014e1a  xor     ecx, ecx
0x180014e1c  mov     [rbp+3Fh+var_B0], rax
0x180014e20  mov     [rbp+3Fh+var_A8], eax
0x180014e23  lea     rax, [rsp+100h+var_D0]
0x180014e28  mov     [rsp+100h+var_D8], rax
0x180014e2d  mov     dword ptr [rsp+100h+Size], r9d
0x180014e32  lea     r9, INDEXSUBHEADER_CONTROL
0x180014e39  mov     [rbp+3Fh+var_B8], rcx
0x180014e3d  lea     r8d, [rcx+8]
0x180014e41  mov     [rsp+100h+var_D0], cx
0x180014e46  mov     [rsp+100h+var_CC], cx
0x180014e4b  mov     rcx, rsi
0x180014e4e  mov     [rbp+3Fh+var_78], r13
0x180014e52  mov     [rbp+3Fh+var_88], rbx
0x180014e56  mov     [rbp+3Fh+var_80], r12
0x180014e5a  call    ReadGeneric
0x180014e5f  xor     r11d, r11d
0x180014e62  test    ax, ax
0x180014e65  jnz     loc_180015423
0x180014e6b  mov     [rbx], r11d
0x180014e6e  lea     r8, [rbp+3Fh+var_B0]
0x180014e72  mov     [r12], r11d
0x180014e76  mov     rcx, r13
0x180014e79  mov     r12d, dword ptr [rbp+3Fh+var_B8+4]
0x180014e7d  mov     edx, r12d
0x180014e80  call    LookupGlyphOffset
0x180014e85  mov     rcx, [rbp+3Fh+var_B8]
0x180014e89  test    eax, eax
0x180014e8b  movzx   eax, word ptr [rbp+3Fh+var_B8+2]
0x180014e8f  jnz     short loc_180014EA9
0x180014e91  mov     ebx, [rbp+3Fh+arg_30]
0x180014e94  lea     r13d, [r11+1]
0x180014e98  mov     dword ptr [rbp+3Fh+var_B0], ebx
0x180014e9b  mov     [rbp+3Fh+var_98], r11d
0x180014e9f  mov     word ptr [rbp+3Fh+var_A8+2], cx
0x180014ea3  mov     word ptr [rbp+3Fh+var_A8], ax
0x180014ea7  jmp     short loc_180014EBF
0x180014ea9  cmp     word ptr [rbp+3Fh+var_A8], ax
0x180014ead  jnz     loc_180015420
0x180014eb3  mov     eax, dword ptr [rbp+3Fh+var_B0+4]
0x180014eb6  mov     r13d, r11d
0x180014eb9  mov     ebx, dword ptr [rbp+3Fh+var_B0]
0x180014ebc  mov     [rbp+3Fh+var_98], eax
0x180014ebf  movzx   edx, cx
0x180014ec2  mov     [rbp+3Fh+var_BC], r13d
0x180014ec6  sub     edx, 1
0x180014ec9  jz      loc_180015419
0x180014ecf  sub     edx, 1
0x180014ed2  jz      loc_18001535D
0x180014ed8  sub     edx, 1
0x180014edb  jz      loc_1800151E6
0x180014ee1  sub     edx, 1
0x180014ee4  jz      loc_180015030
0x180014eea  cmp     edx, 1
0x180014eed  jnz     loc_180015420
0x180014ef3  xorps   xmm0, xmm0
0x180014ef6  lea     rax, [rsp+100h+var_D0]
0x180014efb  lea     r8d, [rdx+17h]
0x180014eff  mov     [rsp+100h+var_D8], rax
0x180014f04  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180014f08  lea     r9, INDEXSUBTABLE5_CONTROL
0x180014f0f  mov     dword ptr [rsp+100h+Size], edi
0x180014f13  lea     rdx, [rbp+3Fh+var_70]
0x180014f17  mov     rcx, rsi
0x180014f1a  movups  xmmword ptr [rbp+3Fh+var_70+0Ch], xmm0
0x180014f1e  call    ReadGeneric
0x180014f23  test    ax, ax
0x180014f26  jnz     loc_180015423
0x180014f2c  lea     rax, [rsp+100h+var_CC]
0x180014f31  mov     [rbp+3Fh+var_70+4], ebx
0x180014f34  mov     [rsp+100h+var_D8], rax
0x180014f39  lea     r9, INDEXSUBTABLE5_CONTROL
0x180014f40  mov     r8d, 18h
0x180014f46  mov     dword ptr [rsp+100h+Size], r14d
0x180014f4b  lea     rdx, [rbp+3Fh+var_70]
0x180014f4f  mov     rcx, r15
0x180014f52  call    WriteGeneric
0x180014f57  test    ax, ax
0x180014f5a  jnz     loc_180015423
0x180014f60  movzx   r9d, [rsp+100h+var_D0]
0x180014f66  mov     rdx, rsi; int
0x180014f69  mov     r15d, [rbp+3Fh+var_5C]
0x180014f6d  add     r9d, edi; int
0x180014f70  movzx   ebx, [rsp+100h+var_CC]
0x180014f75  mov     rcx, qword ptr [rbp+3Fh+var_A0]; int
0x180014f79  add     ebx, r14d
0x180014f7c  mov     r8d, ebx; int
0x180014f7f  lea     r12d, [r15+r15]
0x180014f83  mov     dword ptr [rsp+100h+Size], r12d; Size
0x180014f88  call    CopyBlockOver
0x180014f8d  test    ax, ax
0x180014f90  jnz     loc_180015423
0x180014f96  lea     edi, [rbx+r12]
0x180014f9a  mov     ebx, [rbp+3Fh+var_70+8]
0x180014f9d  mov     r12d, dword ptr [rbp+3Fh+var_B8+4]
0x180014fa1  imul    ebx, r15d
0x180014fa5  mov     [rsp+100h+var_C0], edi
0x180014fa9  test    r13d, r13d
0x180014fac  jz      short loc_180014FD5
0x180014fae  mov     r9d, [rbp+3Fh+arg_38]
0x180014fb5  mov     rdx, rsi; int
0x180014fb8  mov     r8d, [rbp+3Fh+var_70+4]; int
0x180014fbc  add     r9d, r12d; int
0x180014fbf  mov     rcx, qword ptr [rbp+3Fh+var_90]; int
0x180014fc3  mov     dword ptr [rsp+100h+Size], ebx; Size
0x180014fc7  call    CopyBlockOver
0x180014fcc  test    ax, ax
0x180014fcf  jnz     loc_180015423
0x180014fd5  mov     r15, qword ptr [rbp+3Fh+var_A0]
0x180014fd9  lea     r8, [rsp+100h+var_C0]
0x180014fde  mov     edx, edi
0x180014fe0  mov     rcx, r15
0x180014fe3  call    ZeroLongWordAlign
0x180014fe8  xor     r11d, r11d
0x180014feb  test    ax, ax
0x180014fee  jnz     loc_180015423
0x180014ff4  test    ebx, ebx
0x180014ff6  jz      loc_180015420
0x180014ffc  mov     eax, [rsp+100h+var_C0]
0x180015000  mov     rdx, [rbp+3Fh+var_88]
0x180015004  sub     eax, r14d
0x180015007  mov     [rdx], eax
0x180015009  test    r13d, r13d
0x18001500c  jz      loc_18001540D
0x180015012  mov     rax, [rbp+3Fh+var_80]
0x180015016  lea     r8, [rbp+3Fh+var_B0]
0x18001501a  mov     rcx, [rbp+3Fh+var_78]
0x18001501e  mov     edx, r12d
0x180015021  mov     dword ptr [rbp+3Fh+var_B0+4], ebx
0x180015024  mov     [rax], ebx
0x180015026  call    RecordGlyphOffset_0
0x18001502b  jmp     loc_180015423
0x180015030  lea     rax, [rsp+100h+var_D0]
0x180015035  mov     [rsp+100h+var_C4], r11d
0x18001503a  xorps   xmm0, xmm0
0x18001503d  mov     [rsp+100h+var_D8], rax
0x180015042  mov     r12d, 0Ch
0x180015048  mov     dword ptr [rsp+100h+Size], edi
0x18001504c  mov     r8d, r12d
0x18001504f  lea     r9, INDEXSUBTABLE4_CONTROL
0x180015056  lea     rdx, [rbp+3Fh+var_70]
0x18001505a  mov     rcx, rsi
0x18001505d  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x180015061  call    ReadGeneric
0x180015066  xor     r13d, r13d
0x180015069  test    ax, ax
0x18001506c  jnz     loc_180015423
0x180015072  lea     rax, [rsp+100h+var_CC]
0x180015077  mov     [rbp+3Fh+var_70+4], ebx
0x18001507a  mov     [rsp+100h+var_D8], rax
0x18001507f  lea     r9, INDEXSUBTABLE4_CONTROL
0x180015086  mov     r8d, r12d
0x180015089  mov     dword ptr [rsp+100h+Size], r14d
0x18001508e  lea     rdx, [rbp+3Fh+var_70]
0x180015092  mov     rcx, r15
0x180015095  call    WriteGeneric
0x18001509a  test    ax, ax
0x18001509d  jnz     loc_180015423
0x1800150a3  movzx   eax, [rsp+100h+var_D0]
0x1800150a8  lea     r8d, [r12-8]
0x1800150ad  lea     r9, CODEOFFSETPAIR_CONTROL
0x1800150b4  mov     rcx, rsi
0x1800150b7  lea     rdx, [rsp+100h+var_C4]
0x1800150bc  lea     r15d, [rax+rdi]
0x1800150c0  lea     edi, [rax+r14]
0x1800150c4  lea     rax, [rsp+100h+var_D0]
0x1800150c9  mov     [rsp+100h+var_C0], edi
0x1800150cd  mov     [rsp+100h+var_D8], rax
0x1800150d2  mov     dword ptr [rsp+100h+Size], r15d
0x1800150d7  call    ReadGeneric
0x1800150dc  test    ax, ax
0x1800150df  jnz     loc_180015423
0x1800150e5  movzx   r12d, [rsp+100h+var_D0]
0x1800150eb  mov     ebx, r13d
0x1800150ee  add     r12d, r15d
0x1800150f1  movzx   eax, word ptr [rsp+100h+var_C4+2]
0x1800150f6  mov     r15, qword ptr [rbp+3Fh+var_A0]
0x1800150fa  mov     [rsp+100h+var_C8], ax
0x1800150ff  cmp     r13w, word ptr [rbp+3Fh+var_70+8]
0x180015104  ja      loc_18001534D
0x18001510a  lea     rax, [rsp+100h+var_CC]
0x18001510f  mov     word ptr [rsp+100h+var_C4+2], bx
0x180015114  mov     [rsp+100h+var_D8], rax
0x180015119  lea     r9, CODEOFFSETPAIR_CONTROL
0x180015120  mov     r8d, 4
0x180015126  mov     dword ptr [rsp+100h+Size], edi
0x18001512a  lea     rdx, [rsp+100h+var_C4]
0x18001512f  mov     rcx, r15
0x180015132  call    WriteGeneric
0x180015137  test    ax, ax
0x18001513a  jnz     loc_180015423
0x180015140  movzx   eax, [rsp+100h+var_CC]
0x180015145  add     edi, eax
0x180015147  mov     [rsp+100h+var_C0], edi
0x18001514b  cmp     r13w, word ptr [rbp+3Fh+var_70+8]
0x180015150  jz      loc_18001534D
0x180015156  lea     rax, [rsp+100h+var_D0]
0x18001515b  mov     r8d, 4
0x180015161  mov     [rsp+100h+var_D8], rax
0x180015166  lea     r9, CODEOFFSETPAIR_CONTROL
0x18001516d  lea     rdx, [rsp+100h+var_C4]
0x180015172  mov     dword ptr [rsp+100h+Size], r12d
0x180015177  mov     rcx, rsi
0x18001517a  call    ReadGeneric
0x18001517f  xor     edx, edx
0x180015181  test    ax, ax
0x180015184  jnz     loc_180015423
0x18001518a  movzx   r15d, word ptr [rsp+100h+var_C4+2]
0x180015190  movzx   ecx, [rsp+100h+var_C8]
0x180015195  sub     r15w, cx
0x180015199  cmp     [rbp+3Fh+var_BC], edx
0x18001519c  jz      short loc_1800151D1
0x18001519e  mov     r9d, ecx
0x1800151a1  movzx   r8d, bx
0x1800151a5  add     r9d, dword ptr [rbp+3Fh+var_B8+4]
0x1800151a9  mov     rdx, rsi; int
0x1800151ac  add     r9d, [rbp+3Fh+arg_38]; int
0x1800151b3  add     r8d, [rbp+3Fh+var_70+4]; int
0x1800151b7  mov     rcx, qword ptr [rbp+3Fh+var_90]; int
0x1800151bb  movzx   eax, r15w
0x1800151bf  mov     dword ptr [rsp+100h+Size], eax; Size
0x1800151c3  call    CopyBlockOver
0x1800151c8  test    ax, ax
0x1800151cb  jnz     loc_180015423
0x1800151d1  movzx   eax, [rsp+100h+var_D0]
0x1800151d6  add     bx, r15w
0x1800151da  add     r12d, eax
0x1800151dd  inc     r13w
0x1800151e1  jmp     loc_1800150F1
0x1800151e6  xor     eax, eax
0x1800151e8  mov     word ptr [rsp+100h+var_C4], r11w
0x1800151ee  mov     qword ptr [rbp+3Fh+var_70], rax
0x1800151f2  lea     r9, INDEXSUBTABLE3_CONTROL
0x1800151f9  mov     [rbp+3Fh+var_70+8], eax
0x1800151fc  lea     rdx, [rbp+3Fh+var_70]
0x180015200  mov     rcx, rsi
0x180015203  mov     [rsp+100h+var_C8], r11w
0x180015209  lea     r13d, [rax+8]
0x18001520d  lea     rax, [rsp+100h+var_D0]
0x180015212  mov     r8d, r13d
0x180015215  mov     [rsp+100h+var_D8], rax
0x18001521a  mov     dword ptr [rsp+100h+Size], edi
0x18001521e  call    ReadGeneric
0x180015223  xor     r12d, r12d
0x180015226  test    ax, ax
0x180015229  jnz     loc_180015423
0x18001522f  lea     rax, [rsp+100h+var_CC]
0x180015234  mov     [rbp+3Fh+var_70+4], ebx
0x180015237  mov     [rsp+100h+var_D8], rax
0x18001523c  lea     r9, INDEXSUBTABLE3_CONTROL
0x180015243  mov     r8d, r13d
0x180015246  mov     dword ptr [rsp+100h+Size], r14d
0x18001524b  lea     rdx, [rbp+3Fh+var_70]
0x18001524f  mov     rcx, r15
0x180015252  call    WriteGeneric
0x180015257  test    ax, ax
0x18001525a  jnz     loc_180015423
0x180015260  movzx   r10d, [rsp+100h+var_D0]
0x180015266  lea     rdx, [rsp+100h+var_C4]
0x18001526b  add     r10d, edi
0x18001526e  mov     rcx, rsi
0x180015271  movzx   edi, [rsp+100h+var_CC]
0x180015276  mov     r8d, r10d
0x180015279  add     edi, r14d
0x18001527c  mov     [rsp+100h+var_C0], edi
0x180015280  call    ReadWord
0x180015285  test    ax, ax
0x180015288  jnz     loc_180015423
0x18001528e  movzx   eax, word ptr [rsp+100h+var_C4]
0x180015293  lea     r13d, [r10+2]
0x180015297  mov     ebx, r12d
0x18001529a  mov     word ptr [rsp+100h+var_C4], ax
0x18001529f  cmp     r12w, [rbp+3Fh+arg_20]
0x1800152a4  ja      loc_18001534D
0x1800152aa  mov     r8d, edi
  ... truncated ...
```
