# BCP_writefmt(tagDBC *,ushort const *)

- ea: `0x10049de40`
- end: `0x10049eccc`
- name: `?BCP_writefmt@@YAFPEAUtagDBC@@PEBG@Z`
- size: `3724`
- prototype: `__int16 __fastcall(struct tagDBC *, const unsigned __int16 *Source)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x100499e40`

## callees

- `0x100407bf0`
- `0x100408fa4`
- `0x100409338`
- `0x100412efc`
- `0x100413190`
- `0x10049de40`
- `0x1004a0064`
- `0x1004a13c0`
- `0x1004a9c2c`
- `0x1004ac368`
- `0x1004ac6a0`
- `0x1004aca40`
- `0x1004af7ac`
- `0x1004b5b5c`
- `0x100520370`
- `0x100525dbc`
- `0x100546a24`
- `0x100546a7c`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049df66`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049e731`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049e825`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049df66`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049e731`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049e825`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BCP_writefmt(struct tagDBC *a1, const unsigned __int16 *Source)
{
  __int64 *v5; // r13
  unsigned __int16 v6; // bx
  struct BCP_COL_INFO *v7; // rsi
  __int64 v8; // r15
  __int64 v9; // r15
  void *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r10
  unsigned int v17; // edx
  __int64 v18; // r8
  __int64 v19; // r11
  unsigned __int64 v20; // r10
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rcx
  int *v24; // rdx
  __int64 v25; // r8
  unsigned __int64 v26; // rax
  __int64 *v27; // r13
  unsigned __int16 v28; // dx
  struct BCP_COL_INFO *v29; // rax
  int v30; // ecx
  size_t v31; // rdi
  int v32; // eax
  __int64 v33; // r9
  __int64 v34; // r8
  unsigned int v35; // edi
  __int64 *v36; // rsi
  unsigned __int64 v37; // rbx
  size_t v38; // rdi
  char *v39; // rbx
  unsigned __int64 v40; // rbx
  char *v41; // rdi
  size_t v42; // rbx
  size_t v43; // rdi
  size_t v44; // rbx
  char *v45; // r10
  size_t v46; // rcx
  int v47; // eax
  size_t v48; // rax
  size_t v49; // rsi
  char *v50; // rbx
  unsigned __int8 *v51; // rbx
  unsigned __int8 *v52; // rdi
  unsigned __int64 v53; // rsi
  size_t v54; // rbx
  char *v55; // rdi
  unsigned __int64 v56; // rsi
  int v57; // ebx
  const WCHAR *v58; // rdx
  __int64 v59; // r8
  unsigned __int64 v60; // rax
  rsize_t v61; // rax
  unsigned __int64 v62; // rsi
  size_t v63; // rdi
  char *v64; // rbx
  char *v65; // rbx
  char *v66; // rbx
  size_t v67; // rsi
  char *v68; // rbx
  __int64 v69; // rdi
  const WCHAR *v70; // rdx
  __int64 v71; // r8
  unsigned __int64 v72; // rax
  unsigned __int64 v73; // rdx
  __int64 v74; // r9
  _WORD *v75; // rcx
  __int64 v76; // r8
  __int16 v77; // ax
  _WORD *v78; // rax
  unsigned __int64 v79; // rax
  __int64 v80; // r8
  __int64 v81; // rdx
  unsigned __int16 v82; // dx
  int v83; // r10d
  __int64 v84; // rbx
  struct BCP_COL_INFO *v85; // rdi
  __int64 v86; // rdi
  struct BCP_COL_INFO *v87; // rcx
  int v88; // eax
  int v89; // edi
  unsigned __int16 v90; // ax
  unsigned __int16 v91; // dx
  __int64 v92; // rcx
  unsigned __int64 v93; // [rsp+48h] [rbp-C0h] BYREF
  struct BCP_COL_INFO *v94; // [rsp+50h] [rbp-B8h]
  char *v95; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v96; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v97; // [rsp+68h] [rbp-A0h]
  __int64 v98; // [rsp+70h] [rbp-98h]
  __int64 v99; // [rsp+78h] [rbp-90h]
  size_t v100; // [rsp+80h] [rbp-88h]
  char *v101; // [rsp+88h] [rbp-80h]
  __int64 *v102; // [rsp+90h] [rbp-78h]
  ISequentialStream v103; // [rsp+98h] [rbp-70h] BYREF
  __int64 v104; // [rsp+A0h] [rbp-68h]
  __int64 v105; // [rsp+A8h] [rbp-60h]
  int v106; // [rsp+B0h] [rbp-58h]
  __int64 v107; // [rsp+B8h] [rbp-50h]
  void *Sourcea; // [rsp+C0h] [rbp-48h] BYREF
  rsize_t SourceSize; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v110; // [rsp+D0h] [rbp-38h]
  unsigned int v111; // [rsp+D8h] [rbp-30h]
  int v112; // [rsp+DCh] [rbp-2Ch]
  unsigned __int64 v113; // [rsp+E0h] [rbp-28h]
  LPCWSTR lpFileName; // [rsp+E8h] [rbp-20h]
  __int64 v115; // [rsp+F0h] [rbp-18h]
  __int64 v116; // [rsp+F8h] [rbp-10h]
  __int64 v117; // [rsp+100h] [rbp-8h]
  void **v118; // [rsp+108h] [rbp+0h] BYREF
  int v119; // [rsp+110h] [rbp+8h]
  struct tagDBC *v120; // [rsp+118h] [rbp+10h]
  __int64 v121; // [rsp+120h] [rbp+18h]
  CHAR v122[80]; // [rsp+128h] [rbp+20h] BYREF
  CHAR MultiByteStr[32]; // [rsp+178h] [rbp+70h] BYREF
  CHAR v124[528]; // [rsp+198h] [rbp+90h] BYREF

  v121 = -2;
  lpFileName = Source;
  if ( !ENTERBCPFUNC(a1) )
    return 0;
  v5 = (__int64 *)*((_QWORD *)a1 + 15);
  v102 = v5;
  v6 = 0;
  v7 = 0;
  v94 = 0;
  if ( *((_DWORD *)v5 + 475) == 1 )
  {
    if ( v5[234] )
    {
      v8 = -1;
      do
        ++v8;
      while ( Source[v8] );
      if ( v5[242] )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
      v9 = 2 * v8 + 2;
      v10 = SQLAllocateMemoryEx(a1, v9, 1);
      v5[242] = (__int64)v10;
      if ( v10 )
      {
        memcpy_s(v10, v9, Source, v9);
        v6 = 1;
      }
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5111817);
      PostSQLErrorEx(a1, 0x9CE2u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    }
    goto LABEL_163;
  }
  v11 = v5[1];
  v12 = *v5;
  v13 = *((unsigned int *)v5 + 5);
  LODWORD(v99) = *((_DWORD *)v5 + 5);
  v14 = *((_QWORD *)a1 + 12);
  v103.lpVtbl = (struct ISequentialStreamVtbl *)&CFormatStream::`vftable';
  v104 = v14;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  if ( !v12 || !(_DWORD)v13 )
    goto LABEL_163;
  v15 = 0;
  v16 = 0;
  v113 = 0;
  if ( *((_WORD *)v5 + 12) )
  {
    v17 = *((_DWORD *)a1 + 608);
    v18 = v11 + 94;
    v19 = *((unsigned __int16 *)v5 + 12);
    v7 = 0;
    do
    {
      v20 = v15;
      if ( v17 >= 0xC42C )
      {
        if ( v17 - 50220 <= 9 && (v22 = 679, _bittest(&v22, v17 - 50220))
          || v17 == 52936
          || v17 == 54936
          || v17 - 65000 <= 1
          || (v21 = 2, v17 - 57002 <= 9) )
        {
          v21 = 4;
        }
      }
      else
      {
        v21 = 2;
      }
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(v18 + 2 * v23) );
      v15 = v21 * v23;
      if ( v15 <= v20 )
        v15 = v20;
      v18 += 616;
      --v19;
    }
    while ( v19 );
    v16 = 0;
  }
  v24 = (int *)(v12 + 112);
  v25 = v13;
  do
  {
    v26 = *v24;
    if ( v26 <= v16 )
      v26 = v16;
    v16 = v26;
    v24 += 112;
    --v25;
  }
  while ( v25 );
  v113 = v26;
  v27 = v102;
  v115 = 2 * v26 + 49;
  v116 = 2 * v26 + 55;
  v117 = v15 + 5 + v116;
  v100 = v117 + 522;
  v101 = (char *)SQLAllocateMemoryEx(a1, v117 + 522, 1);
  if ( !v101 )
  {
    v103.lpVtbl = (struct ISequentialStreamVtbl *)&CFormatStream::`vftable';
    goto LABEL_163;
  }
  v98 = *v102;
  v110 = v102[1];
  if ( (*((_DWORD *)v102 + 13) & 0x4000) != 0 )
  {
    v29 = (struct BCP_COL_INFO *)SQLAllocateMemoryEx(a1, 76 * v13, 1);
    v7 = v29;
    v94 = v29;
    if ( !v29 )
      goto LABEL_48;
    v30 = v99;
    if ( (_DWORD)v99 )
    {
      do
      {
        *(_DWORD *)v29 = 1;
        v29 = (struct BCP_COL_INFO *)((char *)v29 + 76);
        --v13;
      }
      while ( v13 );
    }
  }
  else
  {
    if ( !lpFileName || !*lpFileName )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5225481);
      v28 = -25277;
      goto LABEL_47;
    }
    if ( (unsigned __int16)bcpOpen(a1, lpFileName, 2, (struct BCPFILE *)v122) == 0xFFFF )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5231625);
      v28 = -25245;
LABEL_47:
      PostSQLErrorEx(a1, v28, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
LABEL_48:
      v103.lpVtbl = (struct ISequentialStreamVtbl *)&CFormatStream::`vftable';
      goto LABEL_39;
    }
    v30 = v99;
  }
  v31 = v100;
  v32 = StringCchPrintfExA(v101, v100, 0, &v96, 0, "%s%d\r\n", "14.0\r\n", v30);
  if ( v32 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(0, 5253129, (unsigned int)v32, v33);
    }
LABEL_60:
    v103.lpVtbl = (struct ISequentialStreamVtbl *)&CFormatStream::`vftable';
    if ( v105 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    goto LABEL_160;
  }
  _mm_lfence();
  v34 = v31 - v96;
  v96 = v31 - v96;
  if ( (*((_DWORD *)v27 + 13) & 0x4000) != 0 )
  {
    if ( (int)CFormatStream::Write((CFormatStream *)&v103, v101, v34, 0) < 0 )
    {
      _mm_lfence();
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5263369);
      PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      goto LABEL_60;
    }
  }
  else if ( (unsigned __int16)bcpWrite(a1, (struct BCPFILE *)v122, v34, (const unsigned __int8 *)v101) == 0xFFFF )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 5271561);
    PostSQLErrorEx(a1, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    bcpClose(a1, (struct BCPFILE *)v122);
    goto LABEL_60;
  }
  v6 = 1;
  v112 = 1;
  v35 = 0;
  LODWORD(v97) = 0;
  v36 = v102;
  if ( !(_DWORD)v99 )
  {
    v85 = v94;
    goto LABEL_126;
  }
  v98 += 100;
  v37 = v100;
  while ( 1 )
  {
    v95 = v101;
    v93 = v37;
    memset_0(v101, 0, v37);
    v111 = v35 + 1;
    StringCchPrintfExA(v101, v37, &v95, &v93, 0, "%d", v35 + 1);
    v38 = v93 - v37 + 8;
    v39 = v95;
    memset_0(v95, 32, v38);
    v95 = &v39[v38];
    v40 = v93 - v38;
    v93 -= v38;
    if ( TDSTypeToFieldName(*(_BYTE *)v98, v95, 0x14u, &v96) < 0 )
    {
      _mm_lfence();
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5311497);
      v82 = -25377;
      goto LABEL_107;
    }
    v41 = &v95[v96];
    v93 = v40 - v96;
    v42 = v40 - v96 - v100 + 28;
    memset_0(&v95[v96], 32, v42);
    v95 = &v41[v42];
    v93 -= v42;
    StringCchPrintfExA(&v41[v42], v93, &v95, &v93, 0, "%d", *(_DWORD *)(v98 - 4));
    v43 = v100;
    v44 = v93 - v100 + 36;
    memset_0(v95, 32, v44);
    v45 = &v95[v44];
    v95 += v44;
    v46 = v93 - v44;
    v93 -= v44;
    v47 = *(_DWORD *)(v98 - 8);
    if ( v47 == 0xFFFF || v47 == 0x7FFFFFFF || *(_BYTE *)v98 == 98 )
      v47 = 0;
    if ( (int)StringCchPrintfExA(v45, v46, &v95, &v93, 0, "%d", v47) < 0 || (v48 = v43 - v93, v43 - v93 > 0x2C) )
    {
      _mm_lfence();
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5354505);
      PostSQLErrorEx(a1, 0x9D3Au, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v6 = 0;
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5356553);
      goto LABEL_125;
    }
    v49 = 44 - v48;
    v50 = v95;
    memset_0(v95, 32, 44 - v48);
    v50[v49] = 34;
    v51 = (unsigned __int8 *)&v50[v49 + 1];
    ConvertTerminatorToChar(*(const unsigned __int8 **)(v98 + 4), *(int *)(v98 + 12), v51, 2 * v113 + 2, &v96);
    v51[v96++] = 34;
    v52 = &v51[v96];
    v53 = v93 - v49 - v96 - 1;
    v54 = v115 + v53 - v100;
    memset_0(v52, 32, v54);
    v55 = (char *)&v52[v54];
    v95 = v55;
    v56 = v53 - v54;
    v93 = v56;
    if ( (unsigned int)v97 > *((unsigned __int16 *)v102 + 12) )
      goto LABEL_86;
    v57 = *(unsigned __int16 *)(v98 - 52);
    LODWORD(v97) = v57;
    if ( (_WORD)v57 )
    {
      v110 = 616LL * (unsigned __int16)v57 + v102[1] - 616;
      v58 = (const WCHAR *)(v110 + 94);
      v59 = -1;
      do
        ++v59;
      while ( v58[v59] );
      LODWORD(Sourcea) = 0;
      v60 = SystemLocale::FastAsciiWideCharToMultiByte(
              *((_DWORD *)a1 + 608),
              v58,
              v59 + 1,
              v124,
              0x204u,
              (int *)&Sourcea,
              0);
      if ( v60 <= 1 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 5425161);
        v91 = -25066;
        goto LABEL_136;
      }
      SourceSize = v60 - 1;
      Sourcea = v124;
    }
    else
    {
LABEL_86:
      LOWORD(v57) = 0;
      LODWORD(v97) = 0;
      Sourcea = szSkip;
      v61 = -1;
      do
        ++v61;
      while ( szSkip[v61] );
      SourceSize = v61;
    }
    StringCchPrintfExA(v55, v56, &v95, &v93, 0, "%d", (unsigned __int16)v57);
    v62 = v93;
    v63 = v116 + v93 - v100;
    v64 = v95;
    memset_0(v95, 32, v63);
    v65 = &v64[v63];
    v96 = SourceSize;
    memcpy_s(v65, SourceSize, Sourcea, SourceSize);
    v66 = &v65[v96];
    v67 = v117 + v62 - v63 - v96 - v100;
    memset_0(v66, 32, v67);
    v68 = &v66[v67];
    v69 = v110;
    v70 = (const WCHAR *)(v110 + 352);
    v71 = -1;
    do
      ++v71;
    while ( v70[v71] );
    LODWORD(SourceSize) = 0;
    v72 = SystemLocale::FastAsciiWideCharToMultiByte(
            *((_DWORD *)a1 + 608),
            v70,
            v71 + 1,
            v124,
            0x204u,
            (int *)&SourceSize,
            0);
    if ( !v72 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5469193);
      v91 = -25263;
LABEL_136:
      PostSQLErrorEx(a1, v91, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v6 = 0;
      v36 = v102;
      goto LABEL_125;
    }
    v73 = v72 - 1;
    v74 = 129;
    v75 = (_WORD *)(v98 + 66);
    v76 = v69 - (v98 + 66);
    do
    {
      if ( v74 == -2147483517 )
        break;
      v77 = *(_WORD *)((char *)v75 + v76 + 352);
      if ( !v77 )
        break;
      *v75++ = v77;
      --v74;
    }
    while ( v74 );
    v78 = v75 - 1;
    if ( v74 )
      v78 = v75;
    *v78 = 0;
    v96 = v73;
    if ( v73 )
    {
      memcpy_s(v68, v73, v124, v73);
      v79 = v96;
    }
    else
    {
      *(_WORD *)v68 = 8738;
      v79 = 2;
      v96 = 2;
    }
    v93 = 522 - v79;
    StringCchPrintfExA(&v68[v79], 522 - v79, &v95, &v93, 0, "\r\n");
    v37 = v100;
    v80 = v100 - v93;
    v96 = v100 - v93;
    v36 = v102;
    if ( (*((_DWORD *)v102 + 13) & 0x4000) != 0 )
    {
      if ( (int)CFormatStream::Write((CFormatStream *)&v103, v101, v80, 0) < 0 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_106:
          v82 = -25322;
LABEL_107:
          PostSQLErrorEx(a1, v82, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
          v6 = 0;
LABEL_125:
          v85 = v94;
          goto LABEL_126;
        }
        v81 = 5511177;
LABEL_105:
        bidTraceMark(0, v81);
        goto LABEL_106;
      }
    }
    else if ( (unsigned __int16)bcpWrite(a1, (struct BCPFILE *)v122, v80, (const unsigned __int8 *)v101) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_106;
      v81 = 5520393;
      goto LABEL_105;
    }
    if ( (*((_DWORD *)v36 + 13) & 0x4000) != 0 && (_WORD)v97 )
      break;
LABEL_123:
    v35 = v111;
    LODWORD(v97) = v111;
    v98 += 448;
    if ( v111 >= (unsigned int)v99 )
    {
      v6 = v112;
      goto LABEL_125;
    }
  }
  v83 = *(unsigned __int8 *)(v69 + 36);
  v84 = 76LL * (unsigned __int16)v97;
  v85 = v94;
  *(_DWORD *)((char *)v94 + v84 - 76) = 0;
  if ( v83 == 38 || v83 == 109 || v83 == 110 || v83 == 111 )
  {
    LOBYTE(v83) = GetGenericType(*(_BYTE *)(v110 + 36), *(_QWORD *)(v110 + 8), 1);
  }
  else if ( v83 == 241 )
  {
    LOBYTE(v83) = -25;
  }
  if ( TDSTypeToFieldName(v83, MultiByteStr, 0x1Eu, 0) >= 0 )
  {
    if ( !SystemLocale::FastAsciiMultiByteToWideChar(
            *((_DWORD *)a1 + 608),
            MultiByteStr,
            -1,
            (LPWSTR)((char *)v85 + v84 - 72),
            0x1Eu,
            0,
            0) )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 5570569);
      PostSQLErrorEx(a1, 0x9CDFu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      v6 = 0;
      goto LABEL_157;
    }
    v86 = v110;
    v87 = v94;
    *(_DWORD *)((char *)v94 + v84 - 12) = *(_DWORD *)(v110 + 64);
    *((_BYTE *)v87 + v84 - 8) = *(_BYTE *)v86;
    *((_BYTE *)v87 + v84 - 7) = *(_BYTE *)(v86 + 18);
    v88 = 0;
    if ( !*(_DWORD *)(v86 + 60) )
      v88 = *(_DWORD *)(v86 + 8);
    *(_DWORD *)((char *)v87 + v84 - 4) = v88;
    v37 = v100;
    goto LABEL_123;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceMark(0, 5558281);
  PostSQLErrorEx(a1, 0x9CDFu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
  v6 = 0;
LABEL_126:
  if ( (*((_DWORD *)v36 + 13) & 0x4000) != 0 )
  {
    if ( v6 == 1 )
    {
      _mm_lfence();
      v118 = &CODBCXmlFmtExceptionPoster::`vftable';
      v119 = 0;
      v120 = a1;
      v89 = WriteXmlFormatFile(g_pMO, &v103, lpFileName, (struct IXmlFmtExceptionPoster *)&v118, v85);
      if ( v89 < 0 )
      {
        v6 = 0;
        if ( !v119 )
        {
          _mm_lfence();
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 5604361);
          v90 = RetCodeFromBCPHRESULT(v89);
          PostSQLErrorEx(a1, v90, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        }
      }
    }
  }
  else
  {
    _mm_lfence();
    bcpClose(a1, (struct BCPFILE *)v122);
  }
LABEL_157:
  v103.lpVtbl = (struct ISequentialStreamVtbl *)&CFormatStream::`vftable';
  if ( v105 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  v7 = v94;
LABEL_160:
  if ( v7 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
LABEL_39:
  ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
LABEL_163:
  v92 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 320LL) + 32LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 24LL))(v92);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)a1 + 9) + 32LL) + 24LL))(*((_QWORD *)a1 + 9) + 32LL);
  return v6;
}

```

## disassembly

```asm
0x10049de40  mov     rax, rsp
0x10049de43  push    rbp
0x10049de44  push    rsi
0x10049de45  push    rdi
0x10049de46  push    r12
0x10049de48  push    r13
0x10049de4a  push    r14
0x10049de4c  push    r15
0x10049de4e  lea     rbp, [rax-2E8h]
0x10049de55  sub     rsp, 3B0h
0x10049de5c  mov     [rbp+2E0h+var_2C8], 0FFFFFFFFFFFFFFFEh
0x10049de64  mov     [rax+18h], rbx
0x10049de68  mov     rax, cs:__security_cookie
0x10049de6f  xor     rax, rsp
0x10049de72  mov     [rbp+2E0h+var_40], rax
0x10049de79  mov     rdi, rdx
0x10049de7c  mov     [rbp+2E0h+lpFileName], rdx
0x10049de80  mov     r14, rcx
0x10049de83  call    ?ENTERBCPFUNC@@YAFPEAUtagDBC@@@Z; ENTERBCPFUNC(tagDBC *)
0x10049de88  xor     r11d, r11d
0x10049de8b  test    ax, ax
0x10049de8e  jnz     short loc_10049DE99
0x10049de90  movzx   eax, r11w
0x10049de94  jmp     loc_10049ECA2
0x10049de99  mov     r13, [r14+78h]
0x10049de9d  mov     [rbp+2E0h+var_358], r13
0x10049dea1  movzx   ebx, r11w
0x10049dea5  mov     rsi, r11
0x10049dea8  mov     [rsp+3E0h+var_398], r11
0x10049dead  mov     r12d, 1
0x10049deb3  cmp     [r13+76Ch], r12d
0x10049deba  jnz     loc_10049DF74
0x10049dec0  cmp     [r13+750h], r11
0x10049dec7  jnz     short loc_10049DF06
0x10049dec9  mov     r12d, 2
0x10049decf  test    byte ptr cs:_bidGblFlags, r12b
0x10049ded6  jz      short loc_10049DEE4
0x10049ded8  mov     edx, 4E0009h
0x10049dedd  xor     ecx, ecx
0x10049dedf  call    _bidTraceMark
0x10049dee4  mov     edx, 9CE2h; unsigned __int16
0x10049dee9  or      r13d, 0FFFFFFFFh
0x10049deed  mov     dword ptr [rsp+3E0h+var_3C0], r13d; unsigned int
0x10049def2  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10049def6  xor     r8d, r8d; int
0x10049def9  mov     rcx, r14; struct tagOBJBASE *
0x10049defc  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049df01  jmp     loc_10049EC6E
0x10049df06  or      r15, 0FFFFFFFFFFFFFFFFh
0x10049df0a  inc     r15
0x10049df0d  cmp     [rdi+r15*2], r11w
0x10049df12  jnz     short loc_10049DF0A
0x10049df14  mov     rdx, [r13+790h]
0x10049df1b  test    rdx, rdx
0x10049df1e  jz      short loc_10049DF34
0x10049df20  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10049df27  mov     rax, [rcx]
0x10049df2a  mov     rax, [rax+28h]
0x10049df2e  call    cs:__guard_dispatch_icall_fptr
0x10049df34  lea     r15, ds:2[r15*2]
0x10049df3c  mov     r8d, r12d; int
0x10049df3f  mov     rdx, r15; dwBytes
0x10049df42  mov     rcx, r14; struct tagOBJBASE *
0x10049df45  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x10049df4a  mov     [r13+790h], rax
0x10049df51  test    rax, rax
0x10049df54  jz      loc_10049EC6E
0x10049df5a  mov     r9, r15; SourceSize
0x10049df5d  mov     r8, rdi; Source
0x10049df60  mov     rdx, r15; DestinationSize
0x10049df63  mov     rcx, rax; Destination
0x10049df66  call    cs:__imp_memcpy_s
0x10049df6c  mov     ebx, r12d
0x10049df6f  jmp     loc_10049EC6E
0x10049df74  mov     r8, [r13+8]
0x10049df78  mov     r9, [r13+0]
0x10049df7c  mov     edi, [r13+14h]
0x10049df80  mov     dword ptr [rsp+3E0h+var_370], edi
0x10049df84  mov     rax, [r14+60h]
0x10049df88  lea     rcx, ??_7CFormatStream@@6B@; const CFormatStream::`vftable'
0x10049df8f  mov     [rbp+2E0h+var_350.lpVtbl], rcx
0x10049df93  mov     [rbp+2E0h+var_348], rax
0x10049df97  mov     [rbp+2E0h+var_340], r11
0x10049df9b  mov     [rbp+2E0h+var_338], r11d
0x10049df9f  mov     [rbp+2E0h+var_330], r11
0x10049dfa3  test    r9, r9
0x10049dfa6  jz      loc_10049EC6E
0x10049dfac  test    edi, edi
0x10049dfae  jz      loc_10049EC6E
0x10049dfb4  mov     rcx, r11
0x10049dfb7  mov     r10, r11
0x10049dfba  mov     [rbp+2E0h+var_308], r11
0x10049dfbe  mov     r12d, 2
0x10049dfc4  or      r15, 0FFFFFFFFFFFFFFFFh
0x10049dfc8  cmp     r11w, [r13+18h]
0x10049dfcd  jnb     loc_10049E064
0x10049dfd3  mov     edx, [r14+980h]
0x10049dfda  add     r8, 5Eh ; '^'
0x10049dfde  movzx   r11d, word ptr [r13+18h]
0x10049dfe3  xor     esi, esi
0x10049dfe5  mov     r10, rcx
0x10049dfe8  cmp     edx, 0C42Ch
0x10049dfee  jnb     short loc_10049DFF5
0x10049dff0  mov     rax, r12
0x10049dff3  jmp     short loc_10049E03C
0x10049dff5  lea     eax, [rdx-0C42Ch]
0x10049dffb  cmp     eax, 9
0x10049dffe  ja      short loc_10049E00A
0x10049e000  mov     ecx, 2A7h
0x10049e005  bt      ecx, eax
0x10049e008  jb      short loc_10049E037
0x10049e00a  cmp     edx, 0CEC8h
0x10049e010  jz      short loc_10049E037
0x10049e012  cmp     edx, 0D698h
0x10049e018  jz      short loc_10049E037
0x10049e01a  lea     eax, [rdx-0FDE8h]
0x10049e020  mov     ecx, 1
0x10049e025  cmp     eax, ecx
0x10049e027  jbe     short loc_10049E037
0x10049e029  lea     eax, [rdx-0DEAAh]
0x10049e02f  cmp     eax, 9
0x10049e032  mov     rax, r12
0x10049e035  ja      short loc_10049E03C
0x10049e037  mov     eax, 4
0x10049e03c  mov     rcx, r15
0x10049e03f  inc     rcx
0x10049e042  cmp     [r8+rcx*2], si
0x10049e047  jnz     short loc_10049E03F
0x10049e049  imul    rcx, rax
0x10049e04d  cmp     rcx, r10
0x10049e050  cmovbe  rcx, r10
0x10049e054  add     r8, 268h
0x10049e05b  sub     r11, 1
0x10049e05f  jnz     short loc_10049DFE5
0x10049e061  mov     r10, rsi
0x10049e064  test    edi, edi
0x10049e066  jz      short loc_10049E096
0x10049e068  lea     rdx, [r9+70h]
0x10049e06c  mov     r8, rdi
0x10049e06f  mov     r13d, 1
0x10049e075  movsxd  rax, dword ptr [rdx]
0x10049e078  cmp     rax, r10
0x10049e07b  cmovbe  rax, r10
0x10049e07f  mov     r10, rax
0x10049e082  lea     rdx, [rdx+1C0h]
0x10049e089  sub     r8, r13
0x10049e08c  jnz     short loc_10049E075
0x10049e08e  mov     [rbp+2E0h+var_308], rax
0x10049e092  mov     r13, [rbp+2E0h+var_358]
0x10049e096  lea     rax, ds:31h[r10*2]
0x10049e09e  mov     [rbp+2E0h+var_2F8], rax
0x10049e0a2  add     rax, 6
0x10049e0a6  mov     [rbp+2E0h+var_2F0], rax
0x10049e0aa  add     rcx, 5
0x10049e0ae  add     rax, rcx
0x10049e0b1  mov     [rbp+2E0h+var_2E8], rax
0x10049e0b5  add     rax, 20Ah
0x10049e0bb  mov     [rsp+3E0h+var_368], rax
0x10049e0c0  mov     r8d, 1; int
0x10049e0c6  mov     rdx, rax; dwBytes
0x10049e0c9  mov     rcx, r14; struct tagOBJBASE *
0x10049e0cc  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x10049e0d1  mov     [rbp+2E0h+var_360], rax
0x10049e0d5  xor     ecx, ecx
0x10049e0d7  test    rax, rax
0x10049e0da  jnz     short loc_10049E10D
0x10049e0dc  lea     rdx, ??_7CFormatStream@@6B@; const CFormatStream::`vftable'
0x10049e0e3  mov     [rbp+2E0h+var_350.lpVtbl], rdx
0x10049e0e7  mov     rdx, [rbp+2E0h+var_340]
0x10049e0eb  test    rdx, rdx
0x10049e0ee  jz      loc_10049EC6E
0x10049e0f4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10049e0fb  mov     rax, [rcx]
0x10049e0fe  mov     rax, [rax+28h]
0x10049e102  call    cs:__guard_dispatch_icall_fptr
0x10049e108  jmp     loc_10049EC6E
0x10049e10d  mov     rax, [r13+0]
0x10049e111  mov     [rsp+3E0h+var_378], rax
0x10049e116  mov     rax, [r13+8]
0x10049e11a  mov     [rbp+2E0h+var_318], rax
0x10049e11e  test    dword ptr [r13+34h], 4000h
0x10049e126  jnz     loc_10049E1BF
0x10049e12c  mov     rax, [rbp+2E0h+lpFileName]
0x10049e130  test    rax, rax
0x10049e133  jz      short loc_10049E1A5
0x10049e135  cmp     [rax], cx
0x10049e138  jz      short loc_10049E1A5
0x10049e13a  lea     r9, [rbp+2E0h+var_2C0]; struct BCPFILE *
0x10049e13e  mov     r8d, r12d; unsigned int
0x10049e141  mov     rdx, rax; lpFileName
0x10049e144  mov     rcx, r14; struct tagDBC *
0x10049e147  call    ?bcpOpen@@YAFPEAUtagDBC@@PEBGIPEAUBCPFILE@@@Z; bcpOpen(tagDBC *,ushort const *,uint,BCPFILE *)
0x10049e14c  cmp     ax, r15w
0x10049e150  jnz     loc_10049E1F8
0x10049e156  test    byte ptr cs:_bidGblFlags, r12b
0x10049e15d  jz      short loc_10049E16B
0x10049e15f  mov     edx, 4FD409h
0x10049e164  xor     ecx, ecx
0x10049e166  call    _bidTraceMark
0x10049e16b  mov     edx, 9D63h; unsigned __int16
0x10049e170  or      r13d, 0FFFFFFFFh
0x10049e174  mov     dword ptr [rsp+3E0h+var_3C0], r13d; unsigned int
0x10049e179  mov     r9, r15; unsigned __int64
0x10049e17c  xor     r8d, r8d; int
0x10049e17f  mov     rcx, r14; struct tagOBJBASE *
0x10049e182  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049e187  nop
0x10049e188  lea     rdx, ??_7CFormatStream@@6B@; const CFormatStream::`vftable'
0x10049e18f  mov     [rbp+2E0h+var_350.lpVtbl], rdx
0x10049e193  mov     rdx, [rbp+2E0h+var_340]
0x10049e197  test    rdx, rdx
0x10049e19a  jz      loc_10049EC65
0x10049e1a0  jmp     loc_10049EC51
0x10049e1a5  test    byte ptr cs:_bidGblFlags, r12b
0x10049e1ac  jz      short loc_10049E1B8
0x10049e1ae  mov     edx, 4FBC09h
0x10049e1b3  call    _bidTraceMark
0x10049e1b8  mov     edx, 9D43h
0x10049e1bd  jmp     short loc_10049E170
0x10049e1bf  imul    rdx, rdi, 4Ch ; 'L'; dwBytes
0x10049e1c3  mov     r8d, 1; int
0x10049e1c9  mov     rcx, r14; struct tagOBJBASE *
0x10049e1cc  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x10049e1d1  mov     rsi, rax
0x10049e1d4  mov     [rsp+3E0h+var_398], rax
0x10049e1d9  test    rax, rax
0x10049e1dc  jz      short loc_10049E188
0x10049e1de  mov     ecx, dword ptr [rsp+3E0h+var_370]
0x10049e1e2  test    ecx, ecx
0x10049e1e4  jz      short loc_10049E1FC
0x10049e1e6  mov     edx, 1
0x10049e1eb  mov     [rax], edx
0x10049e1ed  lea     rax, [rax+4Ch]
0x10049e1f1  sub     rdi, rdx
0x10049e1f4  jnz     short loc_10049E1EB
0x10049e1f6  jmp     short loc_10049E1FC
0x10049e1f8  mov     ecx, dword ptr [rsp+3E0h+var_370]
0x10049e1fc  mov     dword ptr [rsp+3E0h+var_3A8], ecx
0x10049e200  lea     rax, a140; "14.0\r\n"
0x10049e207  mov     [rsp+3E0h+var_3B0], rax
0x10049e20c  lea     rax, aSD; "%s%d\r\n"
0x10049e213  mov     [rsp+3E0h+var_3B8], rax; char *
0x10049e218  xor     eax, eax
0x10049e21a  mov     [rsp+3E0h+var_3C0], rax; unsigned int
0x10049e21f  lea     r9, [rsp+3E0h+var_388]; unsigned __int64 *
0x10049e224  xor     r8d, r8d; char **
0x10049e227  mov     rdi, [rsp+3E0h+var_368]
0x10049e22c  mov     rdx, rdi; Size
0x10049e22f  mov     rcx, [rbp+2E0h+var_360]; char *
0x10049e233  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x10049e238  xor     ecx, ecx
0x10049e23a  test    eax, eax
0x10049e23c  jns     short loc_10049E289
0x10049e23e  test    byte ptr cs:_bidGblFlags, r12b
0x10049e245  jz      short loc_10049E258
0x10049e247  lfence
0x10049e24a  mov     r8d, eax
0x10049e24d  mov     edx, 502809h
0x10049e252  call    _bidTraceHR
0x10049e257  nop
0x10049e258  lea     rdx, ??_7CFormatStream@@6B@; const CFormatStream::`vftable'
0x10049e25f  mov     [rbp+2E0h+var_350.lpVtbl], rdx
0x10049e263  mov     rdx, [rbp+2E0h+var_340]
0x10049e267  test    rdx, rdx
0x10049e26a  jz      loc_10049EC49
0x10049e270  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10049e277  mov     rax, [rcx]
0x10049e27a  mov     rax, [rax+28h]
0x10049e27e  call    cs:__guard_dispatch_icall_fptr
0x10049e284  jmp     loc_10049EC49
0x10049e289  lfence
0x10049e28c  mov     r8, rdi
0x10049e28f  sub     r8, [rsp+3E0h+var_388]; __int64
0x10049e294  mov     [rsp+3E0h+var_388], r8
0x10049e299  test    dword ptr [r13+34h], 4000h
0x10049e2a1  jz      short loc_10049E2F6
0x10049e2a3  xor     r9d, r9d; unsigned int *
0x10049e2a6  mov     rdx, [rbp+2E0h+var_360]; void *
0x10049e2aa  lea     rcx, [rbp+2E0h+var_350]; this
0x10049e2ae  call    ?Write@CFormatStream@@UEAAJPEBXKPEAK@Z; CFormatStream::Write(void const *,ulong,ulong *)
0x10049e2b3  xor     edx, edx
0x10049e2b5  test    eax, eax
0x10049e2b7  jns     loc_10049E350
0x10049e2bd  lfence
0x10049e2c0  test    byte ptr cs:_bidGblFlags, r12b
0x10049e2c7  jz      short loc_10049E2D5
0x10049e2c9  mov     edx, 505009h
0x10049e2ce  xor     ecx, ecx
0x10049e2d0  call    _bidTraceMark
0x10049e2d5  mov     edx, 9D16h; unsigned __int16
0x10049e2da  or      r13d, 0FFFFFFFFh
0x10049e2de  mov     dword ptr [rsp+3E0h+var_3C0], r13d; unsigned int
0x10049e2e3  mov     r9, r15; unsigned __int64
0x10049e2e6  xor     r8d, r8d; int
0x10049e2e9  mov     rcx, r14; struct tagOBJBASE *
0x10049e2ec  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049e2f1  jmp     loc_10049E258
0x10049e2f6  mov     r9, [rbp+2E0h+var_360]; unsigned __int8 *
0x10049e2fa  lea     rdx, [rbp+2E0h+var_2C0]; struct BCPFILE *
0x10049e2fe  mov     rcx, r14; struct tagDBC *
  ... truncated ...
```
