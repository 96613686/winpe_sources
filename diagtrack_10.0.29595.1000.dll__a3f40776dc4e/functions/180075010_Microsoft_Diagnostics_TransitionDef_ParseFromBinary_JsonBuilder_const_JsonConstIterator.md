# Microsoft::Diagnostics::TransitionDef::ParseFromBinary(JsonBuilder const &,JsonConstIterator)

- ea: `0x180075010`
- end: `0x18007611c`
- name: `?ParseFromBinary@TransitionDef@Diagnostics@Microsoft@@UEAAXAEBVJsonBuilder@@VJsonConstIterator@@@Z`
- size: `4364`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180023fdc`
- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x18002df70`
- `0x18006652c`
- `0x18006888c`
- `0x18006f244`
- `0x18006f2ac`
- `0x18006f644`
- `0x180073a50`
- `0x180073c80`
- `0x180073d24`
- `0x180075010`
- `0x180076200`
- `0x180076774`
- `0x1800781b0`
- `0x1800797b4`
- `0x18007af20`
- `0x18007afd0`
- `0x18007b0b8`
- `0x18007d47c`
- `0x18007e1f8`
- `0x1800afab0`
- `0x1800c0cf4`
- `0x180112ba0`
- `0x1801a9494`
- `0x1801b7bd0`
- `0x1801c90e0`
- `0x18020aac0`
- `0x18020b8d6`
- `0x18020bae8`
- `0x1802be760`
- `0x1802c33dc`
- `0x1802c3470`
- `0x1802c3a24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800757fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007582d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180075857`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800757fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18007582d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180075857`

## string_xrefs

- `0x1800756ab`: `onecore\base\telemetry\utc\service\include\scenarios\ScenarioObjectCache.h`
- `0x180075a67`: `onecore\base\telemetry\utc\service\include\scenarios\ScenarioObjectCache.h`
- `0x180075acd`: `onecore\base\telemetry\utc\service\include\scenarios\ScenarioObjectCache.h`
- `0x180075ae8`: `onecore\base\telemetry\utc\service\include\scenarios\ScenarioObjectCache.h`
- `0x180075b03`: `onecore\base\telemetry\utc\service\include\scenarios\ScenarioObjectCache.h`
- `0x180075874`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075983`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800759e5`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800759fd`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075a15`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075a4f`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075d37`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075dd9`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075e41`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075e7c`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075ee0`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075f0f`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075fb0`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x180075fcf`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::TransitionDef::ParseFromBinary(__int64 a1, __int64 *a2, __int64 **a3)
{
  __int64 **v3; // r12
  __int64 v5; // r13
  __int64 v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int i; // r8d
  int *v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r10
  const wchar_t *v13; // r11
  _WORD *v14; // rbx
  int *v15; // r9
  unsigned __int64 v16; // r8
  char v17; // al
  _QWORD *v18; // rdx
  unsigned int v19; // r9d
  int v20; // esi
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int j; // edx
  __int64 v24; // r10
  const wchar_t *v25; // r11
  _WORD *v26; // rbx
  __int64 *v27; // r15
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  unsigned int kk; // r8d
  __int64 v32; // r10
  const wchar_t *v33; // r11
  _WORD *v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // rdx
  unsigned int i1; // edx
  int *v38; // r8
  __int64 v39; // r9
  const wchar_t *v40; // r10
  _WORD *v41; // r11
  wil::details::in1diag3 *v42; // r10
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  unsigned int i2; // r8d
  __int64 v47; // r10
  const wchar_t *v48; // r11
  _WORD *v49; // rbx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 i3; // r8
  unsigned int *v53; // rdx
  __int64 v54; // r9
  const wchar_t *v55; // r10
  _WORD *v56; // r11
  char v57; // al
  char v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  int v62; // ebx
  unsigned int i4; // edx
  int *v64; // r8
  __int64 v65; // r9
  const wchar_t *v66; // r10
  _WORD *v67; // r11
  __int64 v68; // rdx
  wil::details::in1diag3 *v69; // r10
  JsonBuilder *v71; // r10
  __int64 v72; // rdx
  __int64 v73; // r8
  unsigned int *k; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  unsigned int *m; // rdx
  __int64 v78; // rbx
  __int64 v79; // rcx
  __int64 v80; // rdx
  unsigned int *n; // r8
  unsigned int *v82; // rax
  __int64 v83; // r12
  __int64 v84; // r13
  __int64 v85; // rbx
  unsigned __int64 v86; // rsi
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // r8
  unsigned int *ii; // rcx
  unsigned __int64 v95; // rax
  char v96; // dl
  __int64 v97; // rax
  char v98; // cl
  __int16 v99; // dx
  unsigned int *jj; // rcx
  char v101; // al
  __int64 Unchecked; // rax
  char v103; // al
  double v104; // xmm0_8
  unsigned __int64 v105; // rcx
  double v106; // xmm0_8
  unsigned __int64 v107; // rcx
  JsonBuilder *v108; // r12
  unsigned int mm; // ebx
  __int64 v110; // rcx
  __int16 v111; // r10
  unsigned int nn; // esi
  wil::details::in1diag3 *v113; // r10
  wil::details::in1diag3 *v114; // r10
  JsonBuilder *v115; // rsi
  unsigned int Index; // ebx
  __int64 v117; // r14
  __int64 v118; // r15
  __int64 v119; // r9
  __int64 v120; // r9
  __int64 v121; // rdx
  char v122; // r11
  int v123; // [rsp+20h] [rbp-E0h]
  _BYTE *v124; // [rsp+20h] [rbp-E0h]
  _BYTE v125[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v126; // [rsp+34h] [rbp-CCh] BYREF
  JsonBuilder *v127; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v128[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v129[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v130; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v131; // [rsp+60h] [rbp-A0h] BYREF
  JsonBuilder *v132; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v133; // [rsp+78h] [rbp-88h]
  __int128 v134; // [rsp+80h] [rbp-80h] BYREF
  JsonBuilder *v135; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v136; // [rsp+98h] [rbp-68h]
  __int128 v137; // [rsp+A0h] [rbp-60h] BYREF
  char v138; // [rsp+B8h] [rbp-48h]
  char v139; // [rsp+B9h] [rbp-47h]
  __int64 v140; // [rsp+C0h] [rbp-40h]
  __int64 v141; // [rsp+C8h] [rbp-38h]
  __int64 **v142; // [rsp+D0h] [rbp-30h]
  _QWORD v143[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v144[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v146[4]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v3 = a3;
  v142 = a3;
  v5 = a1;
  v140 = a1;
  std::wstring::wstring(v146);
  if ( *v3 != a2 )
    __int2c();
  if ( !*((_DWORD *)a2 + 2) )
    goto LABEL_121;
  v6 = *((unsigned int *)v3 + 2);
  v141 = v6;
  v7 = *a2;
  if ( *(_BYTE *)(*a2 + 4 * v6 + 7) < 0xFEu )
    goto LABEL_121;
  v8 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v7 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
  if ( (_DWORD)v8 == *(_DWORD *)(v7 + 4 * v6 + 8) )
    goto LABEL_121;
  for ( i = *(_DWORD *)(v7 + 4 * v8); ; i = *v10 )
  {
    v10 = (int *)(v7 + 4LL * i);
    if ( *((_BYTE *)v10 + 7) != 0xFD )
    {
      v11 = v10[1] & 0xFFFFFF;
      if ( v11 == 2 )
        break;
    }
LABEL_13:
    if ( i == *(_DWORD *)(v7 + 4 * v6 + 8) )
      goto LABEL_121;
  }
  v12 = 2;
  v13 = L"tn";
  v14 = v10 + 3;
  while ( v12 )
  {
    if ( *v14 != *v13 )
      goto LABEL_13;
    --v12;
    ++v14;
    ++v13;
  }
  if ( !i )
LABEL_121:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\scenarios\\ScenarioObjectCache.h",
      (const char *)0x87C52501LL,
      v123);
  if ( *((_BYTE *)v10 + 7) == 0xF5 )
  {
    v15 = &v10[(unsigned __int64)(2 * v11 + 15) >> 2];
    v16 = (unsigned __int64)(unsigned int)v10[2] >> 1;
    v17 = 0;
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v17 = 1;
  }
  if ( v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3EF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\scenarios\\ScenarioObjectCache.h",
      (const char *)0x87C52502LL,
      v123);
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  std::wstring::_Construct<1,wchar_t *>(pExceptionObject, v15, v16);
  std::wstring::_Tidy_deallocate(v146);
  std::wstring::_Take_contents(v146, pExceptionObject);
  std::wstring::_Tidy_deallocate(pExceptionObject);
  v18 = v146;
  if ( v146[3] > 7u )
    v18 = (_QWORD *)v146[0];
  std::wstring::_Assign<wchar_t>(v5 + 16, v18, v146[2]);
  *(_QWORD *)(v5 + 48) = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)(v5 + 16));
  v134 = *(_OWORD *)&off_18036AE78;
  v131 = *(_OWORD *)v3;
  Microsoft::Diagnostics::ScenarioObjectCache::DeserializeDbKey(
    (_DWORD)a2,
    (unsigned int)&v131,
    v5 + 56,
    (unsigned int)&v134,
    0);
  if ( *v3 != a2 )
    __int2c();
  v19 = 0;
  v20 = *((_DWORD *)a2 + 2);
  if ( v20 )
  {
    v21 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v6 + 7) >= 0xFEu )
    {
      v22 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v21 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
      if ( (_DWORD)v22 != *(_DWORD *)(v21 + 4 * v6 + 8) )
      {
        for ( j = *(_DWORD *)(v21 + 4 * v22); ; j = *(_DWORD *)(v21 + 4LL * j) )
        {
          if ( *(_BYTE *)(v21 + 4LL * j + 7) != 0xFD )
          {
            v24 = 2;
            if ( (*(_DWORD *)(v21 + 4LL * j + 4) & 0xFFFFFF) == 2 )
              break;
          }
LABEL_33:
          if ( j == *(_DWORD *)(v21 + 4 * v6 + 8) )
            goto LABEL_36;
        }
        v25 = L"fs";
        v26 = (_WORD *)(v21 + 12 + 4LL * j);
        while ( v24 )
        {
          if ( *v26 != *v25 )
            goto LABEL_33;
          --v24;
          ++v26;
          ++v25;
        }
        v19 = j;
      }
    }
  }
LABEL_36:
  v27 = a2;
  *(_QWORD *)&v130 = a2;
  DWORD2(v130) = v19;
  if ( v19 )
  {
    v71 = (JsonBuilder *)v19;
    v132 = (JsonBuilder *)v19;
    v72 = *a2;
    if ( *(_BYTE *)(*a2 + 4LL * v19 + 7) != 0xFE )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C52502LL,
        (int)v124);
    v73 = 0;
    if ( v20 )
    {
      v73 = *(unsigned int *)(v72 + 4LL * (v19 + ((2 * (*(_DWORD *)(v72 + 4LL * v19 + 4) & 0xFFFFFFu) + 15) >> 2)));
      for ( k = (unsigned int *)(v72 + 4 * v73); *((_BYTE *)k + 7) == 0xFD; k = (unsigned int *)(v72 + 4 * v73) )
        v73 = *k;
    }
LABEL_125:
    LODWORD(v75) = 0;
    if ( *((_DWORD *)a2 + 2) )
    {
      v76 = *a2;
      if ( *(_BYTE *)(*a2 + 4LL * (_QWORD)v71 + 7) >= 0xFEu )
      {
        v75 = *(unsigned int *)(v76 + 4LL * *(unsigned int *)(v76 + 4LL * (_QWORD)v71 + 8));
        for ( m = (unsigned int *)(v76 + 4 * v75); *((_BYTE *)m + 7) == 0xFD; m = (unsigned int *)(v76 + 4 * v75) )
          v75 = *m;
      }
    }
    if ( (_DWORD)v73 == (_DWORD)v75 )
    {
      v6 = v141;
      v27 = (__int64 *)v130;
      v3 = v142;
      goto LABEL_37;
    }
    v78 = (unsigned int)v73;
    v135 = (JsonBuilder *)(unsigned int)v73;
    v79 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v73 + 7) != 0xFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C52502LL,
        (int)v124);
    v125[0] = 0;
    LOWORD(v127) = 0;
    *(_QWORD *)v128 = 0;
    if ( *((_DWORD *)a2 + 2) )
    {
      v80 = *(unsigned int *)(v79
                            + 4LL * ((unsigned int)v73 + ((2 * (*(_DWORD *)(v79 + 4 * v73 + 4) & 0xFFFFFFu) + 15) >> 2)));
      for ( n = (unsigned int *)(v79 + 4 * v80); *((_BYTE *)n + 7) == 0xFD; n = (unsigned int *)(v79 + 4LL * *n) )
        LODWORD(v80) = *n;
      v82 = (unsigned int *)(v79 + 4LL * *(unsigned int *)(v79 + 4LL * *(unsigned int *)(v79 + 4 * v78 + 8)));
      if ( *((_BYTE *)v82 + 7) == 0xFD )
      {
        do
        {
          v83 = *v82;
          v82 = (unsigned int *)(v79 + 4 * v83);
        }
        while ( *((_BYTE *)v82 + 7) == 0xFD );
      }
      else
      {
        LODWORD(v83) = *(_DWORD *)(v79 + 4LL * *(unsigned int *)(v79 + 4 * v78 + 8));
      }
    }
    else
    {
      LODWORD(v80) = 0;
      LODWORD(v83) = 0;
    }
    while ( 1 )
    {
      if ( (_DWORD)v80 == (_DWORD)v83 )
      {
        v5 = v140;
        std::vector<std::pair<bool,Microsoft::Diagnostics::ScenarioDbLookupPair>>::emplace_back<bool &,Microsoft::Diagnostics::ScenarioDbLookupPair>(
          v140 + 72,
          v125,
          &v127);
        v73 = *(unsigned int *)(*a2 + 4LL * (_QWORD)v135);
        for ( ii = (unsigned int *)(*a2 + 4 * v73); *((_BYTE *)ii + 7) == 0xFD; ii = (unsigned int *)(*a2 + 4 * v73) )
          v73 = *ii;
        v71 = v132;
        goto LABEL_125;
      }
      v84 = (unsigned int)v80;
      v85 = *a2 + 4LL * (unsigned int)v80;
      v86 = *(_DWORD *)(v85 + 4) & 0xFFFFFF;
      v87 = 3;
      if ( v86 <= 3 )
        v87 = (unsigned int)v86;
      if ( (unsigned int)_o__wcsnicmp(v85 + 12, L"str", v87) || (_DWORD)v86 != 3 )
        break;
      if ( *(_BYTE *)(v85 + 7) == 0xF9 )
      {
        v125[0] = JsonImplementType<bool>::GetUnchecked(v85, v88, v89, v90);
        v101 = 0;
      }
      else
      {
        v125[0] = 0;
        v101 = 1;
      }
      if ( v101 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52502LL,
          (int)v124);
LABEL_158:
      v80 = *(unsigned int *)(*a2 + 4 * v84);
      for ( jj = (unsigned int *)(*a2 + 4 * v80); *((_BYTE *)jj + 7) == 0xFD; jj = (unsigned int *)(*a2 + 4 * v80) )
        v80 = *jj;
    }
    v91 = v86;
    if ( v86 > 2 )
      v91 = 2;
    if ( (unsigned int)_o__wcsnicmp(v85 + 12, L"ty", v91) || (_DWORD)v86 != 2 )
    {
      v93 = 1;
      if ( v86 <= 1 )
        v93 = v86;
      if ( (unsigned int)_o__wcsnicmp(v85 + 12, L"h", v93) || (_DWORD)v86 != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52500LL,
          (int)v124);
      if ( *(unsigned __int8 *)(v85 + 7) == 246 )
      {
        Unchecked = JsonImplementType<unsigned __int64>::GetUnchecked(v85);
        goto LABEL_169;
      }
      if ( *(unsigned __int8 *)(v85 + 7) == 247 )
      {
        *(_QWORD *)v128 = JsonImplementType<__int64>::GetUnchecked(v85);
        if ( *(_QWORD *)v128 >= 0x8000000000000000uLL )
          goto LABEL_196;
LABEL_170:
        v103 = 0;
      }
      else
      {
        if ( *(unsigned __int8 *)(v85 + 7) == 248 )
        {
          v106 = JsonImplementType<double>::GetUnchecked(v85);
          if ( v106 >= *(double *)&`Microsoft::Diagnostics::FileWrapStream::SetSize'::`2'::zeroDisplacement.QuadPart
            && v106 < 1.844674407370955e19 )
          {
            v107 = 0;
            if ( v106 >= 9.223372036854776e18 )
            {
              v106 = v106 - 9.223372036854776e18;
              if ( v106 < 9.223372036854776e18 )
                v107 = 0x8000000000000000uLL;
            }
            Unchecked = v107 + (unsigned int)(int)v106;
LABEL_169:
            *(_QWORD *)v128 = Unchecked;
            goto LABEL_170;
          }
        }
LABEL_196:
        *(_QWORD *)v128 = 0;
        v103 = 1;
      }
      if ( v103 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x165,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52502LL,
          (int)v124);
      goto LABEL_158;
    }
    switch ( *(unsigned __int8 *)(v85 + 7) )
    {
      case 0xF6u:
        v95 = JsonImplementType<unsigned __int64>::GetUnchecked(v85);
        break;
      case 0xF7u:
        v95 = JsonImplementType<__int64>::GetUnchecked(v85);
        if ( v95 >= 0x8000000000000000uLL )
          goto LABEL_193;
        break;
      case 0xF8u:
        v104 = JsonImplementType<double>::GetUnchecked(v85);
        if ( v104 < *(double *)&`Microsoft::Diagnostics::FileWrapStream::SetSize'::`2'::zeroDisplacement.QuadPart
          || v104 >= 1.844674407370955e19 )
        {
          goto LABEL_193;
        }
        v105 = 0;
        if ( v104 >= 9.223372036854776e18 )
        {
          v104 = v104 - 9.223372036854776e18;
          if ( v104 < 9.223372036854776e18 )
            v105 = 0x8000000000000000uLL;
        }
        v95 = v105 + (unsigned int)(int)v104;
        break;
      default:
        goto LABEL_193;
    }
    if ( v95 < 0x10000 )
    {
      v96 = 0;
LABEL_153:
      if ( v96 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52502LL,
          (int)v124);
      v97 = Microsoft::Diagnostics::ScenarioDbObjectType::_from_value_loop(
              pExceptionObject,
              (unsigned __int16)v95,
              0,
              v92);
      if ( *(_BYTE *)v97 )
      {
        v98 = 1;
        v99 = word_180396C60[*(_QWORD *)(v97 + 8)];
      }
      else
      {
        v98 = 0;
        v99 = 0;
      }
      if ( !v98 )
      {
        *(_QWORD *)&pExceptionObject[0] = &std::exception::`vftable';
        *(_OWORD *)((char *)pExceptionObject + 8) = 0;
        v127 = (JsonBuilder *)"ScenarioDbObjectType::_from_integral: invalid argument";
        LOBYTE(v128[0]) = 1;
        *(unsigned int *)((char *)v128 + 1) = 0;
        *(_WORD *)((char *)&v128[1] + 1) = 0;
        HIBYTE(v128[1]) = 0;
        o___std_exception_copy_0(&v127, (char *)pExceptionObject + 8);
        *(_QWORD *)&pExceptionObject[0] = &std::logic_error::`vftable';
        throw (std::runtime_error *)pExceptionObject;
      }
      LOWORD(v127) = v99;
      goto LABEL_158;
    }
LABEL_193:
    LOWORD(v95) = 0;
    v96 = 1;
    goto LABEL_153;
  }
LABEL_37:
  if ( *v3 != a2 )
    __int2c();
  v28 = 0;
  if ( *((_DWORD *)a2 + 2) )
  {
    v29 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v6 + 7) >= 0xFEu )
    {
      v30 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v29 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
      if ( (_DWORD)v30 != *(_DWORD *)(v29 + 4 * v6 + 8) )
      {
        for ( kk = *(_DWORD *)(v29 + 4 * v30); ; kk = *(_DWORD *)(v29 + 4LL * kk) )
        {
          if ( *(_BYTE *)(v29 + 4LL * kk + 7) != 0xFD )
          {
            v32 = 2;
            if ( (*(_DWORD *)(v29 + 4LL * kk + 4) & 0xFFFFFF) == 2 )
              break;
          }
LABEL_49:
          if ( kk == *(_DWORD *)(v29 + 4 * v6 + 8) )
            goto LABEL_52;
        }
        v33 = L"te";
        v34 = (_WORD *)(v29 + 12 + 4LL * kk);
        while ( v32 )
        {
          if ( *v34 != *v33 )
            goto LABEL_49;
          --v32;
          ++v34;
          ++v33;
        }
        v28 = kk;
      }
    }
  }
LABEL_52:
  *((_QWORD *)&v130 + 1) = __PAIR64__(HIDWORD(pExceptionObject[0]), v28);
  if ( (_DWORD)v28 )
  {
    if ( *(_BYTE *)(*a2 + 4 * v28 + 7) != 0xFE )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C52502LL,
        (int)v124);
    JsonBuilder::cbegin(a2, &v132, &v130);
    v108 = v132;
    for ( mm = v133; ; v133 = mm )
    {
      JsonBuilder::cend(a2, &v137, &v130);
      if ( mm == DWORD2(v137) )
        break;
      if ( *(_BYTE *)(*(_QWORD *)v108 + 4LL * mm + 7) != 0xFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52502LL,
          (int)v124);
      LOWORD(v127) = 0;
      *(_QWORD *)v128 = 0;
      JsonBuilder::cbegin(v108, &v135, &v132);
      JsonBuilder::cend(v110, pExceptionObject, &v132);
      for ( nn = v136; nn != DWORD2(pExceptionObject[0]); v136 = nn )
      {
        v117 = *(_QWORD *)v135 + 4LL * nn;
        v118 = *(_DWORD *)(v117 + 4) & 0xFFFFFF;
        v143[0] = L"ty";
        v143[1] = 2;
        v144[0] = v117 + 12;
        v144[1] = v118;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v144, v143) )
        {
          *(_QWORD *)&v131 = L"h";
          *((_QWORD *)&v131 + 1) = 1;
          *(_QWORD *)&v134 = v117 + 12;
          *((_QWORD *)&v134 + 1) = v118;
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v134, &v131) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x189,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52500LL,
              (int)v124);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(v117, v128) )
            wil::details::in1diag3::Throw_Hr(
              v114,
              (void *)0x185,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52502LL,
              (int)v124);
        }
        else
        {
          v126 = 0;
          if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_short_(v117, &v126) )
            wil::details::in1diag3::Throw_Hr(
              v113,
              (void *)0x180,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52502LL,
              (int)v124);
          LOWORD(v127) = *(_WORD *)Microsoft::Diagnostics::ScenarioDbObjectType::_from_integral(v129, v126);
        }
        nn = JsonBuilder::NextIndex(v135, nn);
      }
      if ( !v111 || !*(_QWORD *)v128 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x18F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52500LL,
          (int)v124);
      v5 = v140;
      std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::emplace_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
        v140 + 96,
        &v127);
      mm = JsonBuilder::NextIndex(v108, mm);
    }
    v6 = v141;
    v27 = (__int64 *)v130;
    v3 = v142;
  }
  if ( *v3 != a2 )
    __int2c();
  if ( *((_DWORD *)a2 + 2) )
  {
    v35 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v6 + 7) >= 0xFEu )
    {
      v36 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v35 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
      if ( (_DWORD)v36 != *(_DWORD *)(v35 + 4 * v6 + 8) )
      {
        for ( i1 = *(_DWORD *)(v35 + 4 * v36); ; i1 = *v38 )
        {
          v38 = (int *)(v35 + 4LL * i1);
          if ( *((_BYTE *)v38 + 7) != 0xFD && (v38[1] & 0xFFFFFF) == 2 )
            break;
LABEL_65:
          if ( i1 == *(_DWORD *)(v35 + 4 * v6 + 8) )
            goto LABEL_69;
        }
        v39 = 2;
        v40 = L"ta";
        v41 = v38 + 3;
        while ( v39 )
        {
          if ( *v41 != *v40 )
            goto LABEL_65;
          --v39;
          ++v41;
          ++v40;
        }
        if ( i1 && !(unsigned __int8)ConvertToJsonUInt_unsigned_char_(v38, v5 + 120) )
          wil::details::in1diag3::Throw_Hr(
            v42,
            (void *)0x528,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\scenarios\\ScenarioObjectCache.h",
            (const char *)0x87C52502LL,
            (int)v124);
      }
    }
  }
LABEL_69:
  if ( *v3 != a2 )
    __int2c();
  v43 = 0;
  if ( *((_DWORD *)a2 + 2) )
  {
    v44 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v6 + 7) >= 0xFEu )
    {
      v45 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v44 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
      if ( (_DWORD)v45 != *(_DWORD *)(v44 + 4 * v6 + 8) )
      {
        for ( i2 = *(_DWORD *)(v44 + 4 * v45); ; i2 = *(_DWORD *)(v44 + 4LL * i2) )
        {
          if ( *(_BYTE *)(v44 + 4LL * i2 + 7) != 0xFD )
          {
            v47 = 2;
            if ( (*(_DWORD *)(v44 + 4LL * i2 + 4) & 0xFFFFFF) == 2 )
              break;
          }
LABEL_81:
          if ( i2 == *(_DWORD *)(v44 + 4 * v6 + 8) )
            goto LABEL_84;
        }
        v48 = L"tf";
        v49 = (_WORD *)(v44 + 12 + 4LL * i2);
        while ( v47 )
        {
          if ( *v49 != *v48 )
            goto LABEL_81;
          --v47;
          ++v49;
          ++v48;
        }
        v43 = i2;
      }
    }
  }
LABEL_84:
  *((_QWORD *)&v130 + 1) = __PAIR64__(HIDWORD(pExceptionObject[0]), v43);
  if ( (_DWORD)v43 )
  {
    if ( *(_BYTE *)(*a2 + 4 * v43 + 7) != 0xFE )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C52502LL,
        (int)v124);
    JsonBuilder::cbegin(a2, &v127, &v130);
    v115 = v127;
    Index = v128[0];
    while ( 1 )
    {
      JsonBuilder::cend(v27, pExceptionObject, &v130);
      if ( Index == DWORD2(pExceptionObject[0]) )
        break;
      if ( *(_BYTE *)(*(_QWORD *)v115 + 4LL * Index + 7) != 0xFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52502LL,
          (int)v124);
      Microsoft::Diagnostics::PropertySelector::PropertySelector((Microsoft::Diagnostics::PropertySelector *)v143);
      *(_QWORD *)&v134 = L"ps";
      *((_QWORD *)&v134 + 1) = 2;
      v130 = *(_OWORD *)JsonBuilder::find<>(a2, v144, &v127, &v134);
      v137 = v130;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializePropertySelector(a2, &v137, v143);
      v126 = 0;
      LOBYTE(v119) = 0;
      v137 = *(_OWORD *)&off_180386810;
      v131 = *(_OWORD *)v3;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeSimpleConvertTo<unsigned char>(a2, &v131, &v137, v119);
      v125[0] = 0;
      LOBYTE(v120) = 0;
      v137 = *(_OWORD *)&off_180386800;
      v131 = *(_OWORD *)v3;
      v124 = v125;
      if ( (unsigned __int8)Microsoft::Diagnostics::ScenarioObjectCache::DeserializeSimpleConvertTo<unsigned char>(
                              a2,
                              &v131,
                              &v137,
                              v120) )
      {
        LOBYTE(v121) = v125[0];
        Microsoft::Diagnostics::EnumDetails::MultiSelector::_from_integral(v129, v121);
      }
      std::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>(
        &v137,
        v143);
      v138 = v126;
      v139 = v122;
      std::vector<std::pair<Microsoft::Diagnostics::PropertySelector,Microsoft::Diagnostics::SelectFieldDirective>>::emplace_back<std::pair<Microsoft::Diagnostics::PropertySelector,Microsoft::Diagnostics::SelectFieldDirective>>(
        v5 + 128,
        &v137);
      std::vector<Microsoft::Diagnostics::PropertyKey>::_Tidy(&v137);
      std::vector<Microsoft::Diagnostics::PropertyKey>::_Tidy(v143);
      Index = JsonBuilder::NextIndex(v115, Index);
      v128[0] = Index;
      v27 = (__int64 *)v130;
    }
  }
  if ( *v3 != a2 )
    __int2c();
  if ( *((_DWORD *)a2 + 2) )
  {
    v50 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v6 + 7) >= 0xFEu )
    {
      v51 = (unsigned int)v6 + ((2 * (*(_DWORD *)(v50 + 4 * v6 + 4) & 0xFFFFFFu) + 15) >> 2);
      if ( (_DWORD)v51 != *(_DWORD *)(v50 + 4 * v6 + 8) )
      {
        for ( i3 = *(unsigned int *)(v50 + 4 * v51); ; i3 = *v53 )
        {
          v53 = (unsigned int *)(v50 + 4LL * (unsigned int)i3);
          if ( *((_BYTE *)v53 + 7) != 0xFD && (v53[1] & 0xFFFFFF) == 2 )
            break;
LABEL_97:
          if ( (_DWORD)i3 == *(_DWORD *)(v50 + 4 * v6 + 8) )
            goto LABEL_103;
        }
        v54 = 2;
        v55 = L"ut";
        v56 = v53 + 3;
        while ( v54 )
        {
          if ( *v56 != *v55 )
            goto LABEL_97;
          --v54;
          ++v56;
          ++v55;
        }
        if ( (_DWORD)i3 )
        {
          if ( *((_BYTE *)v53 + 7) == 0xF9 )
          {
            LOBYTE(v54) = 1;
            v57 = JsonImplementType<bool>::GetUnchecked(v50 + 4LL * (unsigned int)i3, v53, i3, v54);
          }
          else
          {
            v58 = 0;
            v57 = 0;
          }
          *(_BYTE *)(v5 + 152) = v57;
          if ( !v58 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x528,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\scenarios\\ScenarioObjectCache.h",
              (const char *)0x87C52502LL,
              (int)v124);
        }
      }
    }
  }
LABEL_103:
  v125[0] = 0;
  if ( *v3 != a2 )
    __int2c();
  if ( *((_DWORD *)a2 + 2) )
  {
    v59 = *((unsigned int *)v3 + 2);
    v60 = *a2;
    if ( *(_BYTE *)(*a2 + 4 * v59 + 7) >= 0xFEu )
    {
      v61 = (unsigned int)v59 + ((2 * (*(_DWORD *)(v60 + 4 * v59 + 4) & 0xFFFFFFu) + 15) >> 2);
      v62 = *(_DWORD *)(v60 + 4 * v59 + 8);
      if ( (_DWORD)v61 != v62 )
      {
        for ( i4 = *(_DWORD *)(v60 + 4 * v61); ; i4 = *v64 )
        {
          v64 = (int *)(v60 + 4LL * i4);
          if ( *((_BYTE *)v64 + 7) != 0xFD && (v64[1] & 0xFFFFFF) == 3 )
            break;
LABEL_115:
          if ( i4 == v62 )
            return std::wstring::_Tidy_deallocate(v146);
        }
        v65 = 3;
        v66 = L"src";
        v67 = v64 + 3;
        while ( v65 )
        {
          if ( *v67 != *v66 )
            goto LABEL_115;
          --v65;
          ++v67;
          ++v66;
        }
        if ( i4 )
        {
          if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_char_(v64, v125) )
            wil::details::in1diag3::Throw_Hr(
              v69,
              (void *)0x528,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\scenarios\\ScenarioObjectCache.h",
              (const char *)0x87C52502LL,
              (int)v124);
          LOBYTE(v68) = v125[0];
          *(_BYTE *)(v5 + 153) = *(_BYTE *)Microsoft::Diagnostics::TriggerSource::_from_integral(v129, v68);
        }
      }
    }
  }
  return std::wstring::_Tidy_deallocate(v146);
}

```

## disassembly

```asm
0x180075010  mov     rax, rsp
0x180075013  mov     [rax+20h], rbx
0x180075017  push    rbp
0x180075018  push    rsi
0x180075019  push    rdi
0x18007501a  push    r12
0x18007501c  push    r13
0x18007501e  push    r14
0x180075020  push    r15
0x180075022  lea     rbp, [rsp-80h]
0x180075027  sub     rsp, 180h
0x18007502e  movaps  xmmword ptr [rax-48h], xmm6
0x180075032  movaps  xmmword ptr [rax-58h], xmm7
0x180075036  mov     rax, cs:__security_cookie
0x18007503d  xor     rax, rsp
0x180075040  mov     [rbp+0B0h+var_60], rax
0x180075044  mov     r12, r8
0x180075047  mov     [rbp+0B0h+var_E0], r8
0x18007504b  mov     rdi, rdx
0x18007504e  mov     r13, rcx
0x180075051  mov     [rbp+0B0h+var_F0], rcx
0x180075055  lea     rcx, [rbp+0B0h+var_80]; void *
0x180075059  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007505e  nop
0x18007505f  cmp     [r12], rdi
0x180075063  jnz     loc_180075BF8
0x180075069  xor     r15d, r15d
0x18007506c  cmp     [rdi+8], r15d
0x180075070  jz      loc_18007569E
0x180075076  mov     r14d, [r12+8]
0x18007507b  mov     [rbp+0B0h+var_E8], r14
0x18007507f  mov     rcx, [rdi]
0x180075082  cmp     byte ptr [rcx+r14*4+7], 0FEh
0x180075088  jb      loc_18007569E
0x18007508e  mov     eax, [rcx+r14*4+4]
0x180075093  and     eax, 0FFFFFFh
0x180075098  lea     edx, ds:0Fh[rax*2]
0x18007509f  shr     edx, 2
0x1800750a2  add     edx, r14d
0x1800750a5  cmp     edx, [rcx+r14*4+8]
0x1800750aa  jz      loc_18007569E
0x1800750b0  mov     r8d, [rcx+rdx*4]
0x1800750b4  lea     esi, [r15+2]
0x1800750b8  mov     eax, r8d
0x1800750bb  lea     rdx, [rcx+rax*4]
0x1800750bf  cmp     byte ptr [rcx+rax*4+7], 0FDh
0x1800750c4  jz      short loc_1800750FD
0x1800750c6  mov     r9d, [rdx+4]
0x1800750ca  and     r9d, 0FFFFFFh
0x1800750d1  cmp     r9, rsi
0x1800750d4  jnz     short loc_1800750FD
0x1800750d6  mov     r10, rsi
0x1800750d9  mov     r11, cs:off_18036AEB8; "tn"
0x1800750e0  lea     rbx, [rdx+0Ch]
0x1800750e4  test    r10, r10
0x1800750e7  jz      short loc_18007510D
0x1800750e9  movzx   eax, word ptr [r11]
0x1800750ed  cmp     [rbx], ax
0x1800750f0  jnz     short loc_1800750FD
0x1800750f2  dec     r10
0x1800750f5  add     rbx, rsi
0x1800750f8  add     r11, rsi
0x1800750fb  jmp     short loc_1800750E4
0x1800750fd  cmp     r8d, [rcx+r14*4+8]
0x180075102  jz      loc_18007569E
0x180075108  mov     r8d, [rdx]
0x18007510b  jmp     short loc_1800750B8
0x18007510d  test    r8d, r8d
0x180075110  jz      loc_18007569E
0x180075116  cmp     byte ptr [rdx+7], 0F5h
0x18007511a  jnz     loc_180075A2A
0x180075120  lea     rax, ds:0Fh[r9*2]
0x180075128  shr     rax, 2
0x18007512c  lea     r9, [rdx+rax*4]
0x180075130  mov     r8d, [rdx+8]
0x180075134  shr     r8, 1
0x180075137  mov     al, r15b
0x18007513a  mov     rcx, [rbp+0B8h]; this
0x180075141  test    al, al
0x180075143  jnz     loc_180075A61
0x180075149  xorps   xmm0, xmm0
0x18007514c  movups  [rbp+0B0h+pExceptionObject], xmm0
0x180075150  xorps   xmm1, xmm1
0x180075153  movdqu  [rbp+0B0h+var_90], xmm1
0x180075158  mov     rdx, r9
0x18007515b  lea     rcx, [rbp+0B0h+pExceptionObject]
0x18007515f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180075164  lea     rcx, [rbp+0B0h+var_80]
0x180075168  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007516d  lea     rdx, [rbp+0B0h+pExceptionObject]
0x180075171  lea     rcx, [rbp+0B0h+var_80]
0x180075175  call    ?_Take_contents@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXAEAV12@@Z; std::wstring::_Take_contents(std::wstring &)
0x18007517a  lea     rcx, [rbp+0B0h+pExceptionObject]
0x18007517e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075183  lea     rdx, [rbp+0B0h+var_80]
0x180075187  cmp     [rbp+0B0h+var_68], 7
0x18007518c  cmova   rdx, [rbp+0B0h+var_80]
0x180075191  mov     r8, [rbp+0B0h+var_70]
0x180075195  lea     rcx, [r13+10h]
0x180075199  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18007519e  lea     rcx, [r13+10h]; unsigned __int8 *
0x1800751a2  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$00@std@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x1800751a7  mov     [r13+30h], rax
0x1800751ab  movups  xmm0, xmmword ptr cs:off_18036AE78; "e"
0x1800751b2  movdqu  [rbp+0B0h+var_130], xmm0
0x1800751b7  movups  xmm0, xmmword ptr [r12]
0x1800751bc  movdqu  [rsp+1B0h+var_150], xmm0
0x1800751c2  lea     r8, [r13+38h]
0x1800751c6  mov     byte ptr [rsp+1B0h+var_190], r15b; int
0x1800751cb  lea     r9, [rbp+0B0h+var_130]
0x1800751cf  lea     rdx, [rsp+1B0h+var_150]
0x1800751d4  mov     rcx, rdi
0x1800751d7  call    ?DeserializeDbKey@ScenarioObjectCache@Diagnostics@Microsoft@@SAXAEBVJsonBuilder@@VJsonConstIterator@@AEAUScenarioDbLookupPair@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@VDeserializeType@EnumDetails@23@@Z; Microsoft::Diagnostics::ScenarioObjectCache::DeserializeDbKey(JsonBuilder const &,JsonConstIterator,Microsoft::Diagnostics::ScenarioDbLookupPair &,std::wstring_view,Microsoft::Diagnostics::EnumDetails::DeserializeType)
0x1800751dc  cmp     [r12], rdi
0x1800751e0  jnz     loc_180075BFF
0x1800751e6  mov     r9d, r15d
0x1800751e9  mov     esi, [rdi+8]
0x1800751ec  test    esi, esi
0x1800751ee  jz      loc_18007527D
0x1800751f4  mov     rcx, [rdi]
0x1800751f7  cmp     byte ptr [rcx+r14*4+7], 0FEh
0x1800751fd  jb      short loc_18007527D
0x1800751ff  mov     eax, [rcx+r14*4+4]
0x180075204  and     eax, 0FFFFFFh
0x180075209  lea     edx, ds:0Fh[rax*2]
0x180075210  shr     edx, 2
0x180075213  add     edx, r14d
0x180075216  cmp     edx, [rcx+r14*4+8]
0x18007521b  jz      short loc_18007527D
0x18007521d  mov     edx, [rcx+rdx*4]
0x180075220  mov     r8d, edx
0x180075223  cmp     byte ptr [rcx+r8*4+7], 0FDh
0x180075229  jz      short loc_18007526D
0x18007522b  mov     eax, [rcx+r8*4+4]
0x180075230  and     eax, 0FFFFFFh
0x180075235  mov     r10d, 2
0x18007523b  cmp     eax, r10d
0x18007523e  jnz     short loc_18007526D
0x180075240  mov     r11, cs:off_18036AF08; "fs"
0x180075247  lea     rbx, [rcx+0Ch]
0x18007524b  lea     rbx, [rbx+r8*4]
0x18007524f  test    r10, r10
0x180075252  jz      short loc_18007527A
0x180075254  movzx   eax, word ptr [r11]
0x180075258  cmp     [rbx], ax
0x18007525b  jnz     short loc_18007526D
0x18007525d  dec     r10
0x180075260  mov     eax, 2
0x180075265  add     rbx, rax
0x180075268  add     r11, rax
0x18007526b  jmp     short loc_18007524F
0x18007526d  cmp     edx, [rcx+r14*4+8]
0x180075272  jz      short loc_18007527D
0x180075274  mov     edx, [rcx+r8*4]
0x180075278  jmp     short loc_180075220
0x18007527a  mov     r9d, edx
0x18007527d  mov     r15, rdi
0x180075280  mov     qword ptr [rsp+1B0h+var_160], rdi
0x180075285  mov     dword ptr [rsp+1B0h+var_160+8], r9d
0x18007528a  test    r9d, r9d
0x18007528d  jnz     loc_1800756BD
0x180075293  xor     esi, esi
0x180075295  cmp     [r12], rdi
0x180075299  jnz     loc_180075C06
0x18007529f  mov     edx, esi
0x1800752a1  cmp     [rdi+8], esi
0x1800752a4  jz      loc_18007533A
0x1800752aa  mov     rcx, [rdi]
0x1800752ad  cmp     byte ptr [rcx+r14*4+7], 0FEh
0x1800752b3  jb      loc_18007533A
0x1800752b9  mov     eax, [rcx+r14*4+4]
0x1800752be  and     eax, 0FFFFFFh
0x1800752c3  lea     r8d, ds:0Fh[rax*2]
0x1800752cb  shr     r8d, 2
0x1800752cf  add     r8d, r14d
0x1800752d2  cmp     r8d, [rcx+r14*4+8]
0x1800752d7  jz      short loc_18007533A
0x1800752d9  mov     r8d, [rcx+r8*4]
0x1800752dd  mov     r9d, r8d
0x1800752e0  cmp     byte ptr [rcx+r9*4+7], 0FDh
0x1800752e6  jz      short loc_18007532A
0x1800752e8  mov     eax, [rcx+r9*4+4]
0x1800752ed  and     eax, 0FFFFFFh
0x1800752f2  mov     r10d, 2
0x1800752f8  cmp     eax, r10d
0x1800752fb  jnz     short loc_18007532A
0x1800752fd  mov     r11, cs:off_18036AEA8; "te"
0x180075304  lea     rbx, [rcx+0Ch]
0x180075308  lea     rbx, [rbx+r9*4]
0x18007530c  test    r10, r10
0x18007530f  jz      short loc_180075337
0x180075311  movzx   eax, word ptr [r11]
0x180075315  cmp     [rbx], ax
0x180075318  jnz     short loc_18007532A
0x18007531a  dec     r10
0x18007531d  mov     eax, 2
0x180075322  add     rbx, rax
0x180075325  add     r11, rax
0x180075328  jmp     short loc_18007530C
0x18007532a  cmp     r8d, [rcx+r14*4+8]
0x18007532f  jz      short loc_18007533A
0x180075331  mov     r8d, [rcx+r9*4]
0x180075335  jmp     short loc_1800752DD
0x180075337  mov     edx, r8d
0x18007533a  mov     dword ptr [rsp+1B0h+var_160+8], edx
0x18007533e  mov     eax, dword ptr [rbp+0B0h+pExceptionObject+0Ch]
0x180075341  mov     dword ptr [rsp+1B0h+var_160+0Ch], eax
0x180075345  test    edx, edx
0x180075347  jnz     loc_180075CDD
0x18007534d  cmp     [r12], rdi
0x180075351  jnz     loc_180075C0D
0x180075357  cmp     [rdi+8], esi
0x18007535a  jz      loc_180075402
0x180075360  mov     rcx, [rdi]
0x180075363  cmp     byte ptr [rcx+r14*4+7], 0FEh
0x180075369  jb      loc_180075402
0x18007536f  mov     eax, [rcx+r14*4+4]
0x180075374  and     eax, 0FFFFFFh
0x180075379  lea     edx, ds:0Fh[rax*2]
0x180075380  shr     edx, 2
0x180075383  add     edx, r14d
0x180075386  cmp     edx, [rcx+r14*4+8]
0x18007538b  jz      short loc_180075402
0x18007538d  mov     edx, [rcx+rdx*4]
0x180075390  mov     eax, edx
0x180075392  lea     r8, [rcx+rax*4]
0x180075396  cmp     byte ptr [rcx+rax*4+7], 0FDh
0x18007539b  jz      short loc_1800753D7
0x18007539d  mov     eax, [r8+4]
0x1800753a1  and     eax, 0FFFFFFh
0x1800753a6  mov     ebx, 2
0x1800753ab  cmp     eax, ebx
0x1800753ad  jnz     short loc_1800753D7
0x1800753af  mov     r9d, ebx
0x1800753b2  mov     r10, cs:off_18036AEF8; "ta"
0x1800753b9  lea     r11, [r8+0Ch]
0x1800753bd  test    r9, r9
0x1800753c0  jz      short loc_1800753E3
0x1800753c2  movzx   eax, word ptr [r10]
0x1800753c6  cmp     [r11], ax
0x1800753ca  jnz     short loc_1800753D7
0x1800753cc  dec     r9
0x1800753cf  add     r11, rbx
0x1800753d2  add     r10, rbx
0x1800753d5  jmp     short loc_1800753BD
0x1800753d7  cmp     edx, [rcx+r14*4+8]
0x1800753dc  jz      short loc_180075402
0x1800753de  mov     edx, [r8]
0x1800753e1  jmp     short loc_180075390
0x1800753e3  test    edx, edx
0x1800753e5  jz      short loc_180075402
0x1800753e7  mov     r10, [rbp+0B8h]
0x1800753ee  lea     rdx, [r13+78h]
0x1800753f2  mov     rcx, r8
0x1800753f5  call    ConvertToJsonUInt_unsigned_char_
0x1800753fa  test    al, al
0x1800753fc  jz      loc_180075AC7
0x180075402  cmp     [r12], rdi
0x180075406  jnz     loc_180075C14
0x18007540c  mov     edx, esi
0x18007540e  cmp     [rdi+8], esi
0x180075411  jz      loc_1800754A7
0x180075417  mov     rcx, [rdi]
0x18007541a  cmp     byte ptr [rcx+r14*4+7], 0FEh
0x180075420  jb      loc_1800754A7
0x180075426  mov     eax, [rcx+r14*4+4]
0x18007542b  and     eax, 0FFFFFFh
0x180075430  lea     r8d, ds:0Fh[rax*2]
0x180075438  shr     r8d, 2
0x18007543c  add     r8d, r14d
0x18007543f  cmp     r8d, [rcx+r14*4+8]
0x180075444  jz      short loc_1800754A7
0x180075446  mov     r8d, [rcx+r8*4]
0x18007544a  mov     r9d, r8d
0x18007544d  cmp     byte ptr [rcx+r9*4+7], 0FDh
0x180075453  jz      short loc_180075497
0x180075455  mov     eax, [rcx+r9*4+4]
0x18007545a  and     eax, 0FFFFFFh
0x18007545f  mov     r10d, 2
0x180075465  cmp     eax, r10d
0x180075468  jnz     short loc_180075497
0x18007546a  mov     r11, cs:off_18036AEC8; "tf"
0x180075471  lea     rbx, [rcx+0Ch]
0x180075475  lea     rbx, [rbx+r9*4]
0x180075479  test    r10, r10
0x18007547c  jz      short loc_1800754A4
0x18007547e  movzx   eax, word ptr [r11]
0x180075482  cmp     [rbx], ax
0x180075485  jnz     short loc_180075497
0x180075487  dec     r10
0x18007548a  mov     eax, 2
0x18007548f  add     rbx, rax
0x180075492  add     r11, rax
0x180075495  jmp     short loc_180075479
0x180075497  cmp     r8d, [rcx+r14*4+8]
0x18007549c  jz      short loc_1800754A7
0x18007549e  mov     r8d, [rcx+r9*4]
0x1800754a2  jmp     short loc_18007544A
0x1800754a4  mov     edx, r8d
0x1800754a7  mov     dword ptr [rsp+1B0h+var_160+8], edx
  ... truncated ...
```
