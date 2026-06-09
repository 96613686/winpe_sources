# PerflibciEnsurePerflibV2StringTable(ulong,ushort,uchar * *,ulong *)

- ea: `0x180003b40`
- end: `0x180004495`
- name: `?PerflibciEnsurePerflibV2StringTable@@YAKKGPEAPEAEPEAK@Z`
- size: `2389`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting`

## callers

- `0x180010430`

## callees

- `0x180003b40`
- `0x1800044a0`
- `0x180005da0`
- `0x1800069b0`
- `0x180006bc0`
- `0x1800070d0`
- `0x180007104`
- `0x180007120`
- `0x1800072d0`
- `0x180007300`
- `0x180007320`
- `0x180008042`
- `0x180008050`
- `0x18000805c`
- `0x180008080`
- `0x18000aaa0`
- `0x18000bbec`
- `0x1800102c0`
- `0x180015890`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180003d3b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180003d89`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180003d3b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180003d89`

## pseudocode

```c
__int64 __fastcall PerflibciEnsurePerflibV2StringTable(
        unsigned int a1,
        __int16 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int16 v5; // si
  unsigned int *v6; // r13
  DWORD v7; // edi
  _QWORD *v8; // r15
  __int16 v9; // r12
  __int64 v10; // rsi
  unsigned __int8 *v11; // rax
  char v12; // al
  size_t v13; // r14
  char *v14; // rbx
  char *v15; // rdi
  char v16; // bl
  char *v17; // rax
  int ThreadPreferredUILanguages; // eax
  void *v19; // rax
  __int64 v20; // r15
  unsigned int v21; // eax
  unsigned int v22; // edi
  enum _PerfRegInfoType v23; // ebx
  const struct _GUID *v24; // r12
  __int16 v25; // r15
  unsigned int v26; // esi
  unsigned int v27; // eax
  unsigned int v28; // r13d
  const unsigned __int16 *v29; // rdi
  unsigned int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rax
  bool v33; // zf
  unsigned int v34; // edx
  char *v35; // rdi
  char *v36; // rsi
  __int64 v37; // r15
  unsigned int v38; // r13d
  char v39; // bl
  __int64 v40; // rax
  int v41; // edx
  unsigned int v42; // edi
  unsigned int v43; // edi
  unsigned __int16 *v44; // rdi
  unsigned __int64 v45; // rdx
  unsigned int v46; // esi
  __int64 v47; // rax
  int v48; // edi
  __int64 v49; // r11
  __int64 v50; // rax
  int v51; // ecx
  bool v52; // al
  unsigned int v53; // r12d
  enum _PerfRegInfoType v54; // r14d
  unsigned __int8 *v55; // rcx
  unsigned int v56; // edi
  unsigned int v57; // eax
  unsigned int v58; // edx
  char *v59; // rdi
  char *v60; // rsi
  int v61; // eax
  __int64 v62; // rsi
  __int64 v63; // rcx
  const wchar_t *v64; // rdi
  __int64 v65; // rax
  __int64 v66; // r15
  unsigned int v67; // r13d
  unsigned __int8 *v68; // rcx
  unsigned int v69; // r8d
  unsigned __int8 *v70; // rbx
  const wchar_t *v71; // rcx
  size_t v72; // r8
  __int64 v73; // rax
  int v74; // ebx
  size_t v75; // rdx
  size_t *v76; // r8
  wchar_t *v77; // r11
  __int64 v78; // rax
  unsigned __int8 *v79; // rcx
  size_t cchToCopy; // [rsp+28h] [rbp-79h]
  bool v82; // [rsp+48h] [rbp-59h]
  DWORD v83; // [rsp+4Ch] [rbp-55h]
  int v84; // [rsp+4Ch] [rbp-55h]
  __int16 v85; // [rsp+50h] [rbp-51h]
  unsigned int v86; // [rsp+54h] [rbp-4Dh] BYREF
  unsigned int Size; // [rsp+58h] [rbp-49h]
  unsigned int Size_4; // [rsp+5Ch] [rbp-45h]
  unsigned __int8 *Src; // [rsp+60h] [rbp-41h]
  size_t v90; // [rsp+68h] [rbp-39h] BYREF
  void *v91; // [rsp+70h] [rbp-31h]
  char *v92; // [rsp+78h] [rbp-29h]
  unsigned int v93; // [rsp+80h] [rbp-21h] BYREF
  int v94; // [rsp+84h] [rbp-1Dh]
  __int64 v95; // [rsp+88h] [rbp-19h]
  int v96; // [rsp+90h] [rbp-11h] BYREF
  unsigned int v97; // [rsp+94h] [rbp-Dh]
  void *Block; // [rsp+98h] [rbp-9h]
  _QWORD *v99; // [rsp+A0h] [rbp-1h]
  __int64 v100; // [rsp+A8h] [rbp+7h]
  unsigned int LangIdFromSzLang; // [rsp+108h] [rbp+67h]
  char v102; // [rsp+110h] [rbp+6Fh]

  LangIdFromSzLang = a1;
  v5 = a1;
  v6 = a4;
  v82 = ((a2 - 72) & 0xFFDF) == 0;
  utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(&v90);
  v86 = 0;
  v96 = 0;
  v93 = 0;
  Block = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids);
  if ( !a3 || !v6 )
  {
    v7 = 87;
    goto LABEL_142;
  }
  *a3 = 0;
  *v6 = 0;
  v7 = PerflibciEnsureCounterSetList();
  if ( !v7 )
  {
    v7 = PerflibciLocalWaitForMutex(g_hGlobalMutex);
    if ( v7 )
    {
      v79 = 0;
      goto LABEL_140;
    }
    v8 = g_ObjectList;
    Size = 0;
    v9 = v5 & 0x3FF;
    v94 = 0;
    v85 = v5 & 0x3FF;
    LODWORD(v10) = 0;
    v95 = 4096;
    v99 = g_ObjectList;
    v11 = (unsigned __int8 *)operator new(0x1000u, (const struct std::nothrow_t *)&std::nothrow);
    Src = v11;
    if ( v11 )
    {
      memset_0(v11, 0, 0x1000u);
      v12 = utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&v90, 4096);
      v13 = v90;
      if ( !v12 )
        v7 = 14;
      v102 = v12;
      v83 = v7;
      v14 = &v92[-v90];
      v15 = (char *)v91 - v90;
      if ( &v92[-v90] <= (char *)v91 - v90 )
      {
        v7 = v83;
        v16 = v12;
        v91 = v92;
LABEL_19:
        if ( v9 == 9 )
        {
          ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v96, 0, &v93);
          if ( ThreadPreferredUILanguages == -1073741789 || !ThreadPreferredUILanguages )
          {
            if ( v93 )
            {
              v19 = (void *)operator new(saturated_mul(v93, 2u));
              Block = v19;
              if ( v19 )
                RtlGetThreadPreferredUILanguages(36, &v96, v19, &v93);
            }
          }
        }
        if ( !v16 )
          goto LABEL_135;
        while ( 1 )
        {
          if ( !v8 )
            goto LABEL_134;
          v20 = v8[4];
          v100 = v20;
          if ( v20 )
            break;
LABEL_106:
          v8 = (_QWORD *)v99[3];
          v99 = v8;
          if ( !v16 )
            goto LABEL_134;
        }
        v21 = *(_DWORD *)(v20 + 92);
        v97 = v10;
        v22 = v21 + 1;
        if ( !v82 )
          v22 = v21;
        Size_4 = v22;
        if ( v9 == 9 )
        {
          v23 = PERF_REG_COUNTERSET_HELP_STRING;
          if ( !v82 )
            v23 = PERF_REG_COUNTERSET_ENGLISH_NAME;
        }
        else
        {
          v23 = v82 + 3;
        }
        v24 = (const struct _GUID *)(v20 + 24);
        v25 = v85;
        while ( 1 )
        {
          v26 = (_DWORD)v91 - v13;
          v27 = PerflibciLocalQueryCounterSetRegInfoEx(
                  0,
                  v24,
                  v23,
                  LangIdFromSzLang,
                  (unsigned __int8 *)v13,
                  (_DWORD)v91 - v13,
                  &v86);
          v84 = v27;
          v28 = v27;
          if ( (v27 == 15100 || v27 == 15105) && v25 == 9 )
          {
            if ( Block )
            {
              v29 = (const unsigned __int16 *)Block;
              if ( *(_WORD *)Block )
              {
                do
                {
                  LangIdFromSzLang = GetLangIdFromSzLang(v29);
                  v30 = PerflibciLocalQueryCounterSetRegInfoEx(
                          0,
                          v24,
                          v23,
                          LangIdFromSzLang,
                          (unsigned __int8 *)v13,
                          v26,
                          &v86);
                  v84 = v30;
                  v28 = v30;
                  if ( v30 != 15100 && v30 != 15105 )
                    break;
                  v31 = -1;
                  do
                    ++v31;
                  while ( v29[v31] );
                  v32 = (unsigned int)(v31 + 1);
                  v33 = v29[v32] == 0;
                  v29 += v32;
                }
                while ( !v33 );
                v25 = v85;
              }
            }
          }
          if ( !v28 )
            goto LABEL_51;
          if ( v28 != 8 )
            break;
LABEL_53:
          if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                   &v90,
                                   (v86 + 7) & 0xFFFFFFF8) )
          {
            v28 = 14;
            v102 = 0;
            v84 = 14;
          }
          v13 = v90;
          v35 = &v92[-v90];
          v36 = (char *)v91 - v90;
          if ( &v92[-v90] > (char *)v91 - v90 )
          {
            if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&v90, v35) )
            {
              memset_0(v91, 0, v35 - v36);
              v13 = v90;
              v91 = &v35[v90];
            }
            else
            {
              v13 = v90;
            }
          }
          else
          {
            v91 = v92;
          }
          if ( v28 != 8 )
          {
            v34 = LangIdFromSzLang;
LABEL_62:
            v37 = v100;
            v33 = v28 == 15100;
            v38 = v97;
            v7 = v84;
            if ( !v33 && v84 != 15105 )
            {
              v39 = 1;
              if ( !v84 )
              {
                v40 = -1;
                do
                  v33 = *(_WORD *)(v13 + 2 * v40++ + 2) == 0;
                while ( !v33 );
                v10 = Size;
                v41 = v95;
                v42 = Size + 20 + 2 * v40;
                v86 = v42;
                if ( v42 >= (unsigned int)v95 )
                {
                  v43 = (v42 + 4103) & 0xFFFFFFF8;
                  Src = PerflibciExtendBuffer(Src, Size, v43);
                  if ( Src )
                  {
                    LODWORD(v95) = v43;
                    v41 = v43;
                    goto LABEL_70;
                  }
                  v7 = 14;
LABEL_134:
                  v6 = a4;
LABEL_135:
                  PerflibciLocalReleaseMutex(g_hGlobalMutex);
                  v79 = Src;
                  if ( v94 && Src && (_DWORD)v10 )
                  {
                    v7 = 0;
                    *a3 = Src;
                    *v6 = v10 + 2;
                    goto LABEL_142;
                  }
LABEL_140:
                  operator delete(v79);
                  goto LABEL_142;
                }
LABEL_70:
                v44 = (unsigned __int16 *)&Src[v10];
                v45 = (unsigned int)(v41 - v10);
                v46 = Size_4;
                StringCbPrintfW(v44, v45, L"%d", Size_4);
                Size_4 = v46 + 2;
                v47 = -1;
                do
                  v33 = v44[++v47] == 0;
                while ( !v33 );
                v48 = Size + 2 * (v47 + 1);
                StringCbCopyW((unsigned __int16 *)&Src[v48], (unsigned int)(v95 - v48), (const unsigned __int16 *)v13);
                v50 = -1;
                do
                  v33 = *(_WORD *)(v49 + 2 * v50++ + 2) == 0;
                while ( !v33 );
                v34 = LangIdFromSzLang;
                v51 = v50 + 1;
                v52 = v82;
                Size = v48 + 2 * v51;
LABEL_78:
                if ( v85 == 9 )
                  v54 = 4 * !v52 + 6;
                else
                  v54 = v52 + 5;
                v55 = (unsigned __int8 *)v90;
                while ( 2 )
                {
                  v56 = (_DWORD)v91 - (_DWORD)v55;
                  v57 = PerflibciLocalQueryCounterSetRegInfoEx(0, v24, v54, v34, v55, (_DWORD)v91 - (_DWORD)v55, &v86);
                  v84 = v57;
                  if ( v57 )
                  {
                    if ( v57 != 8 )
                    {
                      v58 = LangIdFromSzLang;
                      if ( LangIdFromSzLang == (LangIdFromSzLang & 0x3FF) )
                      {
                        LangIdFromSzLang |= 0x400u;
                        v57 = PerflibciLocalQueryCounterSetRegInfoEx(
                                0,
                                v24,
                                v54,
                                v58 | 0x400,
                                (unsigned __int8 *)v90,
                                v56,
                                &v86);
                        v84 = v57;
                        break;
                      }
                      v7 = v57;
LABEL_87:
                      if ( v7 != 8 )
                        goto LABEL_97;
                    }
                    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                             &v90,
                                             (v86 + 7) & 0xFFFFFFF8) )
                    {
                      v84 = 14;
                      v102 = 0;
                    }
                    v55 = (unsigned __int8 *)v90;
                    v59 = &v92[-v90];
                    v60 = (char *)v91 - v90;
                    if ( &v92[-v90] > (char *)v91 - v90 )
                    {
                      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&v90, v59) )
                      {
                        memset_0(v91, 0, v59 - v60);
                        v55 = (unsigned __int8 *)v90;
                        v91 = &v59[v90];
                      }
                      else
                      {
                        v55 = (unsigned __int8 *)v90;
                      }
                    }
                    else
                    {
                      v91 = v92;
                    }
                    v7 = v84;
                    v34 = LangIdFromSzLang;
                    if ( v84 != 8 )
                    {
LABEL_97:
                      v52 = v82;
                      v13 = v90;
                      goto LABEL_98;
                    }
                    continue;
                  }
                  break;
                }
                v7 = v57;
                goto LABEL_87;
              }
              v53 = Size_4;
LABEL_100:
              if ( v7 )
                goto LABEL_129;
              if ( !v39 )
                goto LABEL_132;
              v61 = *(_DWORD *)(v13 + 4);
              if ( v61 != *(_DWORD *)(v37 + 128) )
              {
                v7 = 13;
                goto LABEL_104;
              }
              v62 = 0;
              if ( !v61 )
                goto LABEL_131;
              while ( 2 )
              {
                v63 = *(unsigned int *)(v13 + 8 * v62 + 12);
                if ( (_DWORD)v63 != -1 )
                {
                  v64 = (const wchar_t *)(v13 + v63);
                  v65 = -1;
                  do
                    v33 = v64[++v65] == 0;
                  while ( !v33 );
                  v66 = Size;
                  v67 = v95;
                  v68 = Src;
                  v69 = Size + 20 + 2 * v65;
                  v86 = v69;
                  if ( v69 >= (unsigned int)v95 )
                  {
                    v67 = (v69 + 4103) & 0xFFFFFFF8;
                    v95 = v67;
                    Src = PerflibciExtendBuffer(Src, Size, v67);
                    v68 = Src;
                    if ( !Src )
                    {
                      v7 = 14;
                      v102 = 0;
                      v84 = 14;
                      goto LABEL_126;
                    }
                  }
                  if ( !v84 )
                  {
                    v70 = &v68[v66];
                    StringCbPrintfW((unsigned __int16 *)&v68[v66], v67 - (unsigned int)v66, L"%d", v53);
                    v73 = -1;
                    do
                      v33 = *(_WORD *)&v70[2 * v73++ + 2] == 0;
                    while ( !v33 );
                    v74 = v66 + 2 * (v73 + 1);
                    if ( StringValidateDestW(v71, (unsigned __int64)(v67 - v74) >> 1, v72) < 0 )
                    {
                      if ( v75 )
                        *v77 = 0;
                    }
                    else
                    {
                      StringCopyWorkerW(v77, v75, v76, v64, cchToCopy);
                    }
                    v78 = -1;
                    do
                      ++v78;
                    while ( v77[v78] );
                    Size = v74 + 2 * (v78 + 1);
                  }
                }
                v7 = v84;
LABEL_126:
                v53 += 2;
                v62 = (unsigned int)(v62 + 1);
                if ( (unsigned int)v62 >= *(_DWORD *)(v13 + 4) )
                  goto LABEL_130;
                continue;
              }
            }
            v52 = v82;
            v39 = v82;
            if ( !v84 )
            {
              if ( !v82 )
                goto LABEL_132;
              goto LABEL_78;
            }
LABEL_98:
            v53 = Size_4;
            if ( v7 != 15100 && v7 != 15105 )
              goto LABEL_100;
            if ( v52 )
            {
LABEL_129:
              if ( v39 )
              {
LABEL_130:
                if ( !v7 )
LABEL_131:
                  ++v94;
LABEL_104:
                LODWORD(v10) = Size;
LABEL_105:
                v16 = v102;
                v9 = v85;
                goto LABEL_106;
              }
            }
LABEL_132:
            LODWORD(v10) = v38;
            Size = v38;
            goto LABEL_105;
          }
        }
        v34 = LangIdFromSzLang;
        if ( LangIdFromSzLang == (LangIdFromSzLang & 0x3FF) )
        {
          LangIdFromSzLang |= 0x400u;
          v28 = PerflibciLocalQueryCounterSetRegInfoEx(0, v24, v23, v34 | 0x400, (unsigned __int8 *)v13, v26, &v86);
          v84 = v28;
LABEL_51:
          v34 = LangIdFromSzLang;
        }
        if ( v28 != 8 )
          goto LABEL_62;
        goto LABEL_53;
      }
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&v90, v14) )
      {
        memset_0(v91, 0, v14 - v15);
        v13 = v90;
        v7 = v83;
        v17 = &v14[v90];
        v16 = v102;
        v91 = v17;
        v11 = Src;
LABEL_18:
        Src = v11;
        goto LABEL_19;
      }
      v16 = v102;
      v11 = Src;
      v7 = v83;
    }
    else
    {
      v7 = 14;
      v102 = 0;
      v16 = 0;
    }
    v13 = v90;
    goto LABEL_18;
  }
LABEL_142:
  operator delete(Block);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids);
  if ( v90 != -1 )
    operator delete((void *)v90);
  return v7;
}

```

## disassembly

```asm
0x180003b40  mov     rax, rsp
0x180003b43  mov     [rax+20h], r9
0x180003b47  mov     [rax+18h], r8
0x180003b4b  mov     [rax+8], ecx
0x180003b4e  push    rbp
0x180003b4f  lea     rbp, [rax-5Fh]
0x180003b53  sub     rsp, 0F0h
0x180003b5a  mov     [rax-10h], rbx
0x180003b5e  sub     dx, 48h ; 'H'
0x180003b62  mov     [rax-18h], rsi
0x180003b66  mov     rbx, r8
0x180003b69  mov     [rax-30h], r13
0x180003b6d  mov     esi, ecx
0x180003b6f  mov     [rax-38h], r14
0x180003b73  mov     r13, r9
0x180003b76  mov     eax, 0FFDFh
0x180003b7b  test    ax, dx
0x180003b7e  jz      short loc_180003B87
0x180003b80  xor     al, al
0x180003b82  mov     [rbp+57h+var_B0], al
0x180003b85  jmp     short loc_180003B8B
0x180003b87  mov     [rbp+57h+var_B0], 1
0x180003b8b  lea     rcx, [rbp+57h+var_90]
0x180003b8f  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x180003b94  xor     r14d, r14d
0x180003b97  mov     [rbp+57h+var_A4], r14d
0x180003b9b  mov     [rbp+57h+var_68], r14d
0x180003b9f  mov     [rbp+57h+var_78], r14d
0x180003ba3  mov     [rbp+57h+Block], r14
0x180003ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bae  test    dword ptr [rcx+1Ch], 400h
0x180003bb5  jz      short loc_180003BD2
0x180003bb7  cmp     byte ptr [rcx+19h], 4
0x180003bbb  jb      short loc_180003BD2
0x180003bbd  mov     rcx, [rcx+10h]
0x180003bc1  lea     r8, WPP_57908ebe3a6b3f9305bc9279d0bf0558_Traceguids
0x180003bc8  mov     edx, 0Ah
0x180003bcd  call    WPP_SF_
0x180003bd2  mov     [rsp+0F0h+var_18], rdi
0x180003bda  test    rbx, rbx
0x180003bdd  jz      loc_180004410
0x180003be3  test    r13, r13
0x180003be6  jz      loc_180004410
0x180003bec  mov     [rbx], r14
0x180003bef  mov     [r13+0], r14d
0x180003bf3  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180003bf8  mov     edi, eax
0x180003bfa  test    eax, eax
0x180003bfc  jnz     loc_180004415
0x180003c02  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180003c09  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180003c0e  mov     edi, eax
0x180003c10  test    eax, eax
0x180003c12  jnz     loc_180004406
0x180003c18  mov     [rsp+0F0h+var_20], r12
0x180003c20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003c27  movzx   r12d, si
0x180003c2b  mov     [rsp+0F0h+var_38], r15
0x180003c33  mov     r15, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180003c3a  mov     eax, 3FFh
0x180003c3f  mov     ebx, 1000h
0x180003c44  mov     dword ptr [rbp+57h+Size], r14d
0x180003c48  and     r12w, ax
0x180003c4c  mov     [rbp+57h+var_74], r14d
0x180003c50  mov     ecx, ebx; unsigned __int64
0x180003c52  mov     [rbp+57h+var_A8], r12w
0x180003c57  mov     esi, r14d
0x180003c5a  mov     [rbp+57h+var_70], rbx
0x180003c5e  mov     [rbp+57h+var_58], r15
0x180003c62  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003c67  mov     [rbp+57h+Src], rax
0x180003c6b  test    rax, rax
0x180003c6e  jz      loc_180003D11
0x180003c74  mov     r8d, ebx; Size
0x180003c77  xor     edx, edx; Val
0x180003c79  mov     rcx, rax; void *
0x180003c7c  call    memset_0
0x180003c81  mov     edx, ebx
0x180003c83  lea     rcx, [rbp+57h+var_90]
0x180003c87  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180003c8c  mov     r14, [rbp+57h+var_90]
0x180003c90  test    al, al
0x180003c92  mov     rbx, [rbp+57h+var_80]
0x180003c96  mov     ecx, 0Eh
0x180003c9b  cmovz   edi, ecx
0x180003c9e  mov     [rbp+57h+arg_8], al
0x180003ca1  mov     [rbp+57h+var_AC], edi
0x180003ca4  sub     rbx, r14
0x180003ca7  mov     rdi, [rbp+57h+var_88]
0x180003cab  sub     rdi, r14
0x180003cae  cmp     rbx, rdi
0x180003cb1  ja      short loc_180003CC4
0x180003cb3  mov     edi, [rbp+57h+var_AC]
0x180003cb6  lea     rax, [rbx+r14]
0x180003cba  movzx   ebx, [rbp+57h+arg_8]
0x180003cbe  mov     [rbp+57h+var_88], rax
0x180003cc2  jmp     short loc_180003D24
0x180003cc4  mov     rdx, rbx
0x180003cc7  lea     rcx, [rbp+57h+var_90]
0x180003ccb  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180003cd0  test    al, al
0x180003cd2  jz      short loc_180003D01
0x180003cd4  mov     rcx, [rbp+57h+var_88]; void *
0x180003cd8  mov     r8, rbx
0x180003cdb  sub     r8, rdi; Size
0x180003cde  xor     edx, edx; Val
0x180003ce0  call    memset_0
0x180003ce5  mov     r14, [rbp+57h+var_90]
0x180003ce9  mov     edi, [rbp+57h+var_AC]
0x180003cec  lea     rax, [rbx+r14]
0x180003cf0  movzx   ebx, [rbp+57h+arg_8]
0x180003cf4  mov     [rbp+57h+var_88], rax
0x180003cf8  mov     rax, [rbp+57h+Src]
0x180003cfc  mov     [rbp+57h+arg_8], bl
0x180003cff  jmp     short loc_180003D20
0x180003d01  movzx   ebx, [rbp+57h+arg_8]
0x180003d05  mov     rax, [rbp+57h+Src]
0x180003d09  mov     edi, [rbp+57h+var_AC]
0x180003d0c  mov     [rbp+57h+arg_8], bl
0x180003d0f  jmp     short loc_180003D1C
0x180003d11  mov     edi, 0Eh
0x180003d16  mov     [rbp+57h+arg_8], sil
0x180003d1a  xor     bl, bl
0x180003d1c  mov     r14, [rbp+57h+var_90]
0x180003d20  mov     [rbp+57h+Src], rax
0x180003d24  cmp     r12w, 9
0x180003d29  jnz     short loc_180003D8F
0x180003d2b  lea     r9, [rbp+57h+var_78]
0x180003d2f  xor     r8d, r8d
0x180003d32  lea     rdx, [rbp+57h+var_68]
0x180003d36  mov     ecx, 24h ; '$'
0x180003d3b  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180003d41  cmp     eax, 0C0000023h
0x180003d46  jz      short loc_180003D4C
0x180003d48  test    eax, eax
0x180003d4a  jnz     short loc_180003D8F
0x180003d4c  mov     eax, [rbp+57h+var_78]
0x180003d4f  test    eax, eax
0x180003d51  jz      short loc_180003D8F
0x180003d53  mov     edx, eax
0x180003d55  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003d5c  mov     eax, 2
0x180003d61  mul     rdx
0x180003d64  cmovb   rax, rcx
0x180003d68  mov     rcx, rax
0x180003d6b  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180003d70  mov     [rbp+57h+Block], rax
0x180003d74  test    rax, rax
0x180003d77  jz      short loc_180003D8F
0x180003d79  lea     r9, [rbp+57h+var_78]
0x180003d7d  mov     r8, rax
0x180003d80  lea     rdx, [rbp+57h+var_68]
0x180003d84  mov     ecx, 24h ; '$'
0x180003d89  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180003d8f  test    bl, bl
0x180003d91  jz      loc_1800043C5
0x180003d97  mov     edx, 9
0x180003d9c  test    r15, r15
0x180003d9f  jz      loc_1800043C1
0x180003da5  mov     r15, [r15+20h]
0x180003da9  mov     [rbp+57h+var_50], r15
0x180003dad  test    r15, r15
0x180003db0  jz      loc_180004246
0x180003db6  mov     eax, [r15+5Ch]
0x180003dba  movzx   ecx, [rbp+57h+var_B0]
0x180003dbe  test    cl, cl
0x180003dc0  mov     [rbp+57h+var_64], esi
0x180003dc3  lea     edi, [rax+1]
0x180003dc6  cmovz   edi, eax
0x180003dc9  mov     dword ptr [rbp+57h+Size+4], edi
0x180003dcc  cmp     r12w, 9
0x180003dd1  jnz     short loc_180003DDF
0x180003dd3  test    cl, cl
0x180003dd5  mov     ebx, 4
0x180003dda  cmovz   ebx, edx
0x180003ddd  jmp     short loc_180003DE9
0x180003ddf  xor     ebx, ebx
0x180003de1  test    cl, cl
0x180003de3  setnz   bl
0x180003de6  add     ebx, 3
0x180003de9  lea     r12, [r15+18h]
0x180003ded  movzx   r15d, [rbp+57h+var_A8]
0x180003df2  mov     esi, dword ptr [rbp+57h+var_88]
0x180003df5  lea     rax, [rbp+57h+var_A4]
0x180003df9  mov     r9d, [rbp+57h+arg_0]; unsigned int
0x180003dfd  sub     esi, r14d
0x180003e00  mov     [rsp+30h], rax; unsigned int *
0x180003e05  mov     r8d, ebx; enum _PerfRegInfoType
0x180003e08  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x180003e0c  mov     rdx, r12; struct _GUID *
0x180003e0f  xor     ecx, ecx; unsigned __int8
0x180003e11  mov     [rsp+0F0h+cchToCopy], r14; unsigned __int8 *
0x180003e16  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180003e1b  mov     [rbp+57h+var_AC], eax
0x180003e1e  mov     r13d, eax
0x180003e21  cmp     eax, 3AFCh
0x180003e26  jz      short loc_180003E33
0x180003e28  cmp     eax, 3B01h
0x180003e2d  jnz     loc_180003EB3
0x180003e33  cmp     r15w, 9
0x180003e38  jnz     short loc_180003EB3
0x180003e3a  mov     rax, [rbp+57h+Block]
0x180003e3e  test    rax, rax
0x180003e41  jz      short loc_180003EB3
0x180003e43  cmp     word ptr [rax], 0
0x180003e47  mov     rdi, rax
0x180003e4a  jz      short loc_180003EB3
0x180003e4c  mov     rcx, rdi; unsigned __int16 *
0x180003e4f  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180003e54  mov     r15d, eax
0x180003e57  mov     [rbp+57h+arg_0], eax
0x180003e5a  lea     rax, [rbp+57h+var_A4]
0x180003e5e  mov     r9d, r15d; unsigned int
0x180003e61  mov     [rsp+30h], rax; unsigned int *
0x180003e66  mov     r8d, ebx; enum _PerfRegInfoType
0x180003e69  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x180003e6d  mov     rdx, r12; struct _GUID *
0x180003e70  xor     ecx, ecx; unsigned __int8
0x180003e72  mov     [rsp+0F0h+cchToCopy], r14; unsigned __int8 *
0x180003e77  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180003e7c  mov     [rbp+57h+var_AC], eax
0x180003e7f  mov     r13d, eax
0x180003e82  cmp     eax, 3AFCh
0x180003e87  jz      short loc_180003E90
0x180003e89  cmp     eax, 3B01h
0x180003e8e  jnz     short loc_180003EAE
0x180003e90  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003e97  inc     rax
0x180003e9a  cmp     word ptr [rdi+rax*2], 0
0x180003e9f  jnz     short loc_180003E97
0x180003ea1  inc     eax
0x180003ea3  cmp     word ptr [rdi+rax*2], 0
0x180003ea8  lea     rdi, [rdi+rax*2]
0x180003eac  jnz     short loc_180003E4C
0x180003eae  movzx   r15d, [rbp+57h+var_A8]
0x180003eb3  test    r13d, r13d
0x180003eb6  jz      short loc_180003EFC
0x180003eb8  cmp     r13d, 8
0x180003ebc  jz      short loc_180003F09
0x180003ebe  mov     edx, [rbp+57h+arg_0]
0x180003ec1  movzx   eax, dx
0x180003ec4  and     eax, 3FFh
0x180003ec9  cmp     edx, eax
0x180003ecb  jnz     short loc_180003EFF
0x180003ecd  bts     edx, 0Ah
0x180003ed1  lea     rax, [rbp+57h+var_A4]
0x180003ed5  mov     [rsp+30h], rax; unsigned int *
0x180003eda  mov     r9d, edx; unsigned int
0x180003edd  mov     [rbp+57h+arg_0], edx
0x180003ee0  mov     r8d, ebx; enum _PerfRegInfoType
0x180003ee3  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x180003ee7  mov     rdx, r12; struct _GUID *
0x180003eea  xor     ecx, ecx; unsigned __int8
0x180003eec  mov     [rsp+0F0h+cchToCopy], r14; unsigned __int8 *
0x180003ef1  call    ?PerflibciLocalQueryCounterSetRegInfoEx@@YAKEPEBU_GUID@@W4_PerfRegInfoType@@KPEAEKPEAK@Z; PerflibciLocalQueryCounterSetRegInfoEx(uchar,_GUID const *,_PerfRegInfoType,ulong,uchar *,ulong,ulong *)
0x180003ef6  mov     r13d, eax
0x180003ef9  mov     [rbp+57h+var_AC], eax
0x180003efc  mov     edx, [rbp+57h+arg_0]
0x180003eff  cmp     r13d, 8
0x180003f03  jnz     loc_180003F92
0x180003f09  mov     edx, [rbp+57h+var_A4]
0x180003f0c  lea     rcx, [rbp+57h+var_90]
0x180003f10  add     edx, 7
0x180003f13  mov     eax, 0FFFFFFF8h
0x180003f18  and     rdx, rax
0x180003f1b  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180003f20  test    al, al
0x180003f22  jnz     short loc_180003F31
0x180003f24  mov     r13d, 0Eh
0x180003f2a  mov     [rbp+57h+arg_8], al
0x180003f2d  mov     [rbp+57h+var_AC], r13d
0x180003f31  mov     r14, [rbp+57h+var_90]
0x180003f35  mov     rdi, [rbp+57h+var_80]
0x180003f39  mov     rsi, [rbp+57h+var_88]
0x180003f3d  sub     rdi, r14
0x180003f40  sub     rsi, r14
0x180003f43  cmp     rdi, rsi
0x180003f46  ja      short loc_180003F52
0x180003f48  lea     rax, [rdi+r14]
0x180003f4c  mov     [rbp+57h+var_88], rax
0x180003f50  jmp     short loc_180003F85
0x180003f52  mov     rdx, rdi
0x180003f55  lea     rcx, [rbp+57h+var_90]
0x180003f59  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180003f5e  test    al, al
0x180003f60  jz      short loc_180003F81
0x180003f62  mov     rcx, [rbp+57h+var_88]; void *
0x180003f66  mov     r8, rdi
0x180003f69  sub     r8, rsi; Size
0x180003f6c  xor     edx, edx; Val
0x180003f6e  call    memset_0
0x180003f73  mov     r14, [rbp+57h+var_90]
0x180003f77  lea     rax, [rdi+r14]
0x180003f7b  mov     [rbp+57h+var_88], rax
0x180003f7f  jmp     short loc_180003F85
0x180003f81  mov     r14, [rbp+57h+var_90]
0x180003f85  cmp     r13d, 8
0x180003f89  jz      loc_180003DF2
0x180003f8f  mov     edx, [rbp+57h+arg_0]
0x180003f92  mov     r15, [rbp+57h+var_50]
  ... truncated ...
```
