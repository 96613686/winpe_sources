# _AttributesFromHashing(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x180075b20`
- end: `0x1800763a3`
- name: `?_AttributesFromHashing@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `2179`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180066c10`
- `0x18006d5dc`
- `0x180075b20`
- `0x1800771c8`
- `0x180077298`
- `0x180077c64`
- `0x18010c7e8`

## string_xrefs

- `0x180075c42`: `_SetFileAttributeValue`
- `0x180075d26`: `_SetFileAttributeValue`
- `0x180075ef8`: `_SetFileAttributeValue`
- `0x180076128`: `_SetFileAttributeValue`
- `0x180076220`: `_SetFileAttributeValue`
- `0x180076320`: `_SetFileAttributeValue`
- `0x180075c49`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x180075d2d`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x180075eff`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x18007612f`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x18007620b`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x180076319`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromHashing(struct AslFileMapping *a1, _DWORD *a2, __int64 a3, int a4)
{
  signed int v7; // edi
  int v8; // r10d
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 *v13; // rcx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  int v16; // r10d
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rdx
  _WORD *v20; // r8
  _WORD *v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // r14
  int v25; // r10d
  __int64 v26; // rax
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  _WORD *v29; // r8
  _WORD *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // r12
  unsigned __int16 *v33; // r15
  unsigned __int16 *v34; // r12
  _QWORD *v35; // rax
  __int64 v36; // rcx
  unsigned __int16 *v37; // rdx
  __int64 v38; // r9
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rcx
  __int64 v41; // r9
  signed int v42; // eax
  int v43; // r10d
  unsigned __int16 *v44; // rax
  __int64 v45; // rdx
  _WORD *v46; // r8
  _WORD *v47; // rcx
  int v48; // edi
  __int64 v49; // rax
  _WORD *v50; // rcx
  _WORD *v51; // r11
  _WORD *v52; // rcx
  int v53; // r9d
  __int64 v54; // r14
  const wchar_t *v55; // rax
  _WORD *v56; // r8
  _WORD *v57; // rcx
  __int64 v59; // [rsp+20h] [rbp-E0h]
  __int64 v60; // [rsp+30h] [rbp-D0h] BYREF
  int v61; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v63[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v64[33]; // [rsp+58h] [rbp-A8h] BYREF
  char v65; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v66[48]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v67[18]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v61 = a4;
  v62 = 0;
  LODWORD(v60) = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v8 = dword_18015575C;
  v9 = 260;
  v10 = -1;
  v62 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
  if ( v62 < 0x100000000LL )
    v10 = v62;
  LODWORD(v60) = v10;
  if ( (unsigned int)dword_18015575C <= 2 )
  {
    a2[5576] = v62;
  }
  else if ( dword_18015575C == 3 )
  {
    *((_QWORD *)a2 + 2788) = v62;
  }
  else
  {
    if ( dword_18015575C != 4 )
      goto LABEL_19;
    v11 = 4;
    v12 = 260;
    v13 = &v62;
    v14 = a2 + 5576;
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)v13 )
        break;
      *v14 = *(_WORD *)v13;
      v13 = (unsigned __int64 *)((char *)v13 + 2);
      ++v14;
      --v11;
      --v12;
    }
    while ( v12 );
    v15 = v14 - 1;
    if ( v12 )
      v15 = v14;
    *v15 = 0;
    if ( !v12 )
    {
      AslLogCallPrintf(
        1,
        "_SetFileAttributeValue",
        3178,
        "StringCbCopy failed to copy string attribute (index %d) [%x]",
        41,
        -2147024774);
      goto LABEL_19;
    }
  }
  a2[5706] = 41;
  a2[5707] = v8;
  a2[5708] = 1;
LABEL_19:
  v16 = dword_1801553CC;
  if ( (unsigned int)dword_1801553CC <= 2 )
  {
    a2[408] = v60;
    goto LABEL_32;
  }
  if ( dword_1801553CC == 3 )
  {
    *((_QWORD *)a2 + 204) = v60;
    goto LABEL_32;
  }
  if ( dword_1801553CC == 4 )
  {
    v17 = 2;
    v18 = &v60;
    v19 = 260;
    v20 = a2 + 408;
    do
    {
      if ( !v17 )
        break;
      if ( !*(_WORD *)v18 )
        break;
      *v20 = *(_WORD *)v18;
      v18 = (__int64 *)((char *)v18 + 2);
      ++v20;
      --v17;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    if ( !v19 )
    {
      AslLogCallPrintf(
        1,
        "_SetFileAttributeValue",
        3178,
        "StringCbCopy failed to copy string attribute (index %d) [%x]",
        3,
        -2147024774);
      goto LABEL_33;
    }
LABEL_32:
    a2[538] = 3;
    a2[539] = v16;
    a2[540] = 1;
  }
LABEL_33:
  if ( a2[1632] == 1 )
    goto LABEL_102;
  v22 = _SetFarAttributeFromAslAttribute(a1, 28, 12, a2);
  v7 = v22;
  if ( v22 < 0 || a2[1764] != 1 )
  {
    LODWORD(v59) = v22;
    AslLogCallPrintf(
      1,
      "_AttributesFromHashing",
      1678,
      "_SetFarAttributeFromAslAttribute failed to set FA_BIN_TYPE [%x]",
      v59);
    return (unsigned int)v7;
  }
  if ( a2[1632] <= 1u || !(_DWORD)v60 )
  {
LABEL_102:
    if ( (a3 & 0x20000) != 0 )
    {
      v53 = dword_18015551C;
      if ( (unsigned int)dword_18015551C <= 2 )
      {
        a2[2312] = 3145776;
        goto LABEL_116;
      }
      if ( dword_18015551C == 3 )
      {
        *((_QWORD *)a2 + 1156) = 0x30003000300030LL;
        goto LABEL_116;
      }
      if ( dword_18015551C == 4 )
      {
        v54 = 45;
        v55 = L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709";
        v56 = a2 + 2312;
        do
        {
          if ( !v54 )
            break;
          if ( !*v55 )
            break;
          *v56++ = *v55++;
          --v54;
          --v9;
        }
        while ( v9 );
        v57 = v56 - 1;
        if ( v9 )
          v57 = v56;
        *v57 = 0;
        if ( !v9 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            17,
            -2147024774);
          return 1;
        }
LABEL_116:
        a2[2442] = 17;
        a2[2443] = v53;
        a2[2444] = 1;
      }
    }
    return 1;
  }
  v23 = AslFileMappingEnsureMappedAs(*(_QWORD *)a1);
  if ( v23 >= 0 )
  {
    v24 = 45;
    if ( (a3 & 0x20) == 0 )
      goto LABEL_59;
    if ( (int)a2[1632] <= 4 )
      goto LABEL_59;
    memset_0(v66, 0, 0x5Au);
    if ( (int)_ComputePeHeaderHash(a1, v66) < 0 )
      goto LABEL_59;
    v25 = dword_1801553FC;
    if ( (unsigned int)dword_1801553FC <= 2 )
    {
      a2[680] = *(_DWORD *)v66;
    }
    else if ( dword_1801553FC == 3 )
    {
      *((_QWORD *)a2 + 340) = *(_QWORD *)v66;
    }
    else
    {
      if ( dword_1801553FC != 4 )
        goto LABEL_59;
      v26 = 45;
      v27 = v66;
      v28 = 260;
      v29 = a2 + 680;
      do
      {
        if ( !v26 )
          break;
        if ( !*v27 )
          break;
        *v29++ = *v27++;
        --v26;
        --v28;
      }
      while ( v28 );
      v30 = v29 - 1;
      if ( v28 )
        v30 = v29;
      *v30 = 0;
      if ( !v28 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          5,
          -2147024774);
        goto LABEL_59;
      }
    }
    a2[810] = 5;
    a2[811] = v25;
    a2[812] = 1;
LABEL_59:
    v31 = a3 & 0x20000;
    v32 = a3 & 0x80000000000LL;
    if ( !v31 && !v32 )
      return 0;
    memset_0(v66, 0, 0x5Au);
    memset_0(v67, 0, 0x82u);
    v33 = (unsigned __int16 *)((unsigned __int64)v66 & -(__int64)(v31 != 0));
    v34 = (unsigned __int16 *)((unsigned __int64)v67 & -(__int64)(v32 != 0));
    if ( (v61 & 1) == 0 )
    {
      memset_0(v64, 0, 0x208u);
      v35 = *(_QWORD **)a1;
      v63[0] = 1;
      v63[1] = 528;
      v64[0] = *v35;
      v7 = AeWERQueryFileInfo((__int64)v63);
      if ( v7 >= 0 )
      {
        v36 = 2147483646;
        v37 = (unsigned __int16 *)&v65;
        v38 = 45;
        v39 = v66;
        do
        {
          if ( !v36 )
            break;
          if ( !*v37 )
            break;
          *v39++ = *v37++;
          --v36;
          --v38;
        }
        while ( v38 );
        v40 = v39 - 1;
        if ( v38 )
          v40 = v39;
        v7 = v38 == 0 ? 0x8007007A : 0;
        *v40 = 0;
      }
    }
    v41 = *(_QWORD *)v66;
    if ( !v66[0] )
    {
      v42 = _ComputeFileHashes(a1, v33, v34);
      v41 = *(_QWORD *)v66;
      v7 = v42;
    }
    if ( v7 < 0 )
      return 0;
    v43 = dword_18015551C;
    if ( (unsigned int)dword_18015551C <= 2 )
    {
      a2[2312] = v41;
    }
    else if ( dword_18015551C == 3 )
    {
      *((_QWORD *)a2 + 1156) = v41;
    }
    else
    {
      if ( dword_18015551C != 4 )
        goto LABEL_87;
      v44 = v66;
      v45 = 260;
      v46 = a2 + 2312;
      do
      {
        if ( !v24 )
          break;
        if ( !*v44 )
          break;
        *v46++ = *v44++;
        --v24;
        --v45;
      }
      while ( v45 );
      v47 = v46 - 1;
      if ( v45 )
        v47 = v46;
      *v47 = 0;
      if ( !v45 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          17,
          -2147024774);
        goto LABEL_87;
      }
    }
    a2[2442] = 17;
    a2[2443] = v43;
    a2[2444] = 1;
LABEL_87:
    v48 = dword_18015578C;
    if ( (unsigned int)dword_18015578C <= 2 )
    {
      a2[5848] = v67[0];
    }
    else if ( dword_18015578C == 3 )
    {
      *((_QWORD *)a2 + 2924) = v67[0];
    }
    else
    {
      if ( dword_18015578C != 4 )
        return 0;
      v49 = 65;
      v50 = v67;
      v51 = a2 + 5848;
      do
      {
        if ( !v49 )
          break;
        if ( !*v50 )
          break;
        *v51++ = *v50++;
        --v49;
        --v9;
      }
      while ( v9 );
      v52 = v51 - 1;
      if ( v9 )
        v52 = v51;
      *v52 = 0;
      if ( !v9 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          43,
          -2147024774);
        return 0;
      }
    }
    a2[5978] = 43;
    a2[5979] = v48;
    a2[5980] = 1;
    return 0;
  }
  v7 = v23 | 0x10000000;
  if ( v23 != -1073741538 )
  {
    LODWORD(v59) = v23 | 0x10000000;
    AslLogCallPrintf(1, "_AttributesFromHashing", 1716, "Failed to ensure the file mapping as data [%x]", v59);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180075b20  mov     [rsp-8+arg_10], rbx
0x180075b25  push    rbp
0x180075b26  push    rsi
0x180075b27  push    rdi
0x180075b28  push    r12
0x180075b2a  push    r13
0x180075b2c  push    r14
0x180075b2e  push    r15
0x180075b30  lea     rbp, [rsp-260h]
0x180075b38  sub     rsp, 360h
0x180075b3f  mov     rax, cs:__security_cookie
0x180075b46  xor     rax, rsp
0x180075b49  mov     [rbp+290h+var_40], rax
0x180075b50  xor     r15d, r15d
0x180075b53  mov     [rsp+390h+var_358], r9d
0x180075b58  mov     [rsp+390h+var_350], r15
0x180075b5d  mov     r12, r8
0x180075b60  mov     dword ptr [rsp+390h+var_360], r15d
0x180075b65  mov     rbx, rdx
0x180075b68  mov     r13, rcx
0x180075b6b  test    rdx, rdx
0x180075b6e  jnz     short loc_180075B7A
0x180075b70  mov     edi, 80070057h
0x180075b75  jmp     loc_180076377
0x180075b7a  mov     rax, [rcx]
0x180075b7d  mov     edi, 80004005h
0x180075b82  mov     r10d, cs:dword_18015575C
0x180075b89  mov     rcx, 100000000h
0x180075b93  mov     esi, 104h
0x180075b98  mov     r14d, 1
0x180075b9e  mov     rdx, [rax+18h]
0x180075ba2  or      eax, 0FFFFFFFFh
0x180075ba5  cmp     rdx, rcx
0x180075ba8  mov     [rsp+390h+var_350], rdx
0x180075bad  mov     ecx, r10d
0x180075bb0  cmovb   eax, edx
0x180075bb3  mov     dword ptr [rsp+390h+var_360], eax
0x180075bb7  test    r10d, r10d
0x180075bba  jz      loc_180075C71
0x180075bc0  sub     ecx, r14d
0x180075bc3  jz      loc_180075C71
0x180075bc9  sub     ecx, r14d
0x180075bcc  jz      loc_180075C71
0x180075bd2  sub     ecx, r14d
0x180075bd5  jz      loc_180075C68
0x180075bdb  cmp     ecx, r14d
0x180075bde  jnz     loc_180075C8F
0x180075be4  lea     eax, [r14+3]
0x180075be8  mov     edx, esi
0x180075bea  lea     rcx, [rsp+390h+var_350]
0x180075bef  lea     r8, [rbx+5720h]
0x180075bf6  test    rax, rax
0x180075bf9  jz      short loc_180075C19
0x180075bfb  movzx   r9d, word ptr [rcx]
0x180075bff  test    r9w, r9w
0x180075c03  jz      short loc_180075C19
0x180075c05  mov     [r8], r9w
0x180075c09  add     rcx, 2
0x180075c0d  add     r8, 2
0x180075c11  sub     rax, r14
0x180075c14  sub     rdx, r14
0x180075c17  jnz     short loc_180075BF6
0x180075c19  mov     rax, rdx
0x180075c1c  lea     rcx, [r8-2]
0x180075c20  neg     rax
0x180075c23  sbb     r9d, r9d
0x180075c26  not     r9d
0x180075c29  and     r9d, 8007007Ah
0x180075c30  test    rdx, rdx
0x180075c33  cmovnz  rcx, r8
0x180075c37  mov     [rcx], r15w
0x180075c3b  jnz     short loc_180075C77
0x180075c3d  mov     [rsp+390h+var_368], r9d
0x180075c42  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180075c49  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075c50  mov     dword ptr [rsp+390h+var_370], 29h ; ')'
0x180075c58  mov     r8d, 0C6Ah
0x180075c5e  mov     ecx, r14d
0x180075c61  call    AslLogCallPrintf
0x180075c66  jmp     short loc_180075C8F
0x180075c68  mov     [rbx+5720h], rdx
0x180075c6f  jmp     short loc_180075C77
0x180075c71  mov     [rbx+5720h], edx
0x180075c77  mov     dword ptr [rbx+5928h], 29h ; ')'
0x180075c81  mov     [rbx+592Ch], r10d
0x180075c88  mov     [rbx+5930h], r14d
0x180075c8f  mov     r10d, cs:dword_1801553CC
0x180075c96  mov     ecx, r10d
0x180075c99  test    r10d, r10d
0x180075c9c  jz      loc_180075D5A
0x180075ca2  sub     ecx, r14d
0x180075ca5  jz      loc_180075D5A
0x180075cab  sub     ecx, r14d
0x180075cae  jz      loc_180075D5A
0x180075cb4  sub     ecx, r14d
0x180075cb7  jz      loc_180075D4C
0x180075cbd  cmp     ecx, r14d
0x180075cc0  jnz     loc_180075D7C
0x180075cc6  mov     eax, 2
0x180075ccb  lea     rcx, [rsp+390h+var_360]
0x180075cd0  mov     rdx, rsi
0x180075cd3  lea     r8, [rbx+660h]
0x180075cda  test    rax, rax
0x180075cdd  jz      short loc_180075CFD
0x180075cdf  movzx   r9d, word ptr [rcx]
0x180075ce3  test    r9w, r9w
0x180075ce7  jz      short loc_180075CFD
0x180075ce9  mov     [r8], r9w
0x180075ced  add     rcx, 2
0x180075cf1  add     r8, 2
0x180075cf5  sub     rax, r14
0x180075cf8  sub     rdx, r14
0x180075cfb  jnz     short loc_180075CDA
0x180075cfd  mov     rax, rdx
0x180075d00  lea     rcx, [r8-2]
0x180075d04  neg     rax
0x180075d07  sbb     r9d, r9d
0x180075d0a  not     r9d
0x180075d0d  and     r9d, 8007007Ah
0x180075d14  test    rdx, rdx
0x180075d17  cmovnz  rcx, r8
0x180075d1b  mov     [rcx], r15w
0x180075d1f  jnz     short loc_180075D64
0x180075d21  mov     [rsp+390h+var_368], r9d
0x180075d26  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180075d2d  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075d34  mov     dword ptr [rsp+390h+var_370], 3
0x180075d3c  mov     r8d, 0C6Ah
0x180075d42  mov     ecx, r14d
0x180075d45  call    AslLogCallPrintf
0x180075d4a  jmp     short loc_180075D7C
0x180075d4c  mov     rax, [rsp+390h+var_360]
0x180075d51  mov     [rbx+660h], rax
0x180075d58  jmp     short loc_180075D64
0x180075d5a  mov     eax, dword ptr [rsp+390h+var_360]
0x180075d5e  mov     [rbx+660h], eax
0x180075d64  mov     dword ptr [rbx+868h], 3
0x180075d6e  mov     [rbx+86Ch], r10d
0x180075d75  mov     [rbx+870h], r14d
0x180075d7c  cmp     [rbx+1980h], r14d
0x180075d83  jz      loc_180076276
0x180075d89  mov     edx, 1Ch
0x180075d8e  mov     r9, rbx
0x180075d91  mov     rcx, r13
0x180075d94  lea     r8d, [rdx-10h]
0x180075d98  call    ?_SetFarAttributeFromAslAttribute@@YAJAEAVAslFileMapping@@W4ASL_ATTRIBUTE_INDEX@@W4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFarAttributeFromAslAttribute(AslFileMapping &,ASL_ATTRIBUTE_INDEX,FILEATTRID,tagFILEATTRIBUTE *)
0x180075d9d  mov     edi, eax
0x180075d9f  test    eax, eax
0x180075da1  js      short loc_180075DAC
0x180075da3  cmp     [rbx+1B90h], r14d
0x180075daa  jz      short loc_180075DD1
0x180075dac  mov     dword ptr [rsp+390h+var_370], eax
0x180075db0  lea     r9, aSetfarattribut; "_SetFarAttributeFromAslAttribute failed"...
0x180075db7  mov     r8d, 68Eh
0x180075dbd  lea     rdx, aAttributesfrom_1; "_AttributesFromHashing"
0x180075dc4  mov     ecx, r14d
0x180075dc7  call    AslLogCallPrintf
0x180075dcc  jmp     loc_180076377
0x180075dd1  cmp     [rbx+1980h], r14d
0x180075dd8  jbe     loc_180076276
0x180075dde  cmp     dword ptr [rsp+390h+var_360], r15d
0x180075de3  jz      loc_180076276
0x180075de9  mov     rcx, [r13+0]
0x180075ded  call    AslFileMappingEnsureMappedAs
0x180075df2  test    eax, eax
0x180075df4  jns     short loc_180075E1A
0x180075df6  mov     edi, eax
0x180075df8  bts     edi, 1Ch
0x180075dfc  cmp     eax, 0C000011Eh
0x180075e01  jz      loc_180076377
0x180075e07  mov     dword ptr [rsp+390h+var_370], edi
0x180075e0b  lea     r9, aFailedToEnsure_0; "Failed to ensure the file mapping as da"...
0x180075e12  mov     r8d, 6B4h
0x180075e18  jmp     short loc_180075DBD
0x180075e1a  mov     r14d, 2Dh ; '-'
0x180075e20  test    r12b, 20h
0x180075e24  jz      loc_180075F57
0x180075e2a  cmp     dword ptr [rbx+1980h], 4
0x180075e31  jle     loc_180075F57
0x180075e37  xor     edx, edx; Val
0x180075e39  lea     r8d, [r14+2Dh]; Size
0x180075e3d  lea     rcx, [rbp+290h+var_130]; void *
0x180075e44  call    memset_0
0x180075e49  lea     rdx, [rbp+290h+var_130]; unsigned __int16 *
0x180075e50  mov     rcx, r13; struct AslFileMapping *
0x180075e53  call    ?_ComputePeHeaderHash@@YAJAEAVAslFileMapping@@PEAG@Z; _ComputePeHeaderHash(AslFileMapping &,ushort *)
0x180075e58  test    eax, eax
0x180075e5a  js      loc_180075F57
0x180075e60  mov     r10d, cs:dword_1801553FC
0x180075e67  mov     ecx, r10d
0x180075e6a  test    r10d, r10d
0x180075e6d  jz      loc_180075F30
0x180075e73  sub     ecx, 1
0x180075e76  jz      loc_180075F30
0x180075e7c  sub     ecx, 1
0x180075e7f  jz      loc_180075F30
0x180075e85  sub     ecx, 1
0x180075e88  jz      loc_180075F20
0x180075e8e  cmp     ecx, 1
0x180075e91  jnz     loc_180075F57
0x180075e97  mov     eax, r14d
0x180075e9a  lea     rcx, [rbp+290h+var_130]
0x180075ea1  mov     rdx, rsi
0x180075ea4  lea     r8, [rbx+0AA0h]
0x180075eab  test    rax, rax
0x180075eae  jz      short loc_180075ECF
0x180075eb0  movzx   r9d, word ptr [rcx]
0x180075eb4  test    r9w, r9w
0x180075eb8  jz      short loc_180075ECF
0x180075eba  mov     [r8], r9w
0x180075ebe  add     rcx, 2
0x180075ec2  add     r8, 2
0x180075ec6  dec     rax
0x180075ec9  sub     rdx, 1
0x180075ecd  jnz     short loc_180075EAB
0x180075ecf  mov     rax, rdx
0x180075ed2  lea     rcx, [r8-2]
0x180075ed6  neg     rax
0x180075ed9  sbb     r9d, r9d
0x180075edc  not     r9d
0x180075edf  and     r9d, 8007007Ah
0x180075ee6  test    rdx, rdx
0x180075ee9  cmovnz  rcx, r8
0x180075eed  mov     [rcx], r15w
0x180075ef1  jnz     short loc_180075F3C
0x180075ef3  mov     [rsp+390h+var_368], r9d
0x180075ef8  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180075eff  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x180075f06  mov     dword ptr [rsp+390h+var_370], 5
0x180075f0e  mov     r8d, 0C6Ah
0x180075f14  mov     ecx, 1
0x180075f19  call    AslLogCallPrintf
0x180075f1e  jmp     short loc_180075F57
0x180075f20  mov     rax, qword ptr [rbp+290h+var_130]
0x180075f27  mov     [rbx+0AA0h], rax
0x180075f2e  jmp     short loc_180075F3C
0x180075f30  mov     eax, dword ptr [rbp+290h+var_130]
0x180075f36  mov     [rbx+0AA0h], eax
0x180075f3c  mov     dword ptr [rbx+0CA8h], 5
0x180075f46  mov     [rbx+0CACh], r10d
0x180075f4d  mov     dword ptr [rbx+0CB0h], 1
0x180075f57  mov     r15, r12
0x180075f5a  mov     rax, 80000000000h
0x180075f64  and     r15d, 20000h
0x180075f6b  and     r12, rax
0x180075f6e  test    r15, r15
0x180075f71  jnz     short loc_180075F7C
0x180075f73  test    r12, r12
0x180075f76  jz      loc_18007626B
0x180075f7c  xor     edx, edx; Val
0x180075f7e  lea     rcx, [rbp+290h+var_130]; void *
0x180075f85  lea     r8d, [rdx+5Ah]; Size
0x180075f89  call    memset_0
0x180075f8e  xor     edx, edx; Val
0x180075f90  lea     rcx, [rbp+290h+var_D0]; void *
0x180075f97  mov     r8d, 82h; Size
0x180075f9d  call    memset_0
0x180075fa2  neg     r15
0x180075fa5  lea     rax, [rbp+290h+var_130]
0x180075fac  sbb     r15, r15
0x180075faf  and     r15, rax
0x180075fb2  lea     rax, [rbp+290h+var_D0]
0x180075fb9  neg     r12
0x180075fbc  sbb     r12, r12
0x180075fbf  and     r12, rax
0x180075fc2  test    byte ptr [rsp+390h+var_358], 1
0x180075fc7  jnz     loc_180076063
0x180075fcd  xor     edx, edx; Val
0x180075fcf  lea     rcx, [rsp+390h+var_338]; void *
0x180075fd4  mov     r8d, 208h; Size
0x180075fda  call    memset_0
0x180075fdf  mov     rax, [r13+0]
0x180075fe3  mov     [rsp+390h+var_340], 1
0x180075feb  mov     [rsp+390h+var_33C], 210h
0x180075ff3  mov     rcx, [rax]
0x180075ff6  mov     [rsp+390h+var_338], rcx
0x180075ffb  lea     rcx, [rsp+390h+var_340]
0x180076000  call    AeWERQueryFileInfo
0x180076005  xor     r10d, r10d
0x180076008  mov     edi, eax
0x18007600a  test    eax, eax
0x18007600c  js      short loc_180076066
0x18007600e  mov     ecx, 7FFFFFFEh
0x180076013  lea     rdx, [rbp+290h+var_230]
0x180076017  mov     r9, r14
0x18007601a  lea     rax, [rbp+290h+var_130]
0x180076021  test    rcx, rcx
0x180076024  jz      short loc_180076045
0x180076026  movzx   r8d, word ptr [rdx]
0x18007602a  test    r8w, r8w
0x18007602e  jz      short loc_180076045
0x180076030  mov     [rax], r8w
0x180076034  add     rdx, 2
0x180076038  add     rax, 2
0x18007603c  dec     rcx
0x18007603f  sub     r9, 1
0x180076043  jnz     short loc_180076021
0x180076045  test    r9, r9
0x180076048  lea     rcx, [rax-2]
0x18007604c  cmovnz  rcx, rax
  ... truncated ...
```
