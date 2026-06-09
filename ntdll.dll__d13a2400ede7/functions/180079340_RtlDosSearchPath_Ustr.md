# RtlDosSearchPath_Ustr

- ea: `0x180079340`
- end: `0x180079c91`
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
- `0x180021fd0`
- `0x180079340`
- `0x180079ca0`
- `0x180079cf0`
- `0x18007a040`
- `0x18007a110`
- `0x18015ecc0`
- `0x18015f280`
- `0x180162810`
- `0x180164280`

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
0x180079340  mov     [rsp-8+arg_0], rbx
0x180079345  push    rbp
0x180079346  push    rsi
0x180079347  push    rdi
0x180079348  push    r12
0x18007934a  push    r13
0x18007934c  push    r14
0x18007934e  push    r15
0x180079350  lea     rbp, [rsp-250h]
0x180079358  sub     rsp, 350h
0x18007935f  mov     rax, cs:__security_cookie
0x180079366  xor     rax, rsp
0x180079369  mov     [rbp+280h+var_40], rax
0x180079370  mov     r15, [rbp+280h+arg_30]
0x180079377  lea     rax, [rbp+280h+var_250]
0x18007937b  mov     r14, [rbp+280h+arg_28]
0x180079382  mov     rsi, r9
0x180079385  mov     r12, [rbp+280h+arg_38]
0x18007938c  mov     r13, r8
0x18007938f  mov     r8, [rbp+280h+arg_40]
0x180079396  xor     r11d, r11d
0x180079399  mov     [rbp+280h+var_2F0], r9
0x18007939d  mov     rdi, rdx
0x1800793a0  mov     r9, [rbp+280h+arg_20]
0x1800793a7  mov     ebx, ecx
0x1800793a9  mov     [rsp+380h+var_308], r9
0x1800793ae  mov     [rsp+380h+var_318], r8
0x1800793b3  mov     [rbp+280h+var_2B8], r14
0x1800793b7  mov     [rbp+280h+var_2C0], r15
0x1800793bb  mov     [rbp+280h+var_2C8], r12
0x1800793bf  mov     [rsp+380h+var_330], 2080000h
0x1800793c8  mov     [rsp+380h+var_328], rax
0x1800793cd  test    r15, r15
0x1800793d0  jz      short loc_1800793D5
0x1800793d2  mov     [r15], r11
0x1800793d5  test    r8, r8
0x1800793d8  jz      short loc_1800793DD
0x1800793da  mov     [r8], r11
0x1800793dd  test    r12, r12
0x1800793e0  jz      short loc_1800793E6
0x1800793e2  mov     [r12], r11
0x1800793e6  test    r14, r14
0x1800793e9  jz      short loc_1800793F2
0x1800793eb  mov     [r14], r11d
0x1800793ee  mov     [r14+8], r11
0x1800793f2  test    ebx, 0FFFFFFF8h
0x1800793f8  jnz     loc_180079A4E
0x1800793fe  test    rdi, rdi
0x180079401  jz      loc_180079A4E
0x180079407  test    r13, r13
0x18007940a  jz      loc_180079A4E
0x180079410  test    r9, r9
0x180079413  jz      short loc_180079423
0x180079415  test    r14, r14
0x180079418  jz      short loc_180079423
0x18007941a  test    r15, r15
0x18007941d  jz      loc_180079A4E
0x180079423  mov     rcx, r13
0x180079426  call    RtlDetermineDosPathNameType_Ustr
0x18007942b  mov     [rsp+380h+var_320], eax
0x18007942f  test    bl, 2
0x180079432  jz      short loc_1800794A8
0x180079434  cmp     eax, 5
0x180079437  jz      short loc_18007948F
0x180079439  mov     dl, 1
0x18007943b  mov     rcx, r13
0x18007943e  call    RtlDoesFileExists_UstrEx
0x180079443  test    al, al
0x180079445  jz      loc_180079A62
0x18007944b  mov     rax, [rsp+380h+var_318]
0x180079450  mov     r9, r15
0x180079453  mov     rdx, [rsp+380h+var_308]
0x180079458  mov     r8, r14
0x18007945b  mov     [rsp+380h+var_348], rax
0x180079460  mov     rcx, r13
0x180079463  lea     rax, [rsp+380h+var_320]
0x180079468  mov     [rsp+380h+var_350], rax
0x18007946d  mov     [rsp+380h+var_358], 0
0x180079476  mov     [rsp+380h+var_360], r12
0x18007947b  call    RtlGetFullPathName_UstrEx
0x180079480  mov     ebx, eax
0x180079482  test    eax, eax
0x180079484  jns     loc_180079937
0x18007948a  jmp     loc_1800798B2
0x18007948f  movzx   edx, word ptr [r13+0]
0x180079494  cmp     dx, 4
0x180079498  jb      short loc_1800794A8
0x18007949a  mov     rcx, [r13+8]
0x18007949e  cmp     word ptr [rcx], 2Eh ; '.'
0x1800794a2  jz      loc_180079B2F
0x1800794a8  cmp     eax, 5
0x1800794ab  jnz     short loc_180079439
0x1800794ad  test    bl, 1
0x1800794b0  jnz     loc_1800798ED
0x1800794b6  mov     r10, r11
0x1800794b9  mov     ebx, r11d
0x1800794bc  test    rsi, rsi
0x1800794bf  jz      short loc_180079506
0x1800794c1  movzx   eax, word ptr [r13+0]
0x1800794c6  movzx   ebx, word ptr [rsi]
0x1800794c9  test    ax, ax
0x1800794cc  jz      short loc_180079506
0x1800794ce  mov     rdx, [r13+8]
0x1800794d2  shr     rax, 1
0x1800794d5  lea     rcx, [rdx+rax*2]
0x1800794d9  nop     dword ptr [rax+00000000h]
0x1800794e0  cmp     rcx, rdx
0x1800794e3  jbe     short loc_180079506
0x1800794e5  movzx   eax, word ptr [rcx-2]
0x1800794e9  sub     rcx, 2
0x1800794ed  cmp     ax, 5Ch ; '\'
0x1800794f1  jz      short loc_180079506
0x1800794f3  cmp     ax, 2Fh ; '/'
0x1800794f7  jz      short loc_180079506
0x1800794f9  cmp     ax, 2Eh ; '.'
0x1800794fd  jnz     short loc_1800794E0
0x1800794ff  mov     [rbp+280h+var_2F0], r11
0x180079503  mov     ebx, r11d
0x180079506  movzx   ecx, word ptr [rdi]
0x180079509  mov     eax, ecx
0x18007950b  shr     rax, 1
0x18007950e  lea     r11, [rax+rax]
0x180079512  test    cx, cx
0x180079515  jz      short loc_180079576
0x180079517  mov     rdx, [rdi+8]
0x18007951b  lea     r9, [rdx+r11]
0x18007951f  mov     rax, r9
0x180079522  cmp     r9, rdx
0x180079525  jbe     short loc_180079547
0x180079527  nop     word ptr [rax+rax+00000000h]
0x180079530  cmp     word ptr [rax-2], 3Bh ; ';'
0x180079535  lea     rcx, [rax-2]
0x180079539  jz      loc_18007997A
0x18007953f  mov     rax, rcx
0x180079542  cmp     rcx, rdx
0x180079545  ja      short loc_180079530
0x180079547  mov     rcx, r9
0x18007954a  sub     rcx, rax
0x18007954d  sar     rcx, 1
0x180079550  test    cx, cx
0x180079553  jz      short loc_180079569
0x180079555  movzx   eax, word ptr [r9-2]
0x18007955a  cmp     ax, 5Ch ; '\'
0x18007955e  jz      short loc_180079569
0x180079560  cmp     ax, 2Fh ; '/'
0x180079564  jz      short loc_180079569
0x180079566  inc     cx
0x180079569  movzx   eax, cx
0x18007956c  cmp     rax, r10
0x18007956f  cmova   r10, rax
0x180079573  add     r10, r10
0x180079576  movzx   eax, word ptr [r13+0]
0x18007957b  lea     r8, [r10+2]
0x18007957f  movzx   r12d, bx
0x180079583  add     rax, r12
0x180079586  add     r8, rax
0x180079589  mov     [rsp+380h+var_310], r8
0x18007958e  cmp     r8, 0FFFEh
0x180079595  ja      loc_180079C7D
0x18007959b  mov     rbx, [rdi+8]
0x18007959f  lea     r15, [r11+rbx]
0x1800795a3  mov     r11d, 5Ch ; '\'
0x1800795a9  nop     dword ptr [rax+00000000h]
0x1800795b0  cmp     rbx, r15
0x1800795b3  jnb     loc_180079B12
0x1800795b9  mov     r14, rbx
0x1800795bc  nop     dword ptr [rax+00h]
0x1800795c0  cmp     word ptr [r14], 3Bh ; ';'
0x1800795c5  jz      short loc_1800795D0
0x1800795c7  add     r14, 2
0x1800795cb  cmp     r14, r15
0x1800795ce  jnz     short loc_1800795C0
0x1800795d0  mov     rdi, r14
0x1800795d3  sub     rdi, rbx
0x1800795d6  sar     rdi, 1
0x1800795d9  add     di, di
0x1800795dc  movzx   esi, di
0x1800795df  jnz     loc_1800799C1
0x1800795e5  movzx   eax, word ptr [r13+0]
0x1800795ea  add     rax, r12
0x1800795ed  movzx   edx, si
0x1800795f0  add     rdx, rax
0x1800795f3  movzx   eax, word ptr [rsp+380h+var_330+2]
0x1800795f8  lea     rcx, [rdx+2]
0x1800795fc  cmp     rax, rcx
0x1800795ff  jb      loc_180079B79
0x180079605  xor     r10d, r10d
0x180079608  lea     rcx, [rsp+380h+var_330]
0x18007960d  mov     word ptr [rsp+380h+var_330], r10w
0x180079613  call    RtlUnicodeStringValidateWorker
0x180079618  test    eax, eax
0x18007961a  js      short loc_180079667
0x18007961c  movzx   edx, word ptr [rsp+380h+var_330+2]
0x180079621  xor     r9d, r9d
0x180079624  mov     r8, [rsp+380h+var_328]
0x180079629  movzx   ecx, di
0x18007962c  shr     rcx, 1
0x18007962f  shr     rdx, 1
0x180079632  jz      short loc_180079659
0x180079634  test    rcx, rcx
0x180079637  jz      short loc_180079659
0x180079639  movzx   eax, word ptr [rbx]
0x18007963c  test    ax, ax
0x18007963f  jz      short loc_180079659
0x180079641  mov     [r8], ax
0x180079645  add     rbx, 2
0x180079649  add     r8, 2
0x18007964d  dec     rcx
0x180079650  inc     r9
0x180079653  sub     rdx, 1
0x180079657  jnz     short loc_180079634
0x180079659  add     r9w, r9w
0x18007965d  movzx   r10d, r9w
0x180079661  mov     word ptr [rsp+380h+var_330], r9w
0x180079667  test    si, si
0x18007966a  jnz     loc_1800799E2
0x180079670  lea     rcx, [rsp+380h+var_330]
0x180079675  call    RtlUnicodeStringValidateWorker
0x18007967a  test    eax, eax
0x18007967c  js      short loc_1800796EF
0x18007967e  mov     rcx, r13
0x180079681  call    RtlUnicodeStringValidateWorker
0x180079686  test    eax, eax
0x180079688  js      short loc_1800796EF
0x18007968a  mov     rax, [rsp+380h+var_328]
0x18007968f  movzx   ecx, word ptr [r13+0]
0x180079694  movzx   edx, word ptr [rsp+380h+var_330+2]
0x180079699  mov     r8, [r13+8]
0x18007969d  movzx   r11d, r10w
0x1800796a1  mov     r10d, 0
0x1800796a7  shr     r11, 1
0x1800796aa  shr     rcx, 1
0x1800796ad  shr     rdx, 1
0x1800796b0  lea     r9, [rax+r11*2]
0x1800796b4  sub     rdx, r11
0x1800796b7  jz      short loc_1800796E1
0x1800796b9  nop     dword ptr [rax+00000000h]
0x1800796c0  test    rcx, rcx
0x1800796c3  jz      short loc_1800796E1
0x1800796c5  movzx   eax, word ptr [r8]
0x1800796c9  dec     rcx
0x1800796cc  mov     [r9], ax
0x1800796d0  add     r8, 2
0x1800796d4  add     r9, 2
0x1800796d8  inc     r10
0x1800796db  sub     rdx, 1
0x1800796df  jnz     short loc_1800796C0
0x1800796e1  add     r10w, r11w
0x1800796e5  add     r10w, r10w
0x1800796e9  mov     word ptr [rsp+380h+var_330], r10w
0x1800796ef  mov     rsi, [rbp+280h+var_2F0]
0x1800796f3  test    rsi, rsi
0x1800796f6  jz      short loc_18007976F
0x1800796f8  lea     rcx, [rsp+380h+var_330]
0x1800796fd  call    RtlUnicodeStringValidateWorker
0x180079702  test    eax, eax
0x180079704  js      short loc_18007976F
0x180079706  mov     rcx, rsi
0x180079709  call    RtlUnicodeStringValidateWorker
0x18007970e  test    eax, eax
0x180079710  js      short loc_18007976F
0x180079712  mov     rcx, [rsp+380h+var_328]
0x180079717  movzx   eax, word ptr [rsi]
0x18007971a  movzx   edx, word ptr [rsp+380h+var_330+2]
0x18007971f  mov     r8, [rsi+8]
0x180079723  movzx   r11d, r10w
0x180079727  mov     r10d, 0
0x18007972d  shr     r11, 1
0x180079730  shr     rax, 1
0x180079733  shr     rdx, 1
0x180079736  lea     r9, [rcx+r11*2]
0x18007973a  sub     rdx, r11
0x18007973d  jz      short loc_180079761
0x18007973f  nop
0x180079740  test    rax, rax
0x180079743  jz      short loc_180079761
0x180079745  movzx   ecx, word ptr [r8]
0x180079749  dec     rax
0x18007974c  mov     [r9], cx
0x180079750  add     r8, 2
0x180079754  add     r9, 2
0x180079758  inc     r10
0x18007975b  sub     rdx, 1
0x18007975f  jnz     short loc_180079740
0x180079761  add     r10w, r11w
0x180079765  add     r10w, r10w
0x180079769  mov     word ptr [rsp+380h+var_330], r10w
0x18007976f  movzx   eax, word ptr [rsp+380h+var_330+2]
0x180079774  movzx   edx, r10w
0x180079778  lea     rcx, [rdx+2]
0x18007977c  cmp     rcx, rax
0x18007977f  ja      loc_180079A58
0x180079785  mov     rax, [rsp+380h+var_328]
0x18007978a  lea     r9, [rbp+280h+var_300]
0x18007978e  xorps   xmm0, xmm0
0x180079791  shr     rdx, 1
0x180079794  xor     ecx, ecx
0x180079796  xorps   xmm1, xmm1
0x180079799  movups  [rbp+280h+var_2A0], xmm0
0x18007979d  xor     r8d, r8d
  ... truncated ...
```
