# RtlDosSearchPath_Ustr

- ea: `0x18005c960`
- end: `0x18005d2b1`
- name: `RtlDosSearchPath_Ustr`
- size: `2385`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, loader_planting`

## callees

- `0x18001861c`
- `0x18001bcb0`
- `0x18001c520`
- `0x18001d490`
- `0x180021fe0`
- `0x18005c960`
- `0x18005d2c0`
- `0x18005d310`
- `0x18005d660`
- `0x18005d730`
- `0x18015e4b0`
- `0x18015ea70`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlDosSearchPath_Ustr(
        int a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const void **a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  char v12; // bl
  int v13; // eax
  __int64 v14; // rdx
  _QWORD *v15; // r8
  __int64 v16; // r9
  const void **v17; // r11
  int FullPathName_Ustr; // ebx
  _WORD *v19; // rcx
  unsigned __int64 v20; // r10
  unsigned __int16 v21; // bx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  __int16 v25; // ax
  unsigned __int64 v26; // r11
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rcx
  __int64 v31; // rcx
  __int16 v32; // ax
  __int64 v33; // r12
  unsigned __int64 v34; // r8
  _WORD *v35; // rbx
  _WORD *v36; // r15
  _WORD *v37; // r14
  __int64 v38; // rdi
  bool v39; // zf
  unsigned __int16 v40; // di
  unsigned __int16 v41; // si
  unsigned __int64 v42; // rdx
  unsigned __int16 v43; // r10
  __int16 v44; // r11
  __int16 v45; // r9
  _WORD *v46; // r8
  unsigned __int64 v47; // rcx
  unsigned __int64 i; // rdx
  unsigned __int16 v49; // r10
  _WORD *v50; // r8
  unsigned __int64 v51; // r11
  __int16 v52; // r10
  unsigned __int64 v53; // r11
  unsigned __int64 v54; // rcx
  _WORD *v55; // r9
  unsigned __int64 j; // rdx
  const void **v57; // rsi
  _WORD *v58; // r8
  unsigned __int64 v59; // r11
  __int16 v60; // r10
  unsigned __int64 v61; // r11
  unsigned __int64 v62; // rax
  _WORD *v63; // r9
  unsigned __int64 k; // rdx
  __int64 v65; // rdi
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rbx
  int v69; // esi
  int v70; // eax
  int v72; // eax
  __int64 v73; // r8
  unsigned __int16 v74; // ax
  __int16 v75; // r9
  __int16 v76; // ax
  __int64 v77; // rdx
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rdx
  __int16 v80; // r8
  unsigned __int64 v81; // rax
  unsigned __int64 v82; // r8
  unsigned __int64 v83; // rcx
  __int16 v84; // ax
  __m128i v85; // [rsp+50h] [rbp-B0h] BYREF
  int v86; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v87; // [rsp+68h] [rbp-98h]
  _DWORD *v88; // [rsp+70h] [rbp-90h] BYREF
  __int64 v89; // [rsp+78h] [rbp-88h]
  __int128 v90; // [rsp+80h] [rbp-80h] BYREF
  const void **v91; // [rsp+90h] [rbp-70h]
  __int128 v92; // [rsp+98h] [rbp-68h] BYREF
  __int128 v93; // [rsp+A8h] [rbp-58h]
  _QWORD *v94; // [rsp+B8h] [rbp-48h]
  _QWORD *v95; // [rsp+C0h] [rbp-40h]
  __int64 v96; // [rsp+C8h] [rbp-38h]
  __int128 v97; // [rsp+D0h] [rbp-30h] BYREF
  __m256i v98; // [rsp+E0h] [rbp-20h]
  _OWORD v99[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v100; // [rsp+120h] [rbp+20h]
  _BYTE v101[528]; // [rsp+130h] [rbp+30h] BYREF

  v91 = a4;
  v12 = a1;
  v89 = a5;
  v87 = a9;
  v96 = a6;
  v95 = a7;
  v94 = a8;
  v85.m128i_i64[0] = 34078720;
  v85.m128i_i64[1] = (__int64)v101;
  if ( a7 )
    *a7 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a6 )
  {
    *(_DWORD *)a6 = 0;
    *(_QWORD *)(a6 + 8) = 0;
  }
  if ( (a1 & 0xFFFFFFF8) != 0 || !a2 || !a3 || a5 && a6 && !a7 )
    return 3221225485LL;
  v13 = RtlDetermineDosPathNameType_Ustr(a3, a2, a9, a5);
  v86 = v13;
  if ( (v12 & 2) != 0 )
  {
    if ( v13 != 5 )
    {
LABEL_17:
      LOBYTE(v14) = 1;
      if ( (unsigned __int8)RtlDoesFileExists_UstrEx(a3, v14) )
      {
        FullPathName_Ustr = RtlGetFullPathName_UstrEx(
                              (_DWORD)a3,
                              v89,
                              a6,
                              (_DWORD)a7,
                              (__int64)a8,
                              0,
                              (__int64)&v86,
                              (__int64)v87);
        if ( FullPathName_Ustr < 0 )
          goto LABEL_81;
        goto LABEL_86;
      }
      if ( a4 )
      {
        v77 = *(unsigned __int16 *)a4;
        if ( (_WORD)v77 )
        {
          if ( (v12 & 4) == 0 )
          {
            v81 = *a3;
            if ( (_WORD)v81 )
            {
              v82 = *((_QWORD *)a3 + 1);
              v83 = v82 + 2 * (v81 >> 1);
              while ( v83 > v82 )
              {
                v84 = *(_WORD *)(v83 - 2);
                v83 -= 2LL;
                if ( v84 == 92 || v84 == 47 )
                  break;
                if ( v84 == 46 )
                {
                  FullPathName_Ustr = -1073741809;
                  goto LABEL_81;
                }
              }
            }
          }
          v78 = *a3 + 2LL + v77;
          if ( v78 > 0xFFFE )
          {
            FullPathName_Ustr = -1073741562;
            goto LABEL_81;
          }
          if ( v78 > v85.m128i_u16[1] )
          {
            v85.m128i_i16[1] = v78;
            v85.m128i_i64[1] = RtlpAllocateAtom((unsigned __int16)v78);
            if ( !v85.m128i_i64[1] )
            {
LABEL_130:
              FullPathName_Ustr = -1073741801;
              goto LABEL_81;
            }
          }
          memmove((void *)v85.m128i_i64[1], *((const void **)a3 + 1), *a3);
          memmove((void *)(v85.m128i_i64[1] + 2 * ((unsigned __int64)*a3 >> 1)), a4[1], *(unsigned __int16 *)a4);
          v79 = (*(unsigned __int16 *)a4 + (unsigned __int64)*a3) >> 1;
          *(_WORD *)(v85.m128i_i64[1] + 2 * v79) = 0;
          LOBYTE(v79) = 1;
          v85.m128i_i16[0] = *(_WORD *)a4 + *a3;
          if ( (unsigned __int8)RtlDoesFileExists_UstrEx(&v85, v79) )
          {
            FullPathName_Ustr = RtlGetFullPathName_UstrEx(
                                  (unsigned int)&v85,
                                  v89,
                                  a6,
                                  (_DWORD)a7,
                                  (__int64)a8,
                                  0,
                                  (__int64)&v86,
                                  (__int64)v87);
            if ( FullPathName_Ustr >= 0 )
              FullPathName_Ustr = 0;
            goto LABEL_81;
          }
        }
      }
LABEL_113:
      FullPathName_Ustr = -1073741809;
      goto LABEL_81;
    }
    v14 = *a3;
    if ( (unsigned __int16)v14 >= 4u )
    {
      v19 = (_WORD *)*((_QWORD *)a3 + 1);
      if ( *v19 == 46 )
      {
        v80 = v19[1];
        if ( v80 == 92
          || v80 == 47
          || v80 == 46
          && (unsigned __int16)v14 >= 6u
          && ((v14 = (unsigned __int16)v19[2], (_WORD)v14 == 92) || (_WORD)v14 == 47) )
        {
          v86 = (int)v17;
          goto LABEL_17;
        }
        v15 = v87;
      }
    }
  }
  if ( v13 != 5 )
    goto LABEL_17;
  if ( (v12 & 1) == 0 )
  {
LABEL_24:
    v20 = (unsigned __int64)v17;
    v21 = (unsigned __int16)v17;
    if ( a4 )
    {
      v22 = *a3;
      v21 = *(_WORD *)a4;
      if ( (_WORD)v22 )
      {
        v23 = *((_QWORD *)a3 + 1);
        v24 = v23 + 2 * (v22 >> 1);
        while ( v24 > v23 )
        {
          v25 = *(_WORD *)(v24 - 2);
          v24 -= 2LL;
          if ( v25 == 92 || v25 == 47 )
            break;
          if ( v25 == 46 )
          {
            v91 = v17;
            v21 = (unsigned __int16)v17;
            break;
          }
        }
      }
    }
    v26 = 2 * ((unsigned __int64)*a2 >> 1);
    if ( *a2 )
    {
      v27 = *((_QWORD *)a2 + 1);
      v28 = v27 + v26;
      v29 = v27 + v26;
      if ( v27 + v26 > v27 )
      {
        do
        {
          v30 = v29 - 2;
          if ( *(_WORD *)(v29 - 2) == 59 )
          {
            v73 = (__int64)(v28 - v29 + 2) >> 1;
            v74 = v73 - 1;
            if ( (_WORD)v73 != 1 )
            {
              v75 = *(_WORD *)(v28 - 2);
              if ( v75 != 92 && v75 != 47 )
                v74 = v73;
            }
            v28 = v30;
            if ( v74 > v20 )
              v20 = v74;
          }
          v29 = v30;
        }
        while ( v30 > v27 );
      }
      v31 = (__int64)(v28 - v29) >> 1;
      if ( (_WORD)v31 )
      {
        v32 = *(_WORD *)(v28 - 2);
        if ( v32 != 92 && v32 != 47 )
          LOWORD(v31) = v31 + 1;
      }
      if ( (unsigned __int16)v31 > v20 )
        v20 = (unsigned __int16)v31;
      v20 *= 2LL;
    }
    v33 = v21;
    v34 = v21 + (unsigned __int64)*a3 + v20 + 2;
    v88 = (_DWORD *)v34;
    if ( v34 > 0xFFFE )
    {
      FullPathName_Ustr = -1073741562;
      goto LABEL_81;
    }
    v35 = (_WORD *)*((_QWORD *)a2 + 1);
    v36 = &v35[v26 / 2];
    while ( v35 < v36 )
    {
      v37 = v35;
      do
      {
        if ( *v37 == 59 )
          break;
        ++v37;
      }
      while ( v37 != v36 );
      v38 = v37 - v35;
      v39 = 2 * (_WORD)v38 == 0;
      v40 = 2 * v38;
      v41 = v40;
      if ( !v39 )
      {
        v76 = *(v37 - 1);
        if ( v76 != 92 && v76 != 47 )
          v41 = v40 + 2;
      }
      v42 = v33 + *a3 + v41;
      if ( v85.m128i_u16[1] < v42 + 2 )
      {
        if ( (_BYTE *)v85.m128i_i64[1] != v101 || v42 > 0xFFFC )
          goto LABEL_106;
        v85.m128i_i16[1] = v34;
        v85.m128i_i64[1] = RtlpAllocateAtom((unsigned __int16)v34);
        if ( !v85.m128i_i64[1] )
          goto LABEL_130;
      }
      v85.m128i_i16[0] = 0;
      if ( (int)RtlUnicodeStringValidateWorker(&v85) >= 0 )
      {
        v45 = 0;
        v46 = (_WORD *)v85.m128i_i64[1];
        v47 = (unsigned __int64)v40 >> 1;
        for ( i = (unsigned __int64)v85.m128i_u16[1] >> 1; i; --i )
        {
          if ( !v47 )
            break;
          if ( !*v35 )
            break;
          *v46++ = *v35++;
          --v47;
          ++v45;
        }
        v43 = 2 * v45;
        v85.m128i_i16[0] = 2 * v45;
      }
      if ( v41 && v40 != v41 )
      {
        *(_WORD *)(v85.m128i_i64[1] + 2 * ((unsigned __int64)v43 >> 1)) = v44;
        v85.m128i_i16[0] += 2;
      }
      if ( (int)RtlUnicodeStringValidateWorker(&v85) >= 0 && (int)RtlUnicodeStringValidateWorker(a3) >= 0 )
      {
        v50 = (_WORD *)*((_QWORD *)a3 + 1);
        v51 = v49;
        v52 = 0;
        v53 = v51 >> 1;
        v54 = (unsigned __int64)*a3 >> 1;
        v55 = (_WORD *)(v85.m128i_i64[1] + 2 * v53);
        for ( j = ((unsigned __int64)v85.m128i_u16[1] >> 1) - v53; j; --j )
        {
          if ( !v54 )
            break;
          --v54;
          *v55++ = *v50++;
          ++v52;
        }
        v49 = 2 * (v53 + v52);
        v85.m128i_i16[0] = v49;
      }
      v57 = v91;
      if ( v91 && (int)RtlUnicodeStringValidateWorker(&v85) >= 0 && (int)RtlUnicodeStringValidateWorker(v57) >= 0 )
      {
        v58 = v57[1];
        v59 = v49;
        v60 = 0;
        v61 = v59 >> 1;
        v62 = (unsigned __int64)*(unsigned __int16 *)v57 >> 1;
        v63 = (_WORD *)(v85.m128i_i64[1] + 2 * v61);
        for ( k = ((unsigned __int64)v85.m128i_u16[1] >> 1) - v61; k; --k )
        {
          if ( !v62 )
            break;
          --v62;
          *v63++ = *v58++;
          ++v60;
        }
        v49 = 2 * (v61 + v60);
        v85.m128i_i16[0] = v49;
      }
      if ( (unsigned __int64)v49 + 2 > v85.m128i_u16[1] )
      {
LABEL_106:
        FullPathName_Ustr = -1073741595;
        goto LABEL_81;
      }
      *(_OWORD *)v98.m256i_i8 = 0;
      *(_WORD *)(v85.m128i_i64[1] + 2 * ((unsigned __int64)v49 >> 1)) = 0;
      v100 = 0;
      v97 = 0;
      *(_OWORD *)((char *)&v98.m256i_u64[1] + 4) = 0;
      v90 = 0;
      v92 = 0;
      v93 = 0;
      memset(v99, 0, sizeof(v99));
      if ( (int)RtlpDosPathNameToRelativeNtPathName(2, &v85, 0, (unsigned __int16 *)&v90, 0, 0, (__int64)&v92) >= 0 )
      {
        v65 = *((_QWORD *)&v90 + 1);
        if ( (_WORD)v92 )
        {
          v90 = v92;
          v66 = v93;
        }
        else
        {
          v66 = 0;
        }
        *((_QWORD *)&v97 + 1) = v66;
        LODWORD(v97) = 48;
        v98.m256i_i64[0] = (__int64)&v90;
        v98.m256i_i32[2] = 64;
        *(_OWORD *)&v98.m256i_u64[2] = 0;
        v67 = ZwQueryAttributesFile(&v97, v99);
        v68 = *((_QWORD *)&v93 + 1);
        v69 = v67;
        if ( *((_QWORD *)&v93 + 1) && _InterlockedExchangeAdd(*((volatile signed __int32 **)&v93 + 1), 0xFFFFFFFF) == 1 )
        {
          NtClose(*(HANDLE *)(v68 + 8));
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v68);
        }
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v65);
        if ( v69 >= 0 )
        {
          v70 = RtlGetFullPathName_UstrEx(
                  (unsigned int)&v85,
                  v89,
                  v96,
                  (_DWORD)v95,
                  (__int64)v94,
                  0,
                  (__int64)&v86,
                  (__int64)v87);
          FullPathName_Ustr = 0;
          if ( v70 < 0 )
            FullPathName_Ustr = v70;
          goto LABEL_81;
        }
      }
      LOWORD(v34) = (_WORD)v88;
      if ( v37 == v36 )
        v35 = v37;
      else
        v35 = v37 + 1;
    }
    goto LABEL_113;
  }
  v88 = v17;
  v72 = RtlDosApplyFileIsolationRedirection_Ustr(
          1,
          (__int128 *)a3,
          a4,
          v16,
          (_OWORD *)a6,
          (unsigned __int64)&v88,
          v17,
          a8,
          v15);
  FullPathName_Ustr = v72;
  if ( v72 < 0 )
  {
    if ( v72 != -1072365560 )
      goto LABEL_81;
    v17 = 0;
    goto LABEL_24;
  }
  if ( a7 )
    *a7 = v88;
LABEL_86:
  FullPathName_Ustr = 0;
LABEL_81:
  if ( v85.m128i_i64[1] )
  {
    if ( (_BYTE *)v85.m128i_i64[1] != v101 )
      RtlpSysVolFree(v85.m128i_i64[1]);
  }
  return (unsigned int)FullPathName_Ustr;
}

```

## disassembly

```asm
0x18005c960  mov     [rsp-8+arg_0], rbx
0x18005c965  push    rbp
0x18005c966  push    rsi
0x18005c967  push    rdi
0x18005c968  push    r12
0x18005c96a  push    r13
0x18005c96c  push    r14
0x18005c96e  push    r15
0x18005c970  lea     rbp, [rsp-250h]
0x18005c978  sub     rsp, 350h
0x18005c97f  mov     rax, cs:__security_cookie
0x18005c986  xor     rax, rsp
0x18005c989  mov     [rbp+280h+var_40], rax
0x18005c990  mov     r15, [rbp+280h+arg_30]
0x18005c997  lea     rax, [rbp+280h+var_250]
0x18005c99b  mov     r14, [rbp+280h+arg_28]
0x18005c9a2  mov     rsi, r9
0x18005c9a5  mov     r12, [rbp+280h+arg_38]
0x18005c9ac  mov     r13, r8
0x18005c9af  mov     r8, [rbp+280h+arg_40]
0x18005c9b6  xor     r11d, r11d
0x18005c9b9  mov     [rbp+280h+var_2F0], r9
0x18005c9bd  mov     rdi, rdx
0x18005c9c0  mov     r9, [rbp+280h+arg_20]
0x18005c9c7  mov     ebx, ecx
0x18005c9c9  mov     [rsp+380h+var_308], r9
0x18005c9ce  mov     [rsp+380h+var_318], r8
0x18005c9d3  mov     [rbp+280h+var_2B8], r14
0x18005c9d7  mov     [rbp+280h+var_2C0], r15
0x18005c9db  mov     [rbp+280h+var_2C8], r12
0x18005c9df  mov     [rsp+380h+var_330], 2080000h
0x18005c9e8  mov     [rsp+380h+var_328], rax
0x18005c9ed  test    r15, r15
0x18005c9f0  jz      short loc_18005C9F5
0x18005c9f2  mov     [r15], r11
0x18005c9f5  test    r8, r8
0x18005c9f8  jz      short loc_18005C9FD
0x18005c9fa  mov     [r8], r11
0x18005c9fd  test    r12, r12
0x18005ca00  jz      short loc_18005CA06
0x18005ca02  mov     [r12], r11
0x18005ca06  test    r14, r14
0x18005ca09  jz      short loc_18005CA12
0x18005ca0b  mov     [r14], r11d
0x18005ca0e  mov     [r14+8], r11
0x18005ca12  test    ebx, 0FFFFFFF8h
0x18005ca18  jnz     loc_18005D06E
0x18005ca1e  test    rdi, rdi
0x18005ca21  jz      loc_18005D06E
0x18005ca27  test    r13, r13
0x18005ca2a  jz      loc_18005D06E
0x18005ca30  test    r9, r9
0x18005ca33  jz      short loc_18005CA43
0x18005ca35  test    r14, r14
0x18005ca38  jz      short loc_18005CA43
0x18005ca3a  test    r15, r15
0x18005ca3d  jz      loc_18005D06E
0x18005ca43  mov     rcx, r13
0x18005ca46  call    RtlDetermineDosPathNameType_Ustr
0x18005ca4b  mov     [rsp+380h+var_320], eax
0x18005ca4f  test    bl, 2
0x18005ca52  jz      short loc_18005CAC8
0x18005ca54  cmp     eax, 5
0x18005ca57  jz      short loc_18005CAAF
0x18005ca59  mov     dl, 1
0x18005ca5b  mov     rcx, r13
0x18005ca5e  call    RtlDoesFileExists_UstrEx
0x18005ca63  test    al, al
0x18005ca65  jz      loc_18005D082
0x18005ca6b  mov     rax, [rsp+380h+var_318]
0x18005ca70  mov     r9, r15
0x18005ca73  mov     rdx, [rsp+380h+var_308]
0x18005ca78  mov     r8, r14
0x18005ca7b  mov     [rsp+380h+var_348], rax
0x18005ca80  mov     rcx, r13
0x18005ca83  lea     rax, [rsp+380h+var_320]
0x18005ca88  mov     [rsp+380h+var_350], rax
0x18005ca8d  mov     [rsp+380h+var_358], 0
0x18005ca96  mov     [rsp+380h+var_360], r12
0x18005ca9b  call    RtlGetFullPathName_UstrEx
0x18005caa0  mov     ebx, eax
0x18005caa2  test    eax, eax
0x18005caa4  jns     loc_18005CF57
0x18005caaa  jmp     loc_18005CED2
0x18005caaf  movzx   edx, word ptr [r13+0]
0x18005cab4  cmp     dx, 4
0x18005cab8  jb      short loc_18005CAC8
0x18005caba  mov     rcx, [r13+8]
0x18005cabe  cmp     word ptr [rcx], 2Eh ; '.'
0x18005cac2  jz      loc_18005D14F
0x18005cac8  cmp     eax, 5
0x18005cacb  jnz     short loc_18005CA59
0x18005cacd  test    bl, 1
0x18005cad0  jnz     loc_18005CF0D
0x18005cad6  mov     r10, r11
0x18005cad9  mov     ebx, r11d
0x18005cadc  test    rsi, rsi
0x18005cadf  jz      short loc_18005CB26
0x18005cae1  movzx   eax, word ptr [r13+0]
0x18005cae6  movzx   ebx, word ptr [rsi]
0x18005cae9  test    ax, ax
0x18005caec  jz      short loc_18005CB26
0x18005caee  mov     rdx, [r13+8]
0x18005caf2  shr     rax, 1
0x18005caf5  lea     rcx, [rdx+rax*2]
0x18005caf9  nop     dword ptr [rax+00000000h]
0x18005cb00  cmp     rcx, rdx
0x18005cb03  jbe     short loc_18005CB26
0x18005cb05  movzx   eax, word ptr [rcx-2]
0x18005cb09  sub     rcx, 2
0x18005cb0d  cmp     ax, 5Ch ; '\'
0x18005cb11  jz      short loc_18005CB26
0x18005cb13  cmp     ax, 2Fh ; '/'
0x18005cb17  jz      short loc_18005CB26
0x18005cb19  cmp     ax, 2Eh ; '.'
0x18005cb1d  jnz     short loc_18005CB00
0x18005cb1f  mov     [rbp+280h+var_2F0], r11
0x18005cb23  mov     ebx, r11d
0x18005cb26  movzx   ecx, word ptr [rdi]
0x18005cb29  mov     eax, ecx
0x18005cb2b  shr     rax, 1
0x18005cb2e  lea     r11, [rax+rax]
0x18005cb32  test    cx, cx
0x18005cb35  jz      short loc_18005CB96
0x18005cb37  mov     rdx, [rdi+8]
0x18005cb3b  lea     r9, [rdx+r11]
0x18005cb3f  mov     rax, r9
0x18005cb42  cmp     r9, rdx
0x18005cb45  jbe     short loc_18005CB67
0x18005cb47  nop     word ptr [rax+rax+00000000h]
0x18005cb50  cmp     word ptr [rax-2], 3Bh ; ';'
0x18005cb55  lea     rcx, [rax-2]
0x18005cb59  jz      loc_18005CF9A
0x18005cb5f  mov     rax, rcx
0x18005cb62  cmp     rcx, rdx
0x18005cb65  ja      short loc_18005CB50
0x18005cb67  mov     rcx, r9
0x18005cb6a  sub     rcx, rax
0x18005cb6d  sar     rcx, 1
0x18005cb70  test    cx, cx
0x18005cb73  jz      short loc_18005CB89
0x18005cb75  movzx   eax, word ptr [r9-2]
0x18005cb7a  cmp     ax, 5Ch ; '\'
0x18005cb7e  jz      short loc_18005CB89
0x18005cb80  cmp     ax, 2Fh ; '/'
0x18005cb84  jz      short loc_18005CB89
0x18005cb86  inc     cx
0x18005cb89  movzx   eax, cx
0x18005cb8c  cmp     rax, r10
0x18005cb8f  cmova   r10, rax
0x18005cb93  add     r10, r10
0x18005cb96  movzx   eax, word ptr [r13+0]
0x18005cb9b  lea     r8, [r10+2]
0x18005cb9f  movzx   r12d, bx
0x18005cba3  add     rax, r12
0x18005cba6  add     r8, rax
0x18005cba9  mov     [rsp+380h+var_310], r8
0x18005cbae  cmp     r8, 0FFFEh
0x18005cbb5  ja      loc_18005D29D
0x18005cbbb  mov     rbx, [rdi+8]
0x18005cbbf  lea     r15, [r11+rbx]
0x18005cbc3  mov     r11d, 5Ch ; '\'
0x18005cbc9  nop     dword ptr [rax+00000000h]
0x18005cbd0  cmp     rbx, r15
0x18005cbd3  jnb     loc_18005D132
0x18005cbd9  mov     r14, rbx
0x18005cbdc  nop     dword ptr [rax+00h]
0x18005cbe0  cmp     word ptr [r14], 3Bh ; ';'
0x18005cbe5  jz      short loc_18005CBF0
0x18005cbe7  add     r14, 2
0x18005cbeb  cmp     r14, r15
0x18005cbee  jnz     short loc_18005CBE0
0x18005cbf0  mov     rdi, r14
0x18005cbf3  sub     rdi, rbx
0x18005cbf6  sar     rdi, 1
0x18005cbf9  add     di, di
0x18005cbfc  movzx   esi, di
0x18005cbff  jnz     loc_18005CFE1
0x18005cc05  movzx   eax, word ptr [r13+0]
0x18005cc0a  add     rax, r12
0x18005cc0d  movzx   edx, si
0x18005cc10  add     rdx, rax
0x18005cc13  movzx   eax, word ptr [rsp+380h+var_330+2]
0x18005cc18  lea     rcx, [rdx+2]
0x18005cc1c  cmp     rax, rcx
0x18005cc1f  jb      loc_18005D199
0x18005cc25  xor     r10d, r10d
0x18005cc28  lea     rcx, [rsp+380h+var_330]
0x18005cc2d  mov     word ptr [rsp+380h+var_330], r10w
0x18005cc33  call    RtlUnicodeStringValidateWorker
0x18005cc38  test    eax, eax
0x18005cc3a  js      short loc_18005CC87
0x18005cc3c  movzx   edx, word ptr [rsp+380h+var_330+2]
0x18005cc41  xor     r9d, r9d
0x18005cc44  mov     r8, [rsp+380h+var_328]
0x18005cc49  movzx   ecx, di
0x18005cc4c  shr     rcx, 1
0x18005cc4f  shr     rdx, 1
0x18005cc52  jz      short loc_18005CC79
0x18005cc54  test    rcx, rcx
0x18005cc57  jz      short loc_18005CC79
0x18005cc59  movzx   eax, word ptr [rbx]
0x18005cc5c  test    ax, ax
0x18005cc5f  jz      short loc_18005CC79
0x18005cc61  mov     [r8], ax
0x18005cc65  add     rbx, 2
0x18005cc69  add     r8, 2
0x18005cc6d  dec     rcx
0x18005cc70  inc     r9
0x18005cc73  sub     rdx, 1
0x18005cc77  jnz     short loc_18005CC54
0x18005cc79  add     r9w, r9w
0x18005cc7d  movzx   r10d, r9w
0x18005cc81  mov     word ptr [rsp+380h+var_330], r9w
0x18005cc87  test    si, si
0x18005cc8a  jnz     loc_18005D002
0x18005cc90  lea     rcx, [rsp+380h+var_330]
0x18005cc95  call    RtlUnicodeStringValidateWorker
0x18005cc9a  test    eax, eax
0x18005cc9c  js      short loc_18005CD0F
0x18005cc9e  mov     rcx, r13
0x18005cca1  call    RtlUnicodeStringValidateWorker
0x18005cca6  test    eax, eax
0x18005cca8  js      short loc_18005CD0F
0x18005ccaa  mov     rax, [rsp+380h+var_328]
0x18005ccaf  movzx   ecx, word ptr [r13+0]
0x18005ccb4  movzx   edx, word ptr [rsp+380h+var_330+2]
0x18005ccb9  mov     r8, [r13+8]
0x18005ccbd  movzx   r11d, r10w
0x18005ccc1  mov     r10d, 0
0x18005ccc7  shr     r11, 1
0x18005ccca  shr     rcx, 1
0x18005cccd  shr     rdx, 1
0x18005ccd0  lea     r9, [rax+r11*2]
0x18005ccd4  sub     rdx, r11
0x18005ccd7  jz      short loc_18005CD01
0x18005ccd9  nop     dword ptr [rax+00000000h]
0x18005cce0  test    rcx, rcx
0x18005cce3  jz      short loc_18005CD01
0x18005cce5  movzx   eax, word ptr [r8]
0x18005cce9  dec     rcx
0x18005ccec  mov     [r9], ax
0x18005ccf0  add     r8, 2
0x18005ccf4  add     r9, 2
0x18005ccf8  inc     r10
0x18005ccfb  sub     rdx, 1
0x18005ccff  jnz     short loc_18005CCE0
0x18005cd01  add     r10w, r11w
0x18005cd05  add     r10w, r10w
0x18005cd09  mov     word ptr [rsp+380h+var_330], r10w
0x18005cd0f  mov     rsi, [rbp+280h+var_2F0]
0x18005cd13  test    rsi, rsi
0x18005cd16  jz      short loc_18005CD8F
0x18005cd18  lea     rcx, [rsp+380h+var_330]
0x18005cd1d  call    RtlUnicodeStringValidateWorker
0x18005cd22  test    eax, eax
0x18005cd24  js      short loc_18005CD8F
0x18005cd26  mov     rcx, rsi
0x18005cd29  call    RtlUnicodeStringValidateWorker
0x18005cd2e  test    eax, eax
0x18005cd30  js      short loc_18005CD8F
0x18005cd32  mov     rcx, [rsp+380h+var_328]
0x18005cd37  movzx   eax, word ptr [rsi]
0x18005cd3a  movzx   edx, word ptr [rsp+380h+var_330+2]
0x18005cd3f  mov     r8, [rsi+8]
0x18005cd43  movzx   r11d, r10w
0x18005cd47  mov     r10d, 0
0x18005cd4d  shr     r11, 1
0x18005cd50  shr     rax, 1
0x18005cd53  shr     rdx, 1
0x18005cd56  lea     r9, [rcx+r11*2]
0x18005cd5a  sub     rdx, r11
0x18005cd5d  jz      short loc_18005CD81
0x18005cd5f  nop
0x18005cd60  test    rax, rax
0x18005cd63  jz      short loc_18005CD81
0x18005cd65  movzx   ecx, word ptr [r8]
0x18005cd69  dec     rax
0x18005cd6c  mov     [r9], cx
0x18005cd70  add     r8, 2
0x18005cd74  add     r9, 2
0x18005cd78  inc     r10
0x18005cd7b  sub     rdx, 1
0x18005cd7f  jnz     short loc_18005CD60
0x18005cd81  add     r10w, r11w
0x18005cd85  add     r10w, r10w
0x18005cd89  mov     word ptr [rsp+380h+var_330], r10w
0x18005cd8f  movzx   eax, word ptr [rsp+380h+var_330+2]
0x18005cd94  movzx   edx, r10w
0x18005cd98  lea     rcx, [rdx+2]
0x18005cd9c  cmp     rcx, rax
0x18005cd9f  ja      loc_18005D078
0x18005cda5  mov     rax, [rsp+380h+var_328]
0x18005cdaa  lea     r9, [rbp+280h+var_300]
0x18005cdae  xorps   xmm0, xmm0
0x18005cdb1  shr     rdx, 1
0x18005cdb4  xor     ecx, ecx
0x18005cdb6  xorps   xmm1, xmm1
0x18005cdb9  movups  [rbp+280h+var_2A0], xmm0
0x18005cdbd  xor     r8d, r8d
  ... truncated ...
```
