# RtlDosApplyFileIsolationRedirection_Ustr

- ea: `0x18001bcb0`
- end: `0x18001c516`
- name: `RtlDosApplyFileIsolationRedirection_Ustr`
- size: `2150`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001dc60`
- `0x180023e10`
- `0x180077488`
- `0x180079340`

## callees

- `0x18001ae70`
- `0x18001bcb0`
- `0x18001d490`
- `0x180079cf0`
- `0x18007c290`
- `0x18007c700`
- `0x18007d4a8`
- `0x18007e01c`
- `0x18007e170`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x18001c49c`: `minkernel\ntdll\sxsisol.cpp`

## pseudocode

```c
__int64 __fastcall RtlDosApplyFileIsolationRedirection_Ustr(
        int a1,
        __int128 *a2,
        _WORD *a3,
        __int64 a4,
        _OWORD *a5,
        unsigned __int64 a6,
        _DWORD *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  char v9; // di
  char v10; // r13
  int CharInUnicodeString; // eax
  int FullPathName_Ustr; // ebx
  char v14; // al
  unsigned __int64 v15; // rdx
  unsigned int i; // ecx
  unsigned __int64 v17; // rdi
  __int64 v18; // rdi
  __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  __int16 v21; // dx
  __int16 v22; // cx
  bool v23; // cl
  unsigned __int16 v24; // r9
  __int16 v25; // r10
  int v26; // eax
  __int64 v27; // r11
  unsigned __int16 v28; // r8
  int v29; // r15d
  char v30; // dl
  _QWORD *v32; // rdi
  __int16 v33; // dx
  __int16 v34; // dx
  __int16 v35; // cx
  unsigned __int64 v36; // r10
  _WORD *v37; // r9
  unsigned __int16 v38; // [rsp+48h] [rbp-C0h] BYREF
  int v39; // [rsp+4Ch] [rbp-BCh] BYREF
  __int128 v40; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h] BYREF
  void *v42; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v43[3]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v44[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v45; // [rsp+98h] [rbp-70h]
  __int16 v46; // [rsp+A8h] [rbp-60h]
  int v47; // [rsp+AAh] [rbp-5Eh]
  __int16 v48; // [rsp+AEh] [rbp-5Ah]
  void *v49; // [rsp+B0h] [rbp-58h]
  void *Src; // [rsp+B8h] [rbp-50h]
  __int64 v51; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD *v52; // [rsp+C8h] [rbp-40h]
  __int128 v53; // [rsp+D0h] [rbp-38h]
  void *v54; // [rsp+E0h] [rbp-28h] BYREF
  _WORD *v55; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v56; // [rsp+F0h] [rbp-18h]
  __int64 v57; // [rsp+F8h] [rbp-10h]
  __int64 v58; // [rsp+100h] [rbp-8h]
  __int128 v59; // [rsp+108h] [rbp+0h] BYREF
  __int128 v60; // [rsp+118h] [rbp+10h]
  __int128 v61; // [rsp+128h] [rbp+20h]
  __int128 v62; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int128 v63; // [rsp+148h] [rbp+40h]
  __int64 v64; // [rsp+158h] [rbp+50h]
  _WORD v65[16]; // [rsp+168h] [rbp+60h] BYREF
  char v66; // [rsp+188h] [rbp+80h] BYREF

  v9 = 0;
  v10 = a1;
  v44[1] = &v66;
  v52 = a8;
  v42 = a3;
  *(_OWORD *)&v43[1] = 0u;
  v44[0] = 0x800000;
  DWORD1(v53) = 0;
  v58 = 0;
  v64 = 0;
  v51 = 0;
  LOWORD(v41) = 0;
  LODWORD(v43[0]) = 0;
  v40 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 520;
  if ( a5 )
    *a5 = 0;
  v54 = v65;
  v55 = v65;
  v56 = 32;
  *((_QWORD *)&v53 + 1) = v65;
  v57 = 32;
  v65[0] = 0;
  LODWORD(v53) = 0x200000;
  if ( a4 && (v36 = *(unsigned __int16 *)(a4 + 2), v36 >= 2) )
  {
    v37 = *(_WORD **)(a4 + 8);
    *(_QWORD *)&v60 = v37;
    *(_QWORD *)&v61 = v36;
    *((_QWORD *)&v60 + 1) = v37;
    *((_QWORD *)&v61 + 1) = v36;
    *((_QWORD *)&v59 + 1) = v37;
    if ( v37 )
      *v37 = 0;
    LOWORD(v59) = 0;
    WORD1(v59) = v36;
  }
  else
  {
    *(_QWORD *)&v61 = 2;
    *(_QWORD *)&v60 = &v62;
    *((_QWORD *)&v60 + 1) = &v62;
    *((_QWORD *)&v59 + 1) = &v62;
    *((_QWORD *)&v61 + 1) = 2;
    LOWORD(v62) = 0;
    LODWORD(v59) = 0x20000;
  }
  *((_QWORD *)&v62 + 1) = a4;
  v63 = __PAIR128__(a6, (unsigned __int64)a5);
  LOBYTE(v64) = 1;
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    FullPathName_Ustr = -1073741811;
    goto LABEL_58;
  }
  if ( !a2 )
  {
    FullPathName_Ustr = -1073741811;
    goto LABEL_58;
  }
  if ( a4 )
  {
    if ( a5 && !a6 )
    {
      FullPathName_Ustr = -1073741811;
      goto LABEL_58;
    }
  }
  else if ( !a5 && a8 )
  {
    FullPathName_Ustr = -1073741811;
    goto LABEL_58;
  }
  v40 = *a2;
  if ( a3 && *a3 )
  {
    v38 = 0;
    CharInUnicodeString = RtlFindCharInUnicodeString(1, &v40, &qword_180170780, &v38);
    FullPathName_Ustr = CharInUnicodeString;
    if ( CharInUnicodeString >= 0 )
    {
      v14 = 1;
    }
    else
    {
      if ( CharInUnicodeString != -1073741275 )
        goto LABEL_58;
      v14 = 0;
    }
    if ( !v14 )
    {
      v15 = 0;
      v38 = v40;
      Src = (void *)*((_QWORD *)&v40 + 1);
      v45 = v40;
      LOWORD(v39) = *(_WORD *)v42;
      v46 = v39;
      v47 = *(_DWORD *)((char *)v42 + 2);
      v48 = *((_WORD *)v42 + 3);
      v42 = (void *)*((_QWORD *)v42 + 1);
      v49 = v42;
      LOWORD(v53) = 0;
      for ( i = 0; i != 2; ++i )
      {
        v15 += *((unsigned __int16 *)&v45 + 8 * i);
        if ( v15 > 0xFFFE )
          goto LABEL_122;
      }
      v17 = v15 + 2;
      if ( v15 + 2 > 0xFFFE )
      {
LABEL_122:
        FullPathName_Ustr = -1073741562;
        goto LABEL_58;
      }
      if ( v17 <= v56 || (FullPathName_Ustr = RtlpEnsureBufferSize(0, &v54), FullPathName_Ustr >= 0) )
      {
        WORD1(v53) = v17;
        LOWORD(v53) = v17 - 2;
        v18 = v38;
        *((_QWORD *)&v53 + 1) = v54;
        memmove(v54, Src, v38);
        v19 = (unsigned __int16)v39;
        memmove(
          (void *)(*((_QWORD *)&v53 + 1) + 2 * ((unsigned __int64)(unsigned int)v18 >> 1)),
          v42,
          (unsigned __int16)v39);
        v20 = (unsigned __int64)(v19 + v18) >> 1;
        v9 = 1;
        *(_WORD *)(*((_QWORD *)&v53 + 1) + 2 * v20) = 0;
        goto LABEL_28;
      }
      goto LABEL_58;
    }
  }
LABEL_28:
  if ( v9 )
    v40 = v53;
  v42 = 0;
  if ( v43[2] )
  {
    FullPathName_Ustr = -1073741811;
    goto LABEL_47;
  }
  if ( (unsigned __int16)v40 < 2u )
    goto LABEL_82;
  v21 = **((_WORD **)&v40 + 1);
  if ( **((_WORD **)&v40 + 1) == 92 || v21 == 47 )
  {
    if ( (unsigned __int16)v40 < 4u )
      goto LABEL_82;
    v33 = *(_WORD *)(*((_QWORD *)&v40 + 1) + 2LL);
    if ( v33 != 92 && v33 != 47 )
      goto LABEL_82;
    if ( (unsigned __int16)v40 >= 6u )
    {
      v34 = *(_WORD *)(*((_QWORD *)&v40 + 1) + 4LL);
      if ( v34 == 46 || v34 == 63 )
      {
        if ( (unsigned __int16)v40 < 8u )
        {
          if ( (_WORD)v40 == 6 )
          {
LABEL_82:
            FullPathName_Ustr = 0;
            goto LABEL_47;
          }
        }
        else
        {
          v35 = *(_WORD *)(*((_QWORD *)&v40 + 1) + 6LL);
          if ( v35 == 92 || v35 == 47 )
          {
            v39 = 6;
            goto LABEL_40;
          }
        }
      }
    }
    v39 = 1;
    goto LABEL_40;
  }
  if ( (unsigned __int16)v40 < 4u )
    goto LABEL_82;
  if ( !v21 )
    goto LABEL_82;
  if ( *(_WORD *)(*((_QWORD *)&v40 + 1) + 2LL) != 58 )
    goto LABEL_82;
  if ( (unsigned __int16)v40 < 6u )
    goto LABEL_82;
  v22 = *(_WORD *)(*((_QWORD *)&v40 + 1) + 4LL);
  if ( v22 != 92 && v22 != 47 )
    goto LABEL_82;
  v39 = 2;
LABEL_40:
  FullPathName_Ustr = RtlGetFullPathName_UstrEx(
                        (unsigned int)&v40,
                        (unsigned int)v44,
                        (unsigned int)&v43[1],
                        (unsigned int)&v42,
                        0,
                        0,
                        (__int64)&v39,
                        0);
  if ( FullPathName_Ustr < 0 )
    goto LABEL_47;
  v23 = 0;
  v24 = *(_WORD *)v42;
  v25 = *((_WORD *)v42 + 1);
  v26 = *((_DWORD *)v42 + 1);
  v27 = *((_QWORD *)v42 + 1);
  if ( v39 == 6 && *(_WORD *)(*((_QWORD *)&v40 + 1) + 10LL) == 58 && *(_WORD *)(*((_QWORD *)&v40 + 1) + 12LL) == 92 )
  {
    WORD1(v40) -= 8;
    v28 = v40 - 8;
    LOWORD(v40) = v40 - 8;
    v24 -= 8;
    *((_QWORD *)&v40 + 1) += 8LL;
    v27 += 8;
    v25 -= 8;
  }
  else
  {
    v28 = v40;
  }
  if ( v28 > v24 )
  {
    DWORD1(v40) = v26;
    LOWORD(v40) = v24;
    WORD1(v40) = v25;
    v23 = v42 == &v43[1];
    *((_QWORD *)&v40 + 1) = v27;
  }
  FullPathName_Ustr = 0;
  if ( !v23 )
  {
LABEL_47:
    if ( v43[2] )
    {
      RtlpSysVolFree(v43[2]);
      v43[1] = 0;
      v43[2] = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    if ( FullPathName_Ustr < 0 )
      goto LABEL_58;
  }
  if ( (v10 & 1) == 0
    || !NtCurrentPeb()->ProcessParameters
    || (NtCurrentPeb()->ProcessParameters->Flags & 0x1000) == 0
    || (FullPathName_Ustr = sxsisol_RespectDotLocal(&v40, &v59, v43), FullPathName_Ustr >= 0) )
  {
    v29 = v43[0];
    if ( (v43[0] & 1) != 0
      || (!a4 && !a5 ? (v30 = 1) : (v30 = 0),
          FullPathName_Ustr = sxsisol_SearchActCtxForDllName(&v40, v30, &v51, a7, (unsigned __int16 *)&v59),
          FullPathName_Ustr >= 0) )
    {
      if ( !a5 && a4 && *((_QWORD *)&v59 + 1) != *(_QWORD *)(a4 + 8) )
      {
        FullPathName_Ustr = -1073741789;
        goto LABEL_58;
      }
      v32 = v52;
      if ( v52 )
      {
        FullPathName_Ustr = RtlFindCharInUnicodeString(1, &v59, &RtlDosPathSeperatorsString, &v41);
        if ( FullPathName_Ustr < 0 )
          goto LABEL_58;
        *v32 = ((unsigned __int64)(unsigned __int16)v41 >> 1) + 1;
      }
      FullPathName_Ustr = sxsisol_FreeUnicodeStringBufferAroundUnicodeStrings_Success(&v59);
      if ( FullPathName_Ustr >= 0 )
      {
        if ( a7 )
          *a7 = v29;
        FullPathName_Ustr = 0;
      }
    }
  }
LABEL_58:
  if ( FullPathName_Ustr >= 0 )
    goto LABEL_66;
  while ( 1 )
  {
    if ( (_BYTE)v64 )
    {
      if ( (_QWORD)v60 && (_QWORD)v60 != *((_QWORD *)&v60 + 1) )
        RtlpSysVolFree(v60);
      if ( *((_QWORD *)&v60 + 1) )
        **((_WORD **)&v60 + 1) = 0;
    }
    v59 = 0;
    v64 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
LABEL_66:
    if ( v43[2] )
    {
      RtlpSysVolFree(v43[2]);
      *(_OWORD *)&v43[1] = 0;
    }
    if ( v54 )
    {
      if ( v54 != v55 )
        RtlpSysVolFree(v54);
      v54 = v55;
      v56 = v57;
    }
    *((_QWORD *)&v53 + 1) = v55;
    if ( v55 )
      *v55 = 0;
    WORD1(v53) = v57;
    LOWORD(v53) = 0;
    if ( FullPathName_Ustr != -1072365567 )
      break;
    RtlAssert(
      "Internal error check failed",
      "minkernel\\ntdll\\sxsisol.cpp",
      433,
      "Status != STATUS_SXS_SECTION_NOT_FOUND");
    FullPathName_Ustr = -1073741595;
  }
  return (unsigned int)FullPathName_Ustr;
}

```

## disassembly

```asm
0x18001bcb0  mov     r11, rsp
0x18001bcb3  push    rbp
0x18001bcb4  push    rbx
0x18001bcb5  push    rdi
0x18001bcb6  lea     rbp, [r11-138h]
0x18001bcbd  sub     rsp, 220h
0x18001bcc4  mov     rax, cs:__security_cookie
0x18001bccb  xor     rax, rsp
0x18001bcce  mov     [rbp+130h+var_30], rax
0x18001bcd5  xor     edi, edi
0x18001bcd7  mov     [r11+8], rsi
0x18001bcdb  mov     rsi, [rbp+130h+arg_20]
0x18001bce2  lea     rax, [rbp+130h+var_B0]
0x18001bce9  xorps   xmm1, xmm1
0x18001bcec  mov     [r11+18h], r12
0x18001bcf0  mov     r12, [rbp+130h+arg_30]
0x18001bcf7  xorps   xmm0, xmm0
0x18001bcfa  mov     [r11+20h], r13
0x18001bcfe  mov     r13d, ecx
0x18001bd01  mov     rcx, [rbp+130h+arg_38]
0x18001bd08  mov     [rbp+130h+var_1A8], rax
0x18001bd0c  xor     eax, eax
0x18001bd0e  mov     [r11-20h], r14
0x18001bd12  mov     r14, r9
0x18001bd15  mov     r9, [rbp+130h+arg_40]
0x18001bd1c  mov     [rbp+130h+var_170], rcx
0x18001bd20  mov     [rsp+230h+var_1D0], r8
0x18001bd25  mov     qword ptr [rsp+230h+var_1C8+8], rdi
0x18001bd2a  mov     qword ptr [rsp+230h+var_1C8+10h], rdi
0x18001bd2f  mov     [rbp+130h+var_1B0], 800000h
0x18001bd37  mov     dword ptr [rbp+130h+var_168+4], edi
0x18001bd3a  mov     [rbp+130h+var_138], rdi
0x18001bd3e  mov     [rbp+130h+var_E0], rax
0x18001bd42  mov     [rbp+130h+var_178], rdi
0x18001bd46  mov     word ptr [rsp+230h+var_1D8], di
0x18001bd4b  mov     dword ptr [rsp+230h+var_1C8], edi
0x18001bd4f  movups  [rsp+230h+var_1F0+8], xmm0
0x18001bd54  movups  [rbp+130h+var_130], xmm1
0x18001bd58  movups  [rbp+130h+var_120], xmm1
0x18001bd5c  movups  [rbp+130h+var_110], xmm1
0x18001bd60  movups  [rbp+130h+var_100], xmm1
0x18001bd64  movups  [rbp+130h+var_F0], xmm1
0x18001bd68  test    r12, r12
0x18001bd6b  jz      short loc_18001BD71
0x18001bd6d  mov     [r12], edi
0x18001bd71  test    rcx, rcx
0x18001bd74  jz      short loc_18001BD79
0x18001bd76  mov     [rcx], rdi
0x18001bd79  test    r9, r9
0x18001bd7c  jz      short loc_18001BD85
0x18001bd7e  mov     qword ptr [r9], 208h
0x18001bd85  test    rsi, rsi
0x18001bd88  jz      short loc_18001BD8D
0x18001bd8a  movups  xmmword ptr [rsi], xmm0
0x18001bd8d  mov     [rsp+230h+var_20], r15
0x18001bd95  lea     rax, [rbp+130h+var_D0]
0x18001bd99  mov     [rbp+130h+var_158], rax
0x18001bd9d  lea     rax, [rbp+130h+var_D0]
0x18001bda1  mov     [rbp+130h+var_150], rax
0x18001bda5  mov     r9d, 20h ; ' '
0x18001bdab  mov     [rbp+130h+var_148], r9
0x18001bdaf  lea     rax, [rbp+130h+var_D0]
0x18001bdb3  mov     [rbp+130h+var_160], rax
0x18001bdb7  mov     r15d, 2
0x18001bdbd  mov     [rbp+130h+var_140], r9
0x18001bdc1  mov     [rbp+130h+var_D0], di
0x18001bdc5  mov     dword ptr [rbp+130h+var_168], 200000h
0x18001bdcc  test    r14, r14
0x18001bdcf  jnz     loc_18001C30A
0x18001bdd5  lea     rax, [rbp+130h+var_100]
0x18001bdd9  mov     qword ptr [rbp+130h+var_110], r15
0x18001bddd  mov     qword ptr [rbp+130h+var_120], rax
0x18001bde1  lea     rax, [rbp+130h+var_100]
0x18001bde5  mov     qword ptr [rbp+130h+var_120+8], rax
0x18001bde9  lea     rax, [rbp+130h+var_100]
0x18001bded  mov     qword ptr [rbp+130h+var_130+8], rax
0x18001bdf1  mov     qword ptr [rbp+130h+var_110+8], r15
0x18001bdf5  mov     word ptr [rbp+130h+var_100], di
0x18001bdf9  mov     dword ptr [rbp+130h+var_130], 20000h
0x18001be00  mov     rax, [rbp+130h+arg_28]
0x18001be07  mov     qword ptr [rbp+130h+var_F0+8], rax
0x18001be0b  mov     qword ptr [rbp+130h+var_100+8], r14
0x18001be0f  mov     qword ptr [rbp+130h+var_F0], rsi
0x18001be13  mov     byte ptr [rbp+130h+var_E0], 1
0x18001be17  test    r13d, 0FFFFFFFEh
0x18001be1e  jnz     loc_18001C253
0x18001be24  test    rdx, rdx
0x18001be27  jz      loc_18001C3FC
0x18001be2d  test    r14, r14
0x18001be30  jnz     loc_18001C237
0x18001be36  test    rsi, rsi
0x18001be39  jz      loc_18001C503
0x18001be3f  movups  xmm0, xmmword ptr [rdx]
0x18001be42  movups  [rsp+230h+var_1F0+8], xmm0
0x18001be47  test    r8, r8
0x18001be4a  jz      loc_18001BF93
0x18001be50  cmp     word ptr [r8], 0
0x18001be55  jz      loc_18001BF93
0x18001be5b  xor     eax, eax
0x18001be5d  lea     r9, [rsp+230h+var_1F0]
0x18001be62  lea     r8, qword_180170780
0x18001be69  mov     word ptr [rsp+230h+var_1F0], ax
0x18001be6e  lea     rdx, [rsp+230h+var_1F0+8]
0x18001be73  mov     ecx, 1
0x18001be78  call    RtlFindCharInUnicodeString
0x18001be7d  mov     ebx, eax
0x18001be7f  test    eax, eax
0x18001be81  jns     loc_18001C4FC
0x18001be87  cmp     eax, 0C0000225h
0x18001be8c  jnz     loc_18001C2B2
0x18001be92  xor     al, al
0x18001be94  test    al, al
0x18001be96  jnz     loc_18001BF93
0x18001be9c  mov     rcx, [rsp+230h+var_1D0]
0x18001bea1  xor     edx, edx
0x18001bea3  movzx   eax, word ptr [rsp+230h+var_1F0+8]
0x18001bea8  mov     word ptr [rsp+230h+var_1F0], ax
0x18001bead  mov     word ptr [rbp+130h+var_1A0], ax
0x18001beb1  movzx   eax, word ptr [rsp+230h+var_1F0+0Ah]
0x18001beb6  mov     word ptr [rbp+130h+var_1A0+2], ax
0x18001beba  mov     eax, dword ptr [rsp+230h+var_1F0+0Ch]
0x18001bebe  mov     dword ptr [rbp+130h+var_1A0+4], eax
0x18001bec1  mov     rax, qword ptr [rsp+230h+var_1E0]
0x18001bec6  mov     [rbp+130h+Src], rax
0x18001beca  mov     [rbp+130h+var_198], rax
0x18001bece  movzx   eax, word ptr [rcx]
0x18001bed1  mov     word ptr [rsp+230h+var_1F0+4], ax
0x18001bed6  mov     [rbp+130h+var_190], ax
0x18001beda  mov     eax, [rcx+2]
0x18001bedd  mov     [rbp+130h+var_18E], eax
0x18001bee0  movzx   eax, word ptr [rcx+6]
0x18001bee4  mov     [rbp+130h+var_18A], ax
0x18001bee8  mov     rax, [rcx+8]
0x18001beec  mov     [rsp+230h+var_1D0], rax
0x18001bef1  mov     [rbp+130h+var_188], rax
0x18001bef5  xor     eax, eax
0x18001bef7  mov     word ptr [rbp+130h+var_168], ax
0x18001befb  xor     ecx, ecx
0x18001befd  cmp     ecx, 2
0x18001bf00  jz      short loc_18001BF20
0x18001bf02  mov     eax, ecx
0x18001bf04  add     rax, rax
0x18001bf07  movzx   eax, word ptr [rbp+rax*8+130h+var_1A0]
0x18001bf0c  add     rdx, rax
0x18001bf0f  cmp     rdx, 0FFFEh
0x18001bf16  ja      loc_18001C4DF
0x18001bf1c  inc     ecx
0x18001bf1e  jmp     short loc_18001BEFD
0x18001bf20  lea     rdi, [rdx+2]
0x18001bf24  cmp     rdi, 0FFFEh
0x18001bf2b  ja      loc_18001C4DF
0x18001bf31  cmp     rdi, [rbp+130h+var_148]
0x18001bf35  ja      loc_18001C3D0
0x18001bf3b  mov     rcx, [rbp+130h+var_158]; void *
0x18001bf3f  mov     rdx, [rbp+130h+Src]; Src
0x18001bf43  mov     word ptr [rbp+130h+var_168+2], di
0x18001bf47  sub     di, 2
0x18001bf4b  mov     word ptr [rbp+130h+var_168], di
0x18001bf4f  movzx   edi, word ptr [rsp+230h+var_1F0]
0x18001bf54  mov     r8d, edi; Size
0x18001bf57  mov     [rbp+130h+var_160], rcx
0x18001bf5b  call    memmove
0x18001bf60  mov     rax, [rbp+130h+var_160]
0x18001bf64  mov     ecx, edi
0x18001bf66  movzx   ebx, word ptr [rsp+230h+var_1F0+4]
0x18001bf6b  mov     rdx, [rsp+230h+var_1D0]; Src
0x18001bf70  mov     r8d, ebx; Size
0x18001bf73  shr     rcx, 1
0x18001bf76  lea     rcx, [rax+rcx*2]; void *
0x18001bf7a  call    memmove
0x18001bf7f  mov     rax, [rbp+130h+var_160]
0x18001bf83  lea     rdx, [rbx+rdi]
0x18001bf87  shr     rdx, 1
0x18001bf8a  mov     dil, 1
0x18001bf8d  xor     ecx, ecx
0x18001bf8f  mov     [rax+rdx*2], cx
0x18001bf93  test    dil, dil
0x18001bf96  jz      short loc_18001BFBA
0x18001bf98  movzx   eax, word ptr [rbp+130h+var_168]
0x18001bf9c  mov     word ptr [rsp+230h+var_1F0+8], ax
0x18001bfa1  movzx   eax, word ptr [rbp+130h+var_168+2]
0x18001bfa5  mov     word ptr [rsp+230h+var_1F0+0Ah], ax
0x18001bfaa  mov     eax, dword ptr [rbp+130h+var_168+4]
0x18001bfad  mov     dword ptr [rsp+230h+var_1F0+0Ch], eax
0x18001bfb1  mov     rax, [rbp+130h+var_160]
0x18001bfb5  mov     qword ptr [rsp+230h+var_1E0], rax
0x18001bfba  xor     edi, edi
0x18001bfbc  mov     [rsp+230h+var_1D0], rdi
0x18001bfc1  cmp     qword ptr [rsp+230h+var_1C8+10h], rdi
0x18001bfc6  jnz     loc_18001C25D
0x18001bfcc  movzx   ecx, word ptr [rsp+230h+var_1F0+8]
0x18001bfd1  cmp     cx, 2
0x18001bfd5  jb      loc_18001C271
0x18001bfdb  mov     rax, qword ptr [rsp+230h+var_1E0]
0x18001bfe0  movzx   edx, word ptr [rax]
0x18001bfe3  cmp     dx, 5Ch ; '\'
0x18001bfe7  jz      loc_18001C2B9
0x18001bfed  cmp     dx, 2Fh ; '/'
0x18001bff1  jz      loc_18001C2B9
0x18001bff7  cmp     cx, 4
0x18001bffb  jb      loc_18001C271
0x18001c001  test    dx, dx
0x18001c004  jz      loc_18001C271
0x18001c00a  cmp     word ptr [rax+2], 3Ah ; ':'
0x18001c00f  jnz     loc_18001C271
0x18001c015  cmp     cx, 6
0x18001c019  jb      loc_18001C271
0x18001c01f  movzx   ecx, word ptr [rax+4]
0x18001c023  cmp     cx, 5Ch ; '\'
0x18001c027  jnz     loc_18001C267
0x18001c02d  mov     dword ptr [rsp+230h+var_1F0+4], r15d
0x18001c032  mov     qword ptr [rsp+230h+var_1F8], rdi
0x18001c037  lea     rax, [rsp+230h+var_1F0+4]
0x18001c03c  mov     [rsp+230h+var_200], rax
0x18001c041  lea     r9, [rsp+230h+var_1D0]
0x18001c046  mov     [rsp+230h+var_208], rdi
0x18001c04b  lea     r8, [rsp+230h+var_1C8+8]
0x18001c050  lea     rdx, [rbp+130h+var_1B0]
0x18001c054  mov     [rsp+230h+var_210], rdi
0x18001c059  lea     rcx, [rsp+230h+var_1F0+8]
0x18001c05e  call    RtlGetFullPathName_UstrEx
0x18001c063  mov     ebx, eax
0x18001c065  test    eax, eax
0x18001c067  js      short loc_18001C0AD
0x18001c069  mov     rdx, [rsp+230h+var_1D0]
0x18001c06e  xor     cl, cl
0x18001c070  cmp     dword ptr [rsp+230h+var_1F0+4], 6
0x18001c075  movzx   r9d, word ptr [rdx]
0x18001c079  movzx   r10d, word ptr [rdx+2]
0x18001c07e  mov     eax, [rdx+4]
0x18001c081  mov     r11, [rdx+8]
0x18001c085  jnz     short loc_18001C097
0x18001c087  mov     rbx, qword ptr [rsp+230h+var_1E0]
0x18001c08c  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x18001c091  jz      loc_18001C42B
0x18001c097  movzx   r8d, word ptr [rsp+230h+var_1F0+8]
0x18001c09d  cmp     r8w, r9w
0x18001c0a1  ja      loc_18001C406
0x18001c0a7  mov     ebx, edi
0x18001c0a9  test    cl, cl
0x18001c0ab  jnz     short loc_18001C0D3
0x18001c0ad  mov     rcx, qword ptr [rsp+230h+var_1C8+10h]
0x18001c0b2  test    rcx, rcx
0x18001c0b5  jz      short loc_18001C0CF
0x18001c0b7  call    RtlpSysVolFree
0x18001c0bc  xorps   xmm0, xmm0
0x18001c0bf  movups  xmmword ptr [rsp+230h+var_1C8+8], xmm0
0x18001c0c4  psrldq  xmm0, 8
0x18001c0c9  movq    qword ptr [rsp+230h+var_1C8+10h], xmm0
0x18001c0cf  test    ebx, ebx
0x18001c0d1  js      short loc_18001C146
0x18001c0d3  test    r13b, 1
0x18001c0d7  jz      short loc_18001C103
0x18001c0d9  mov     rax, gs:60h
0x18001c0e2  cmp     qword ptr [rax+20h], 0
0x18001c0e7  jz      short loc_18001C103
0x18001c0e9  mov     rax, gs:60h
0x18001c0f2  mov     rcx, [rax+20h]
0x18001c0f6  test    dword ptr [rcx+8], 1000h
0x18001c0fd  jnz     loc_18001C381
0x18001c103  mov     r15d, dword ptr [rsp+230h+var_1C8]
0x18001c108  test    r15b, 1
0x18001c10c  jnz     loc_18001C278
0x18001c112  test    r14, r14
0x18001c115  jnz     short loc_18001C120
0x18001c117  test    rsi, rsi
0x18001c11a  jz      loc_18001C347
0x18001c120  xor     dl, dl
0x18001c122  lea     rax, [rbp+130h+var_130]
0x18001c126  mov     r9, r12
0x18001c129  lea     r8, [rbp+130h+var_178]
0x18001c12d  mov     [rsp+230h+var_210], rax
0x18001c132  lea     rcx, [rsp+230h+var_1F0+8]
0x18001c137  call    sxsisol_SearchActCtxForDllName
0x18001c13c  mov     ebx, eax
0x18001c13e  test    eax, eax
0x18001c140  jns     loc_18001C278
0x18001c146  mov     r15, [rsp+230h+var_20]
0x18001c14e  mov     r14, [rsp+218h]
0x18001c156  mov     r13, [rsp+230h+arg_18]
0x18001c15e  mov     r12, [rsp+230h+arg_10]
0x18001c166  mov     rsi, [rsp+230h+arg_0]
0x18001c16e  xchg    ax, ax
0x18001c170  test    ebx, ebx
0x18001c172  jns     short loc_18001C1B7
0x18001c174  cmp     byte ptr [rbp+130h+var_E0], 0
0x18001c178  jz      short loc_18001C19A
0x18001c17a  mov     rcx, qword ptr [rbp+130h+var_120]
0x18001c17e  test    rcx, rcx
0x18001c181  jz      short loc_18001C18E
0x18001c183  cmp     rcx, qword ptr [rbp+130h+var_120+8]
0x18001c187  jz      short loc_18001C18E
0x18001c189  call    RtlpSysVolFree
0x18001c18e  mov     rcx, qword ptr [rbp+130h+var_120+8]
0x18001c192  test    rcx, rcx
0x18001c195  jz      short loc_18001C19A
0x18001c197  mov     [rcx], di
0x18001c19a  xorps   xmm0, xmm0
0x18001c19d  xor     eax, eax
0x18001c19f  movups  [rbp+130h+var_130], xmm0
  ... truncated ...
```
