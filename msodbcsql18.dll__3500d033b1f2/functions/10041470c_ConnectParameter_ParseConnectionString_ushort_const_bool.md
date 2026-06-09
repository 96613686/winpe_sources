# ConnectParameter::ParseConnectionString(ushort const *,bool)

- ea: `0x10041470c`
- end: `0x1004158b7`
- name: `?ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z`
- size: `4523`
- prototype: `unsigned int __fastcall(LPCWCH lpString2, LPCWSTR lpSrcStr, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x100414210`
- `0x10043d748`

## callees

- `0x100413da8`
- `0x10041470c`
- `0x100416508`
- `0x1004165dc`
- `0x100419c90`
- `0x100419dc8`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005494b8`
- `0x1005494c4`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x100414b81`
- `KERNEL32!CompareStringW` at `0x100414e10`
- `KERNEL32!CompareStringW` at `0x100414e4c`
- `KERNEL32!CompareStringW` at `0x100414ebb`
- `KERNEL32!CompareStringW` at `0x100414b81`
- `KERNEL32!CompareStringW` at `0x100414e10`
- `KERNEL32!CompareStringW` at `0x100414e4c`
- `KERNEL32!CompareStringW` at `0x100414ebb`
- `KERNEL32!LCMapStringW` at `0x100414891`
- `KERNEL32!LCMapStringW` at `0x100414891`
- `USER32!CharNextW` at `0x1004149ca`
- `USER32!CharNextW` at `0x100414a3f`
- `USER32!CharNextW` at `0x1004149ca`
- `USER32!CharNextW` at `0x100414a3f`
- `VCRUNTIME140!wcschr` at `0x1004148ef`
- `VCRUNTIME140!wcschr` at `0x100414f87`
- `VCRUNTIME140!wcschr` at `0x100415067`
- `VCRUNTIME140!wcschr` at `0x1004148ef`
- `VCRUNTIME140!wcschr` at `0x100414f87`
- `VCRUNTIME140!wcschr` at `0x100415067`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConnectParameter::ParseConnectionString(WCHAR *lpString2, LPCWSTR lpSrcStr, char a3)
{
  __int64 v6; // r13
  int v7; // r12d
  char v8; // al
  __int64 v9; // rbx
  __int64 v10; // rdx
  WCHAR *lpDestStr; // rax
  unsigned int v12; // edi
  wchar_t *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r15
  unsigned int v16; // eax
  __int64 v17; // r8
  wchar_t *v18; // r14
  wchar_t *v19; // rax
  wchar_t *v20; // r12
  __int64 v21; // rbx
  LPCWCH v22; // rsi
  __int64 v23; // rdx
  WCHAR *v24; // rcx
  WCHAR v25; // ax
  WCHAR *v26; // rax
  __int64 v27; // rax
  rsize_t v28; // r15
  const WCHAR *v29; // r14
  const WCHAR *v30; // rbx
  const WCHAR *v31; // rax
  rsize_t v32; // rbp
  const WCHAR *v33; // r14
  unsigned __int64 v34; // rax
  rsize_t v35; // rbx
  __int64 v36; // rax
  int v37; // eax
  WCHAR *v38; // rcx
  char *v39; // rdx
  WCHAR v40; // ax
  WCHAR *v41; // rax
  __int64 v42; // rax
  WCHAR *v43; // rcx
  __int64 v44; // rdx
  WCHAR v45; // ax
  WCHAR *v46; // rax
  char *v47; // rbx
  __int64 v48; // rax
  _WORD *v49; // rax
  _WORD *v50; // rsi
  __int16 v51; // dx
  __int16 v52; // cx
  __int64 v53; // r13
  WCHAR *v54; // rcx
  __int64 v55; // rdx
  WCHAR v56; // ax
  WCHAR *v57; // rax
  bool v58; // al
  WCHAR *v59; // rcx
  __int64 v60; // r8
  WCHAR v61; // ax
  WCHAR *v62; // rax
  __int64 v63; // rdx
  signed __int64 v64; // rbx
  WCHAR v65; // ax
  WCHAR *v66; // rax
  const WCHAR *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  const WCHAR *v70; // rsi
  __int64 v71; // rax
  int v72; // eax
  __int64 v73; // rax
  __int64 v74; // rax
  _WORD *v75; // r14
  const WCHAR *v76; // r8
  __int64 v77; // rdx
  WCHAR *v78; // rbx
  int v79; // eax
  __int64 v80; // rax
  __int64 v81; // rdx
  WCHAR v82; // ax
  WCHAR *v83; // rax
  unsigned __int16 *v84; // rcx
  wchar_t *v85; // rax
  wchar_t *v86; // rsi
  __int64 v87; // rax
  __int64 v88; // rdx
  WCHAR *v89; // rcx
  WCHAR v90; // ax
  WCHAR *v91; // rax
  wchar_t *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  wchar_t *v95; // rdx
  wchar_t v96; // cx
  wchar_t v97; // ax
  __int64 v98; // rax
  _WORD *v99; // rax
  WCHAR *v100; // rcx
  __int64 v101; // rdx
  signed __int64 v102; // rsi
  WCHAR v103; // ax
  WCHAR *v104; // rax
  int v105; // esi
  __int64 v106; // rax
  _WORD *v107; // rax
  wchar_t *v108; // rbx
  __int64 v109; // rax
  wchar_t *v110; // rdx
  wchar_t v111; // cx
  wchar_t v112; // ax
  __int64 v113; // rax
  int v114; // eax
  wchar_t v115; // ax
  wchar_t *v116; // rcx
  wchar_t v117; // dx
  WCHAR *v118; // rcx
  __int64 v119; // rdx
  WCHAR *v120; // rax
  LPCWCH v121; // rbp
  __int64 v122; // rax
  WCHAR *v123; // rcx
  __int64 v124; // rdx
  WCHAR v125; // ax
  WCHAR *v126; // rax
  wchar_t *v127; // rdx
  wchar_t v128; // cx
  wchar_t v129; // ax
  WCHAR *v130; // rcx
  signed __int64 v131; // r14
  WCHAR v132; // ax
  int v133; // eax
  WCHAR v134; // ax
  WCHAR v135; // ax
  WCHAR *v136; // rax
  WCHAR *v137; // rbx
  unsigned int v138; // ebx
  wchar_t *v139; // r8
  __int64 v140; // rdx
  __int64 v141; // r10
  WCHAR *v142; // r9
  WCHAR v143; // ax
  WCHAR *v144; // rax
  char *v145; // rdx
  __int64 v146; // rcx
  WCHAR v147; // ax
  WCHAR *v148; // rax
  wchar_t *Str; // [rsp+68h] [rbp-60h]
  _QWORD v151[10]; // [rsp+78h] [rbp-50h] BYREF
  int v153; // [rsp+E8h] [rbp+20h]

  v151[1] = -2;
  v6 = -1;
  v151[0] = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_117[0] )
    bidScopeEnterW(v151, `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_117[0], lpSrcStr);
  v7 = 0;
  *((_BYTE *)lpString2 + 3096) = a3;
  if ( !*((_BYTE *)lpString2 + 3094) || (v8 = 1, a3) )
    v8 = 0;
  *((_BYTE *)lpString2 + 3094) = v8;
  v9 = -1;
  do
    ++v9;
  while ( lpSrcStr[v9] );
  v10 = 2LL * (unsigned int)(v9 + 1);
  if ( !is_mul_ok((unsigned int)(v9 + 1), 2u) )
    v10 = -1;
  lpDestStr = (WCHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 112LL))(
                         gpmo,
                         v10);
  Str = lpDestStr;
  if ( !lpDestStr )
  {
    v12 = 14;
    if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_137[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 140288, `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_137[0], 9);
    }
    SNISetLastError(9, 14, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_139[0] )
    {
      v13 = `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_139[0];
      v14 = 142336;
LABEL_310:
      bidTraceW(0, v14, v13, v12);
      goto LABEL_311;
    }
    goto LABEL_311;
  }
  v153 = 87;
  v15 = 256;
  v16 = LCMapStringW(0x800u, 0x100u, lpSrcStr, -1, lpDestStr, v9 + 1);
  if ( !v16 )
    goto LABEL_296;
  if ( v16 > (int)v9 + 1 )
    goto LABEL_296;
  _mm_lfence();
  Str[(unsigned int)v9] = 0;
  if ( (unsigned int)StrTrimBothW_Sys(Str, 3) )
    goto LABEL_296;
  _mm_lfence();
  v18 = Str;
  v19 = wcschr(Str, 0x3Au);
  v20 = v19;
  v21 = 11;
  if ( v19 )
  {
    *v19 = 0;
    if ( (__int64)(((char *)v19 - (char *)Str) & 0xFFFFFFFFFFFFFFFEuLL) <= 20 )
    {
      v22 = lpString2 + 768;
      v23 = 11;
      v24 = lpString2 + 768;
      v17 = (char *)Str - (char *)(lpString2 + 768);
      do
      {
        if ( v23 == -2147483635 )
          break;
        v25 = *(WCHAR *)((char *)v24 + v17);
        if ( !v25 )
          break;
        *v24++ = v25;
        --v23;
      }
      while ( v23 );
      v26 = v24 - 1;
      if ( v23 )
        v26 = v24;
      *v26 = 0;
      v27 = -1;
      do
        ++v27;
      while ( v22[v27] );
      v28 = (unsigned int)(v27 + 1);
      if ( !*v22 )
      {
LABEL_52:
        if ( v20 != Str
          && (!wcscmp_0(L"tcp", v22)
           || *v22 == 110 && v22[1] == 112 && !v22[2]
           || !wcscmp_0(L"lpc", v22)
           || !wcscmp_0(L"admin", v22)) )
        {
          _mm_lfence();
          v18 = v20 + 1;
          v36 = -1;
          do
            ++v36;
          while ( v18[v36] );
          v37 = StrTrimBothW_Sys(v20 + 1, 3);
          v7 = 0;
          if ( v37 )
            goto LABEL_296;
          v15 = 256;
        }
        else
        {
          *v20 = 58;
          *v22 = 0;
          v15 = 256;
        }
        goto LABEL_64;
      }
      if ( !v22[v28 - 1] )
      {
        v29 = lpString2 + 768;
        v30 = 0;
        do
        {
          if ( StrChrW_SYS(L" \t") )
          {
            v31 = v29;
            if ( v30 )
              v31 = v30;
            v30 = v31;
          }
          else
          {
            v30 = 0;
          }
          v29 = CharNextW(v29);
        }
        while ( *v29 );
        v22 = lpString2 + 768;
        if ( v30 )
        {
          v32 = v30 - v22 + 1;
          if ( v32 >= v28 )
            goto LABEL_295;
          *v30 = 0;
        }
        else
        {
          v32 = v28;
        }
        v33 = lpString2 + 768;
        if ( !*v22 )
        {
LABEL_51:
          v18 = Str;
          v21 = 11;
          goto LABEL_52;
        }
        if ( !v22[v32 - 1] )
        {
          do
          {
            if ( !StrChrW_SYS(L" \t") )
              break;
            v33 = CharNextW(v33);
          }
          while ( *v33 );
          if ( v33 != v22 )
          {
            v34 = v33 - v22;
            if ( v34 >= v32 )
              goto LABEL_144;
            _mm_lfence();
            v35 = v32 - v34;
            wmemmove_s_0(lpString2 + 768, v32, v33, v32 - v34);
            v22[v35] = 0;
          }
          goto LABEL_51;
        }
      }
    }
LABEL_295:
    v7 = 0;
    goto LABEL_296;
  }
LABEL_64:
  _mm_lfence();
  if ( CompareStringW(0x800u, 0, v18, 2, L"\\\\", 2) != 2 )
  {
    _mm_lfence();
    v85 = wcschr(v18, 0x2Cu);
    if ( v85 )
    {
      _mm_lfence();
      *v85 = 0;
      v86 = v85 + 1;
      v87 = -1;
      do
        ++v87;
      while ( v86[v87] );
      if ( (unsigned int)StrTrimBothW_Sys(v86, 3) )
        goto LABEL_293;
      if ( !lpString2[768] )
      {
        v88 = 11;
        v89 = lpString2 + 768;
        do
        {
          if ( v88 == -2147483635 )
            break;
          v90 = *(WCHAR *)((char *)v89 + (char *)L"tcp" - (char *)(lpString2 + 768));
          if ( !v90 )
            break;
          *v89++ = v90;
          --v88;
        }
        while ( v88 );
        v91 = v89 - 1;
        if ( v88 )
          v91 = v89;
        *v91 = 0;
      }
      if ( wcscmp_0(L"tcp", lpString2 + 768) )
      {
        v7 = 0;
        goto LABEL_296;
      }
      if ( !wcscmp_0(L"tcp", lpString2 + 768) )
      {
        _mm_lfence();
        v92 = wcschr(v86, 0x2Cu);
        if ( v92 )
        {
          _mm_lfence();
          *v92 = 0;
          v93 = -1;
          do
            ++v93;
          while ( v86[v93] );
          if ( (unsigned int)StrTrimBothW_Sys(v86, 3) )
            goto LABEL_293;
        }
      }
      if ( !*v86 )
        goto LABEL_293;
      if ( *v86 == 92 )
        goto LABEL_293;
      _mm_lfence();
      v94 = -1;
      do
        ++v94;
      while ( v86[v94] );
      if ( (unsigned int)v94 > 0xFF )
        goto LABEL_293;
      v95 = v18;
      if ( !*v18 )
        goto LABEL_293;
      v96 = *v18;
      v17 = 9;
      do
      {
        if ( v96 != 32 )
        {
          v97 = v96;
          if ( v96 != 9 )
            break;
        }
        v97 = *++v95;
        v96 = *v95;
      }
      while ( *v95 );
      if ( !v97 )
        goto LABEL_293;
      _mm_lfence();
      v98 = -1;
      do
        ++v98;
      while ( v86[v98] );
      v99 = (_WORD *)StrChrW_SYS(v86);
      if ( v99 )
        *v99 = 0;
      v100 = lpString2 + 779;
      v101 = 256;
      v102 = (char *)v86 - (char *)(lpString2 + 779);
      do
      {
        if ( v101 == -2147483390 )
          break;
        v103 = *(WCHAR *)((char *)v100 + v102);
        if ( !v103 )
          break;
        *v100++ = v103;
        --v101;
      }
      while ( v101 );
      v104 = v100 - 1;
      if ( v101 )
        v104 = v100;
      *v104 = 0;
      v105 = 1;
      *((_BYTE *)lpString2 + 3094) = 0;
    }
    else
    {
      v105 = 0;
    }
    _mm_lfence();
    v106 = -1;
    do
      ++v106;
    while ( v18[v106] );
    v107 = (_WORD *)StrChrW_SYS(v18);
    if ( v107 )
    {
      _mm_lfence();
      *v107 = 0;
      v108 = v107 + 1;
      v109 = -1;
      v17 = 0;
      do
        ++v109;
      while ( v108[v109] );
      if ( (unsigned int)v109 > 0xFF )
        goto LABEL_292;
      v110 = v18;
      if ( !*v18 )
        goto LABEL_292;
      v111 = *v18;
      do
      {
        if ( v111 != 32 )
        {
          v112 = v111;
          if ( v111 != 9 )
            break;
        }
        v112 = *++v110;
        v111 = *v110;
      }
      while ( *v110 );
      if ( !v112 )
        goto LABEL_292;
      _mm_lfence();
      v113 = -1;
      do
        ++v113;
      while ( v108[v113] );
      v114 = StrTrimBothW_Sys(v108, 3);
      v17 = 0;
      if ( v114 )
        goto LABEL_292;
      v115 = *v108;
      if ( !*v108 )
        goto LABEL_215;
      v116 = v108;
      do
      {
        if ( v115 != 32 )
        {
          v117 = v115;
          if ( v115 != 9 )
            break;
        }
        v115 = *++v116;
        v117 = *v116;
      }
      while ( *v116 );
      v15 = 256;
      if ( !v117 )
      {
LABEL_292:
        v7 = 0;
        goto LABEL_296;
      }
      if ( !v105 )
      {
        v118 = lpString2 + 512;
        v119 = 256;
        do
        {
          if ( v119 == -2147483390 )
            break;
          if ( !*v108 )
            break;
          *v118++ = *v108++;
          --v119;
        }
        while ( v119 );
        v120 = v118 - 1;
        if ( v119 )
          v120 = v118;
        *v120 = 0;
      }
    }
LABEL_215:
    v121 = lpString2 + 512;
    if ( !wcscmp_0(L"mssqlserver", lpString2 + 512) )
      goto LABEL_144;
    _mm_lfence();
    v122 = -1;
    do
      ++v122;
    while ( v18[v122] );
    if ( (unsigned int)v122 > 0xFF )
      goto LABEL_144;
    _mm_lfence();
    v7 = 0;
    do
      ++v6;
    while ( v18[v6] );
    if ( (unsigned int)StrTrimBothW_Sys(v18, 3) )
      goto LABEL_296;
    v123 = lpString2 + 256;
    v124 = 256;
    do
    {
      if ( v124 == -2147483390 )
        break;
      v125 = *(WCHAR *)((char *)v123 + (char *)v18 - (char *)(lpString2 + 256));
      if ( !v125 )
        break;
      *v123++ = v125;
      --v124;
    }
    while ( v124 );
    v126 = v123 - 1;
    if ( v124 )
      v126 = v123;
    *v126 = 0;
    v127 = v18;
    if ( !*v18 )
      goto LABEL_240;
    v128 = *v18;
    do
    {
      if ( v128 != 32 )
      {
        v129 = v128;
        if ( v128 != 9 )
          break;
      }
      v129 = *++v127;
      v128 = *v127;
    }
    while ( *v127 );
    v121 = lpString2 + 512;
    if ( v129 && (_mm_lfence(), !IsLocalHost(v18)) )
    {
      v130 = lpString2;
      v131 = (char *)v18 - (char *)lpString2;
      do
      {
        if ( v15 == -2147483390 )
          break;
        v132 = *(WCHAR *)((char *)v130 + v131);
        if ( !v132 )
          break;
        *v130++ = v132;
        --v15;
      }
      while ( v15 );
    }
    else
    {
LABEL_240:
      v133 = wcscmp_0(L"admin", lpString2 + 768);
      v130 = lpString2;
      if ( v133 )
      {
        do
        {
          if ( v15 == -2147483390 )
            break;
          v134 = *(WCHAR *)((char *)v130 + (char *)&gwszComputerName - (char *)lpString2);
          if ( !v134 )
            break;
          *v130++ = v134;
          --v15;
        }
        while ( v15 );
      }
      else
      {
        do
        {
          if ( v15 == -2147483390 )
            break;
          v135 = *(WCHAR *)((char *)v130 + (char *)L"localhost" - (char *)lpString2);
          if ( !v135 )
            break;
          *v130++ = v135;
          --v15;
        }
        while ( v15 );
      }
    }
    v136 = v130 - 1;
    if ( v15 )
      v136 = v130;
    *v136 = 0;
    v137 = lpString2 + 768;
    if ( wcscmp_0(L"lpc", lpString2 + 768) || IsLocalHost(lpString2) )
    {
      v141 = 512;
      v142 = lpString2 + 1035;
      do
      {
        if ( v141 == -2147483134 )
          break;
        v143 = *(v142 - 1035);
        if ( !v143 )
          break;
        *v142++ = v143;
        --v141;
      }
      while ( v141 );
      v144 = v142 - 1;
      if ( v141 )
        v144 = v142;
      *v144 = 0;
      if ( !*v121
        || (StringCchCatW(lpString2 + 1035, 0x200u, L"\\"),
            StringCchCatW(lpString2 + 1035, 0x200u, v121),
            !wcscmp_0(L"lpc", lpString2 + 768))
        || !wcscmp_0(L"admin", lpString2 + 768) )
      {
        *((_BYTE *)lpString2 + 3094) = 0;
      }
      if ( !a3 )
        goto LABEL_291;
      if ( *v137 == 110 && lpString2[769] == 112 && !lpString2[770]
        || !wcscmp_0(L"via", lpString2 + 768)
        || !wcscmp_0(L"lpc", lpString2 + 768)
        || !wcscmp_0(L"admin", lpString2 + 768) )
      {
        v153 = 87;
        v138 = 50149;
        if ( (bidGblFlags & 2) == 0 || !`ConnectParameter::ParseConnectionString'::`212'::_bidPtrSA_030_571[0] )
          goto LABEL_256;
        SniErrorIdFromStringId(0xC3E5u);
        v139 = `ConnectParameter::ParseConnectionString'::`212'::_bidPtrSA_030_571[0];
        v140 = 584704;
        goto LABEL_255;
      }
      if ( *v137 )
        goto LABEL_291;
      v145 = (char *)((char *)L"tcp" - (char *)v137);
      v146 = 11;
      do
      {
        if ( v146 == -2147483635 )
          break;
        v147 = *(WCHAR *)((char *)v137 + (_QWORD)v145);
        if ( !v147 )
          break;
        *v137++ = v147;
        --v146;
      }
      while ( v146 );
      v148 = v137 - 1;
      if ( v146 )
        v148 = v137;
      *v148 = 0;
      if ( v146 )
      {
LABEL_291:
        v153 = 0;
        goto LABEL_296;
      }
      if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`226'::_bidPtrSA_030_583[0] )
      {
        _mm_lfence();
        bidTraceW(
          0,
          596992,
          `ConnectParameter::ParseConnectionString'::`226'::_bidPtrSA_030_583[0],
          v146 == 0 ? 0x8007007A : 0);
      }
      v153 = 87;
      v138 = 50100;
      if ( (bidGblFlags & 2) == 0 || !`ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_586[0] )
        goto LABEL_256;
      SniErrorIdFromStringId(0xC3B4u);
      v139 = `ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_586[0];
      v140 = 600064;
    }
    else
    {
      v138 = 50141;
      if ( (bidGblFlags & 2) == 0 || !`ConnectParameter::ParseConnectionString'::`190'::_bidPtrSA_030_539[0] )
        goto LABEL_256;
      SniErrorIdFromStringId(0xC3DDu);
      v139 = `ConnectParameter::ParseConnectionString'::`190'::_bidPtrSA_030_539[0];
      v140 = 551936;
    }
LABEL_255:
    bidTraceW(0, v140, v139, 9);
LABEL_256:
    SNISetLastError(9, 87, v138);
    v7 = 1;
    goto LABEL_296;
  }
  v38 = lpString2 + 768;
  if ( lpString2[768] )
  {
    if ( *v38 != 110 || lpString2[769] != 112 || lpString2[770] )
      goto LABEL_144;
  }
  else
  {
    v39 = (char *)((char *)L"np" - (char *)v38);
    do
    {
      if ( v21 == -2147483635 )
        break;
      v40 = *(_WORD *)&v39[(_QWORD)v38];
      if ( !v40 )
        break;
      *v38++ = v40;
      --v21;
    }
    while ( v21 );
    v41 = v38 - 1;
    if ( v21 )
      v41 = v38;
    *v41 = 0;
  }
  _mm_lfence();
  v42 = -1;
  do
    ++v42;
  while ( v18[v42] );
  if ( (unsigned int)v42 > 0xFF )
  {
LABEL_144:
    v7 = 0;
    goto LABEL_296;
  }
  _mm_lfence();
  v43 = lpString2 + 779;
  v44 = 256;
  v7 = 0;
  do
  {
    if ( v44 == -2147483390 )
      break;
    v45 = *(WCHAR *)((char *)v43 + (char *)v18 - (char *)(lpString2 + 779));
    if ( !v45 )
      break;
    *v43++ = v45;
    --v44;
  }
  while ( v44 );
  v46 = v43 - 1;
  if ( v44 )
    v46 = v43;
  *v46 = 0;
  v47 = (char *)(v18 + 2);
  v48 = -1;
  do
    ++v48;
  while ( *(_WORD *)&v47[2 * v48] );
  v49 = (_WORD *)StrChrW_SYS(v18 + 2);
  v50 = v49;
  if ( !v49 )
    goto LABEL_296;
  *v49 = 0;
  v17 = (__int64)(v18 + 2);
  if ( !*(_WORD *)v47 )
    goto LABEL_296;
  v51 = *(_WORD *)v47;
  do
  {
    if ( v51 != 32 )
    {
      v52 = v51;
      if ( v51 != 9 )
        break;
    }
    v17 += 2;
    v52 = *(_WORD *)v17;
    v51 = *(_WORD *)v17;
  }
  while ( *(_WORD *)v17 );
  v53 = -1;
  if ( !v52 )
    goto LABEL_296;
  _mm_lfence();
  v54 = lpString2 + 256;
  v55 = 256;
  do
  {
    if ( v55 == -2147483390 )
      break;
    v56 = *(WCHAR *)((char *)v54 + v47 - (char *)(lpString2 + 256));
    if ( !v56 )
      break;
    *v54++ = v56;
    --v55;
  }
  while ( v55 );
  v57 = v54 - 1;
  if ( v55 )
    v57 = v54;
  *v57 = 0;
  v58 = IsLocalHost(v18 + 2);
  v59 = lpString2;
  if ( v58 )
  {
    v60 = 256;
    do
    {
      if ( v60 == -2147483390 )
        break;
      v61 = *(WCHAR *)((char *)v59 + (char *)&gwszComputerName - (char *)lpString2);
      if ( !v61 )
        break;
      *v59++ = v61;
      --v60;
    }
    while ( v60 );
    v62 = v59 - 1;
    if ( v60 )
      v62 = v59;
    *v62 = 0;
  }
  else
  {
    v63 = 256;
    v64 = v47 - (char *)lpString2;
    do
    {
      if ( v63 == -2147483390 )
        break;
      v65 = *(WCHAR *)((char *)v59 + v64);
      if ( !v65 )
        break;
      *v59++ = v65;
      --v63;
    }
    while ( v63 );
    v66 = v59 - 1;
    if ( v63 )
      v66 = v59;
    *v66 = 0;
    if ( !v63 )
      goto LABEL_296;
  }
  _mm_lfence();
  v67 = v50 + 1;
  v68 = -1;
  do
    ++v68;
  while ( v67[v68] );
  v69 = StrChrW_SYS(v67);
  if ( !v69 )
    goto LABEL_296;
  _mm_lfence();
  v70 = (const WCHAR *)(v69 + 2);
  v71 = -1;
  do
    ++v71;
  while ( v70[v71] );
  if ( CompareStringW(0x800u, 0, v70, v71, L"sql\\query", 9) == 2 )
  {
    lpString2[512] = 0;
LABEL_143:
    *((_BYTE *)lpString2 + 3094) = 0;
    v153 = 0;
    goto LABEL_144;
  }
  _mm_lfence();
  v72 = CompareStringW(0x800u, 0, v70, 6, L"mssql$", 6);
  _mm_lfence();
  if ( v72 != 2 )
  {
    v84 = lpString2 + 512;
    goto LABEL_141;
  }
  v73 = -1;
  do
    ++v73;
  while ( v70[v73] );
  v74 = StrChrW_SYS(v70);
  v75 = (_WORD *)v74;
  if ( !v74 )
  {
LABEL_293:
    v7 = 0;
    goto LABEL_296;
  }
  _mm_lfence();
  v76 = (const WCHAR *)(v74 + 2);
  v77 = -1;
  do
    ++v77;
  while ( v76[v77] );
  v78 = lpString2 + 512;
  v79 = CompareStringW(0x800u, 0, v76, v77, L"sql\\query", 9);
  _mm_lfence();
  if ( v79 != 2 )
  {
    v84 = lpString2 + 512;
LABEL_141:
    v7 = 0;
    if ( (int)StringCchPrintf_lW(v84, 0x100u, L"pipe%s", 0, v70) < 0 )
      goto LABEL_296;
    *((_BYTE *)lpString2 + 3095) = 0;
    goto LABEL_143;
  }
  v7 = 0;
  do
    ++v53;
  while ( v70[v53] );
  v80 = StrChrW_SYS(v70);
  *v75 = 0;
  v81 = v80 - (_QWORD)v78;
  do
  {
    if ( v15 == -2147483390 )
      break;
    v82 = *(WCHAR *)((char *)v78 + v81 + 2);
    if ( !v82 )
      break;
    *v78++ = v82;
    --v15;
  }
  while ( v15 );
  v83 = v78 - 1;
  if ( v15 )
    v83 = v78;
  *v83 = 0;
  if ( v15 )
    goto LABEL_143;
LABEL_296:
  ((void (__fastcall *)(struct IMalloc *, wchar_t *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, Str, v17);
  if ( !v153 )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && `ConnectParameter::ParseConnectionString'::`257'::_bidPtrSA_030_626[0] )
      bidTraceW(0, 641024, `ConnectParameter::ParseConnectionString'::`257'::_bidPtrSA_030_626[0], lpString2 + 768);
    goto LABEL_306;
  }
  if ( v7 )
  {
LABEL_306:
    v12 = v153;
    goto LABEL_307;
  }
  if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`248'::_bidPtrSA_030_604[0] )
  {
    v12 = v153;
    SniErrorIdFromStringId(0xC3CDu);
    bidTraceW(0, 618496, `ConnectParameter::ParseConnectionString'::`248'::_bidPtrSA_030_604[0], 9);
  }
  else
  {
    v12 = v153;
  }
  SNISetLastError(9, v12, 50125);
LABEL_307:
  if ( (bidGblFlags & 0x20002) == 0x20002 && `ConnectParameter::ParseConnectionString'::`264'::_bidPtrSA_030_629[0] )
  {
    v13 = `ConnectParameter::ParseConnectionString'::`264'::_bidPtrSA_030_629[0];
    v14 = 644096;
    goto LABEL_310;
  }
LABEL_311:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v151);
  return v12;
}

```

## disassembly

```asm
0x10041470c  mov     r11, rsp
0x10041470f  mov     [r11+18h], r8b
0x100414713  push    rbp
0x100414714  push    rsi
0x100414715  push    rdi
0x100414716  push    r12
0x100414718  push    r13
0x10041471a  push    r14
0x10041471c  push    r15
0x10041471e  sub     rsp, 90h
0x100414725  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x10041472d  mov     [r11+10h], rbx
0x100414731  mov     bl, r8b
0x100414734  mov     rsi, rdx
0x100414737  mov     rdi, rcx
0x10041473a  or      r13, 0FFFFFFFFFFFFFFFFh
0x10041473e  mov     [r11-50h], r13
0x100414742  mov     eax, cs:_bidGblFlags
0x100414748  mov     ecx, 20004h
0x10041474d  and     eax, ecx
0x10041474f  xor     r15d, r15d
0x100414752  cmp     eax, ecx
0x100414754  jnz     short loc_100414775
0x100414756  mov     rax, cs:?_bidPtrSA_040_117@?6??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`7'::_bidPtrSA_040_117
0x10041475d  test    rax, rax
0x100414760  jz      short loc_100414775
0x100414762  mov     r8, rdx
0x100414765  mov     rdx, cs:?_bidPtrSA_040_117@?6??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`7'::_bidPtrSA_040_117
0x10041476c  lea     rcx, [r11-50h]
0x100414770  call    _bidScopeEnterW
0x100414775  mov     r12d, r15d
0x100414778  mov     [rsp+0C8h+arg_0], r15d
0x100414780  mov     [rdi+0C18h], bl
0x100414786  cmp     [rdi+0C16h], r15b
0x10041478d  jz      short loc_100414795
0x10041478f  test    bl, bl
0x100414791  mov     al, 1
0x100414793  jz      short loc_100414798
0x100414795  mov     al, r15b
0x100414798  mov     [rdi+0C16h], al
0x10041479e  mov     rbx, r13
0x1004147a1  inc     rbx
0x1004147a4  cmp     [rsi+rbx*2], r15w
0x1004147a9  jnz     short loc_1004147A1
0x1004147ab  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004147b2  lea     ebp, [rbx+1]
0x1004147b5  mov     r14d, ebp
0x1004147b8  mov     eax, 2
0x1004147bd  mul     r14
0x1004147c0  mov     rdx, rax
0x1004147c3  cmovo   rdx, r13
0x1004147c7  mov     rax, [rcx]
0x1004147ca  mov     rax, [rax+70h]
0x1004147ce  call    cs:__guard_dispatch_icall_fptr
0x1004147d4  mov     [rsp+0C8h+Str], rax
0x1004147d9  test    rax, rax
0x1004147dc  jnz     loc_100414869
0x1004147e2  mov     ebx, 0C3B4h
0x1004147e7  lea     edi, [rax+0Eh]
0x1004147ea  lea     esi, [rax+9]
0x1004147ed  test    byte ptr cs:_bidGblFlags, 2
0x1004147f4  jz      short loc_100414827
0x1004147f6  mov     rax, cs:?_bidPtrSA_030_137@?BE@??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`20'::_bidPtrSA_030_137
0x1004147fd  test    rax, rax
0x100414800  jz      short loc_100414827
0x100414802  mov     ecx, ebx; unsigned int
0x100414804  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100414809  mov     [rsp+0C8h+cchDest], edi
0x10041480d  mov     dword ptr [rsp+0C8h+lpDestStr], eax
0x100414811  mov     r9d, esi
0x100414814  mov     r8, cs:?_bidPtrSA_030_137@?BE@??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`20'::_bidPtrSA_030_137
0x10041481b  mov     edx, 22400h
0x100414820  xor     ecx, ecx
0x100414822  call    _bidTraceW
0x100414827  mov     r8d, ebx
0x10041482a  mov     edx, edi
0x10041482c  mov     ecx, esi
0x10041482e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100414833  mov     eax, cs:_bidGblFlags
0x100414839  mov     ebx, 20002h
0x10041483e  and     eax, ebx
0x100414840  cmp     eax, ebx
0x100414842  jnz     loc_100415890
0x100414848  mov     rax, cs:?_bidPtrSA_030_139@?BL@??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`27'::_bidPtrSA_030_139
0x10041484f  test    rax, rax
0x100414852  jz      loc_100415890
0x100414858  mov     r8, cs:?_bidPtrSA_030_139@?BL@??ParseConnectionString@ConnectParameter@@QEAAKPEBG_N@Z@4REBGEB; ushort const * const `ConnectParameter::ParseConnectionString(ushort const *,bool)'::`27'::_bidPtrSA_030_139
0x10041485f  mov     edx, 22C00h
0x100414864  jmp     loc_100415885
0x100414869  mov     [rsp+0C8h+arg_18], 57h ; 'W'
0x100414874  mov     [rsp+0C8h+cchDest], ebp; cchDest
0x100414878  mov     [rsp+0C8h+lpDestStr], rax; lpDestStr
0x10041487d  mov     r9d, r13d; cchSrc
0x100414880  mov     r8, rsi; lpSrcStr
0x100414883  mov     r15d, 100h
0x100414889  mov     edx, r15d; dwMapFlags
0x10041488c  mov     ecx, 800h; Locale
0x100414891  call    cs:__imp_LCMapStringW
0x100414897  xor     ecx, ecx
0x100414899  test    eax, eax
0x10041489b  jz      loc_100415742
0x1004148a1  cmp     eax, ebp
0x1004148a3  ja      loc_100415742
0x1004148a9  lfence
0x1004148ac  mov     eax, ebx
0x1004148ae  mov     rsi, [rsp+0C8h+Str]
0x1004148b3  mov     [rsi+rax*2], cx
0x1004148b7  mov     dword ptr [rsp+0C8h+lpDestStr], 3; int
0x1004148bf  lea     r9, sz; " \t"
0x1004148c6  xor     r8d, r8d
0x1004148c9  mov     rdx, r14
0x1004148cc  mov     rcx, rsi; S2
0x1004148cf  call    StrTrimBothW_Sys
0x1004148d4  test    eax, eax
0x1004148d6  jnz     loc_100415742
0x1004148dc  lfence
0x1004148df  mov     r14, rsi
0x1004148e2  mov     [rsp+0C8h+var_58], rsi
0x1004148e7  lea     ebp, [rax+3Ah]
0x1004148ea  mov     edx, ebp; Ch
0x1004148ec  mov     rcx, rsi; Str
0x1004148ef  call    cs:__imp_wcschr
0x1004148f5  mov     r12, rax
0x1004148f8  lea     ebx, [rbp-2Fh]
0x1004148fb  lea     r9, aTcp_1; "tcp"
0x100414902  xor     r10d, r10d
0x100414905  test    rax, rax
0x100414908  jz      loc_100414B57
0x10041490e  mov     [rax], r10w
0x100414912  mov     rcx, rax
0x100414915  sub     rcx, rsi
0x100414918  and     rcx, 0FFFFFFFFFFFFFFFEh
0x10041491c  cmp     rcx, 14h
0x100414920  jg      loc_10041573F
0x100414926  lea     rsi, [rdi+600h]
0x10041492d  mov     edx, ebx
0x10041492f  mov     rcx, rsi
0x100414932  mov     r8, r14
0x100414935  sub     r8, rsi
0x100414938  lea     rax, [rdx+7FFFFFF3h]
0x10041493f  test    rax, rax
0x100414942  jz      short loc_10041495B
0x100414944  movzx   eax, word ptr [rcx+r8]
0x100414949  test    ax, ax
0x10041494c  jz      short loc_10041495B
0x10041494e  mov     [rcx], ax
0x100414951  add     rcx, 2
0x100414955  sub     rdx, 1
0x100414959  jnz     short loc_100414938
0x10041495b  lea     rax, [rcx-2]
0x10041495f  test    rdx, rdx
0x100414962  cmovnz  rax, rcx
0x100414966  mov     [rax], r10w
0x10041496a  mov     rax, r13
0x10041496d  inc     rax
0x100414970  cmp     [rsi+rax*2], r10w
0x100414975  jnz     short loc_10041496D
0x100414977  lea     r15d, [rax+1]
0x10041497b  movzx   eax, word ptr [rsi]
0x10041497e  test    ax, ax
0x100414981  jz      loc_100414AA0
0x100414987  cmp     r10w, [rsi+r15*2-2]
0x10041498d  jnz     loc_10041573F
0x100414993  mov     r14, rsi
0x100414996  mov     rbx, r10
0x100414999  movzx   r8d, ax
0x10041499d  mov     edx, 3
0x1004149a2  lea     rcx, sz; " \t"
0x1004149a9  call    StrChrW_SYS
0x1004149ae  xor     esi, esi
0x1004149b0  test    rax, rax
0x1004149b3  jz      short loc_1004149C4
0x1004149b5  mov     rax, r14
0x1004149b8  test    rbx, rbx
0x1004149bb  cmovnz  rax, rbx
0x1004149bf  mov     rbx, rax
0x1004149c2  jmp     short loc_1004149C7
0x1004149c4  mov     rbx, rsi
0x1004149c7  mov     rcx, r14; lpsz
0x1004149ca  call    cs:__imp_CharNextW
0x1004149d0  mov     r14, rax
0x1004149d3  movzx   eax, word ptr [rax]
0x1004149d6  xor     r10d, r10d
0x1004149d9  test    ax, ax
0x1004149dc  jnz     short loc_100414999
0x1004149de  test    rbx, rbx
0x1004149e1  lea     rsi, [rdi+600h]
0x1004149e8  jz      short loc_100414A05
0x1004149ea  mov     rbp, rbx
0x1004149ed  sub     rbp, rsi
0x1004149f0  sar     rbp, 1
0x1004149f3  inc     rbp
0x1004149f6  cmp     rbp, r15
0x1004149f9  jnb     loc_10041573F
0x1004149ff  mov     [rbx], r10w
0x100414a03  jmp     short loc_100414A08
0x100414a05  mov     rbp, r15
0x100414a08  mov     r14, rsi
0x100414a0b  movzx   eax, word ptr [rsi]
0x100414a0e  test    ax, ax
0x100414a11  jz      short loc_100414A8C
0x100414a13  cmp     r10w, [rsi+rbp*2-2]
0x100414a19  jnz     loc_10041573F
0x100414a1f  movzx   r8d, ax
0x100414a23  mov     edx, 3
0x100414a28  lea     rcx, sz; " \t"
0x100414a2f  call    StrChrW_SYS
0x100414a34  xor     r10d, r10d
0x100414a37  test    rax, rax
0x100414a3a  jz      short loc_100414A53
0x100414a3c  mov     rcx, r14; lpsz
0x100414a3f  call    cs:__imp_CharNextW
0x100414a45  mov     r14, rax
0x100414a48  movzx   eax, word ptr [rax]
0x100414a4b  xor     r10d, r10d
0x100414a4e  test    ax, ax
0x100414a51  jnz     short loc_100414A1F
0x100414a53  cmp     r14, rsi
0x100414a56  jz      short loc_100414A8C
0x100414a58  mov     rax, r14
0x100414a5b  sub     rax, rsi
0x100414a5e  sar     rax, 1
0x100414a61  cmp     rax, rbp
0x100414a64  jnb     loc_100414F6F
0x100414a6a  lfence
0x100414a6d  mov     rbx, rbp
0x100414a70  sub     rbx, rax
0x100414a73  mov     r9, rbx; N
0x100414a76  mov     r8, r14; S2
0x100414a79  mov     rdx, rbp; N1
0x100414a7c  mov     rcx, rsi; S1
0x100414a7f  call    wmemmove_s_0
0x100414a84  xor     r10d, r10d
0x100414a87  mov     [rsi+rbx*2], r10w
0x100414a8c  mov     r14, [rsp+0C8h+var_58]
0x100414a91  mov     ebx, 0Bh
0x100414a96  lea     r9, aTcp_1; "tcp"
0x100414a9d  lea     ebp, [rbx+2Fh]
0x100414aa0  cmp     r12, [rsp+0C8h+Str]
0x100414aa5  jz      loc_100414B48
0x100414aab  mov     rdx, rsi; String2
0x100414aae  mov     rcx, r9; String1
0x100414ab1  call    wcscmp_0
0x100414ab6  xor     r10d, r10d
0x100414ab9  test    eax, eax
0x100414abb  jz      short loc_100414B03
0x100414abd  lea     eax, [r10+6Eh]
0x100414ac1  cmp     ax, [rsi]
0x100414ac4  jnz     short loc_100414AD7
0x100414ac6  lea     eax, [r10+70h]
0x100414aca  cmp     ax, [rsi+2]
0x100414ace  jnz     short loc_100414AD7
0x100414ad0  cmp     r10w, [rsi+4]
0x100414ad5  jz      short loc_100414B03
0x100414ad7  mov     rdx, rsi; String2
0x100414ada  lea     rcx, aLpc; "lpc"
0x100414ae1  call    wcscmp_0
0x100414ae6  xor     r10d, r10d
0x100414ae9  test    eax, eax
0x100414aeb  jz      short loc_100414B03
0x100414aed  mov     rdx, rsi; String2
0x100414af0  lea     rcx, aAdmin; "admin"
0x100414af7  call    wcscmp_0
0x100414afc  xor     r10d, r10d
0x100414aff  test    eax, eax
0x100414b01  jnz     short loc_100414B48
0x100414b03  lfence
0x100414b06  lea     r14, [r12+2]
0x100414b0b  mov     rax, r13
0x100414b0e  inc     rax
0x100414b11  cmp     [r14+rax*2], r10w
0x100414b16  jnz     short loc_100414B0E
0x100414b18  lea     edx, [rax+1]
0x100414b1b  mov     dword ptr [rsp+0C8h+lpDestStr], 3; int
0x100414b23  lea     r9, sz; " \t"
0x100414b2a  xor     r8d, r8d
0x100414b2d  mov     rcx, r14; S2
0x100414b30  call    StrTrimBothW_Sys
0x100414b35  xor     r12d, r12d
0x100414b38  test    eax, eax
0x100414b3a  jnz     loc_100415742
0x100414b40  mov     r15d, 100h
0x100414b46  jmp     short loc_100414B5A
0x100414b48  mov     [r12], bp
0x100414b4d  mov     [rsi], r10w
0x100414b51  mov     r15d, 100h
0x100414b57  xor     r12d, r12d
0x100414b5a  lfence
0x100414b5d  mov     [rsp+0C8h+cchDest], 2; cchCount2
0x100414b65  lea     rax, asc_100559CFC; "\\\\"
0x100414b6c  mov     [rsp+0C8h+lpDestStr], rax; lpString2
0x100414b71  mov     r9d, 2; cchCount1
0x100414b77  mov     r8, r14; lpString1
0x100414b7a  xor     edx, edx; dwCmpFlags
0x100414b7c  mov     ecx, 800h; Locale
0x100414b81  call    cs:__imp_CompareStringW
0x100414b87  cmp     eax, 2
0x100414b8a  jnz     loc_100414F7C
0x100414b90  lea     rcx, [rdi+600h]
0x100414b97  cmp     [rcx], r12w
  ... truncated ...
```
