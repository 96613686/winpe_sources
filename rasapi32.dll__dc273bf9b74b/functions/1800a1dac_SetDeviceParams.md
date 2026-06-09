# SetDeviceParams

- ea: `0x1800a1dac`
- end: `0x1800a3775`
- name: `SetDeviceParams`
- size: `6601`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036f2c`

## callees

- `0x180006afc`
- `0x18000b0f4`
- `0x180012570`
- `0x180012f7c`
- `0x180029390`
- `0x18004e580`
- `0x18004e5c0`
- `0x18004e984`
- `0x18007e3a8`
- `0x18007e5f0`
- `0x1800a1898`
- `0x1800a1aec`
- `0x1800a1dac`
- `0x1800a377c`
- `0x1800a7a30`
- `0x1800c5a2c`
- `0x1800c8dc8`
- `0x1800c8f6c`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a34d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a3516`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a3667`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a3516`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a3667`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a34be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a34be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a3428`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a3428`

## string_xrefs

- `0x1800a2a7f`: `Compression`
- `0x1800a29d7`: `Protocol`
- `0x1800a2fa7`: `EnableCompression`
- `0x1800a34b4`: `GetSessionCompartmentId`
- `0x1800a341c`: `iphlpapi.dll`

## pseudocode

```c
__int64 __fastcall SetDeviceParams(__int64 a1, wchar_t *a2, __int64 a3, wchar_t *a4, __int64 a5, _DWORD *a6)
{
  __int64 v9; // r12
  __int64 v10; // r15
  DWORD v11; // eax
  DWORD v12; // ebx
  _DWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  DWORD v17; // eax
  DWORD v18; // eax
  int v19; // edx
  int v20; // edx
  int v21; // edx
  DWORD v22; // eax
  DWORD v23; // eax
  _DWORD *v24; // rcx
  DWORD v25; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  _DWORD *v29; // rcx
  BOOL v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  _QWORD *v34; // r10
  const wchar_t *v35; // r12
  _QWORD *v36; // rcx
  const wchar_t *v37; // r8
  DWORD v38; // eax
  __int64 v39; // r9
  DWORD v40; // eax
  const wchar_t *v41; // r8
  const wchar_t *v42; // r8
  DWORD v43; // eax
  __int64 v44; // rdx
  DWORD RasUnimodemBlob; // eax
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r12
  bool v50; // zf
  __int64 v51; // r9
  HRESULT v52; // eax
  unsigned int v53; // ebx
  _DWORD *v54; // rcx
  __int64 v55; // rdx
  const wchar_t *v56; // r8
  DWORD v57; // eax
  HRESULT v58; // eax
  DWORD v59; // eax
  DWORD v60; // eax
  STRSAFE_LPWSTR v61; // r15
  DWORD v62; // eax
  DWORD v63; // eax
  HMODULE Library; // rax
  HMODULE v65; // r14
  DWORD LastError; // eax
  FARPROC ProcAddress; // r15
  DWORD v68; // eax
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rbx
  int v72; // eax
  int v73; // edx
  DWORD v74; // eax
  BOOL v75; // [rsp+30h] [rbp-79h] BYREF
  STRSAFE_LPWSTR v76; // [rsp+38h] [rbp-71h]
  __int64 v77; // [rsp+40h] [rbp-69h] BYREF
  BOOL v78; // [rsp+48h] [rbp-61h]
  _DWORD v79[6]; // [rsp+50h] [rbp-59h] BYREF
  int v80; // [rsp+68h] [rbp-41h]
  int v81; // [rsp+6Ch] [rbp-3Dh]
  __int64 v82; // [rsp+70h] [rbp-39h]
  __int128 v83; // [rsp+78h] [rbp-31h] BYREF
  wchar_t pszDest[8]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v85; // [rsp+98h] [rbp-11h]
  __int16 v86; // [rsp+A8h] [rbp-1h]

  v76 = a4;
  *(_QWORD *)&v83 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
  }
  v9 = *(_QWORD *)(a1 + 1584);
  v10 = *(_QWORD *)(a1 + 1592);
  *a6 = 0;
  v11 = StringCchCopyWrapW(a4);
  v12 = v11;
  if ( v11 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v12;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v11);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
      return v12;
    v14 = 235;
    goto LABEL_14;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      236,
      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
      *(unsigned int *)(v10 + 40));
    v16 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(v10 + 40) != 3 && *(_DWORD *)(v10 + 40) != 5 )
  {
    if ( *(_DWORD *)(v10 + 40) != 6 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
        WPP_SF_(v16[2], 258, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      v17 = StringCchCopyWrapW(a2);
      v12 = v17;
      if ( v17 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v12;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v17);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
          return v12;
        v14 = 260;
        goto LABEL_14;
      }
      goto LABEL_35;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
      WPP_SF_(v16[2], 255, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    v18 = StringCchCopyWrapW(a2);
    v12 = v18;
    if ( !v18 )
    {
LABEL_35:
      *(_DWORD *)(a1 + 380) = 1;
      goto LABEL_146;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v12;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v18);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
      return v12;
    v14 = 257;
LABEL_14:
    v15 = *((_QWORD *)v13 + 2);
LABEL_415:
    WPP_SF_d(v15, v14, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
    return v12;
  }
  if ( v16 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    {
      WPP_SF_(v16[2], 237, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    {
      WPP_SF_d(v16[2], 238, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, *(unsigned int *)(a1 + 380));
      v16 = WPP_GLOBAL_Control;
    }
  }
  v19 = *(_DWORD *)(a1 + 380);
  if ( !v19 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    {
      WPP_SF_(v16[2], 239, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(v10 + 92) || *(_DWORD *)(v10 + 88)) && *(_DWORD *)(v10 + 40) != 3 )
    {
      v22 = StringCchCopyWrapW(a2);
      v12 = v22;
      if ( v22 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v12;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v22);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
          return v12;
        v14 = 241;
      }
      else
      {
        if ( !*(_QWORD *)(v10 + 96) || (v23 = StringCchCopyWrapW(v76), (v12 = v23) == 0) )
        {
          v24 = (_DWORD *)v83;
          *(_DWORD *)(a1 + 380) = 1;
          *v24 = *(_DWORD *)(v10 + 88);
          goto LABEL_146;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v12;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v23);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
          return v12;
        v14 = 243;
      }
      goto LABEL_14;
    }
    goto LABEL_89;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_89:
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
      WPP_SF_(v16[2], 244, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    if ( CaseInsensitiveMatch((PCNZWCH)(a1 + 924), L"modem") )
    {
      v25 = StringCchCopyWrapW(a2);
      v12 = v25;
      if ( !v25 )
      {
        *(_DWORD *)(a1 + 380) = 2;
        goto LABEL_146;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v12;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v25);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
        return v12;
      v14 = 246;
      goto LABEL_14;
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_105;
  }
  v21 = v20 - 1;
  if ( v21 )
  {
    if ( v21 != 1 )
      goto LABEL_116;
    goto LABEL_109;
  }
LABEL_105:
  if ( v16 == &WPP_GLOBAL_Control )
    goto LABEL_113;
  if ( (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
  {
    WPP_SF_(v16[2], 247, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    v16 = WPP_GLOBAL_Control;
  }
LABEL_109:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
  {
    WPP_SF_(v16[2], 248, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    v16 = WPP_GLOBAL_Control;
  }
LABEL_113:
  if ( *(_DWORD *)(v9 + 216) || *(_DWORD *)(v9 + 212) || *(_DWORD *)(v9 + 232) )
  {
    v27 = StringCchCopyWrapW(a2);
    v12 = v27;
    if ( v27 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v12;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v27);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
        return v12;
      v14 = 250;
    }
    else
    {
      if ( !*(_QWORD *)(v9 + 224) || (v28 = StringCchCopyWrapW(v76), (v12 = v28) == 0) )
      {
        v29 = (_DWORD *)v83;
        *(_DWORD *)(a1 + 380) = 4;
        *v29 = *(_DWORD *)(v9 + 212);
        if ( *(_DWORD *)(v9 + 232) == 1 )
          *v29 = 1;
LABEL_146:
        v75 = CaseInsensitiveMatch(a2, L"modem");
        v78 = CaseInsensitiveMatch(a2, L"isdn");
        v30 = CaseInsensitiveMatch(a2, L"switch");
        LODWORD(v77) = v30;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          LOBYTE(v33) = v75;
          WPP_SF_ccc(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, v33, v78, v30);
          v34 = WPP_GLOBAL_Control;
        }
        v35 = L"1";
        if ( v75 )
        {
          if ( (unsigned int)CompareStringWrapW((PCNZWCH)(a1 + 924), a2) )
          {
            v36 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 636);
                v36 = WPP_GLOBAL_Control;
              }
              if ( v36 != &WPP_GLOBAL_Control && (*((_DWORD *)v36 + 7) & 0x800) != 0 && *((_BYTE *)v36 + 25) >= 6u )
                WPP_SF_d(v36[2], 263, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 636);
            }
            return 636;
          }
          v37 = L"0";
          if ( !*(_DWORD *)(a1 + 3732) )
            v37 = L"1";
          v38 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"Speaker", v37, a2, v76);
          v12 = v38;
          if ( v38 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v38);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 265;
            goto LABEL_14;
          }
          v34 = WPP_GLOBAL_Control;
        }
        if ( !*(_DWORD *)(a1 + 368) )
        {
          v39 = *(unsigned int *)(*(_QWORD *)(v10 + 168) + 16LL);
          *(_DWORD *)(a1 + 368) = v39;
          if ( (unsigned int)v39 > 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v39);
            }
            *(_DWORD *)(a1 + 352) = 1;
          }
          v34 = WPP_GLOBAL_Control;
        }
        if ( v75 )
        {
          if ( *(_DWORD *)(a1 + 5444) )
          {
            *(_WORD *)(a1 + 2118) = 0;
            v40 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"AutoDial", L"0", a2, v76);
            v12 = v40;
            if ( v40 )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v12;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v40);
                v13 = WPP_GLOBAL_Control;
              }
              if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
                return v12;
              v14 = 268;
              goto LABEL_14;
            }
          }
          v12 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"PhoneNumber", a1 + 4030, a2, v76);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 270;
            goto LABEL_14;
          }
          v41 = L"1";
          if ( !*(_DWORD *)(v10 + 108) )
            v41 = L"0";
          v12 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"HwFlowControl", v41, a2, v76);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 272;
            goto LABEL_14;
          }
          v42 = L"1";
          if ( !*(_DWORD *)(v10 + 112) )
            v42 = L"0";
          v12 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"Protocol", v42, a2, v76);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 274;
            goto LABEL_14;
          }
          if ( !*(_DWORD *)(v10 + 116) )
            v35 = L"0";
          v43 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"Compression", v35, a2, v76);
          v12 = v43;
          if ( v43 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v43);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 276;
            goto LABEL_14;
          }
          v77 = 0;
          LOBYTE(v85) = 0;
          v75 = 0;
          *(_OWORD *)pszDest = 0;
          StrncpyWtoA(pszDest, a2, 17, 65001);
          v44 = *(_QWORD *)(a1 + 624);
          if ( *(_DWORD *)(*(_QWORD *)(a1 + 1584) + 44LL) )
          {
            RasUnimodemBlob = GetRasUnimodemBlobEx(0, v44, (unsigned int)pszDest, 1, (__int64)&v77, (__int64)&v75);
            v12 = RasUnimodemBlob;
            if ( RasUnimodemBlob )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_246;
                v47 = 277;
LABEL_245:
                WPP_SF_d(*((_QWORD *)v13 + 2), v47, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, RasUnimodemBlob);
                v13 = WPP_GLOBAL_Control;
LABEL_246:
                if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
                  return v12;
                v14 = 279;
                goto LABEL_14;
              }
              return v12;
            }
          }
          else
          {
            RasUnimodemBlob = GetRasUnimodemBlobEx(0, v44, (unsigned int)pszDest, 0, (__int64)&v77, (__int64)&v75);
            v12 = RasUnimodemBlob;
            if ( RasUnimodemBlob )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  goto LABEL_246;
                v47 = 278;
                goto LABEL_245;
              }
              return v12;
            }
          }
          if ( v75 )
          {
            v48 = *(_QWORD *)(a1 + 1584);
            v82 = 0;
            v49 = v77;
            if ( !*(_DWORD *)(v48 + 44) )
            {
              if ( !(unsigned int)ValidateModemSettings(v77, v75, v46, 0) )
              {
                Free0(v49);
                v13 = WPP_GLOBAL_Control;
                v12 = 87;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
                {
                  return v12;
                }
                v14 = 280;
                goto LABEL_14;
              }
              v50 = *(_DWORD *)(a1 + 3732) == 0;
              v79[0] = *(_DWORD *)(v10 + 108);
              v79[1] = *(_DWORD *)(v10 + 112);
              v79[2] = *(_DWORD *)(v10 + 116);
              v79[3] = *(_DWORD *)(v10 + 104);
              v79[4] = v50;
              v79[5] = *(_DWORD *)(a1 + 5444);
              v81 = *(_DWORD *)(v10 + 124);
              if ( !*(_DWORD *)(v10 + 88) || (v50 = *(_DWORD *)(v10 + 40) == 3, v80 = 1, !v50) )
                v80 = 0;
              UnimodemInfoToBlob(v79, v49);
            }
            v83 = 0;
            StrncpyWtoA(&v83, a2, 16, 65001);
            v12 = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int64, BOOL))g_pRasSetDevConfig)(
                    *(_QWORD *)(a1 + 624),
                    &v83,
                    v49,
                    v75);
            if ( v12
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
            }
            Free0(v49);
            v34 = WPP_GLOBAL_Control;
          }
          else
          {
            v34 = WPP_GLOBAL_Control;
          }
LABEL_346:
          if ( !*(_WORD *)(a1 + 2634) && !*(_WORD *)(a1 + 3148) )
            goto LABEL_411;
          if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x800) != 0 && *((_BYTE *)v34 + 25) >= 5u )
            WPP_SF_S(v34[2], 306, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, a1 + 2634);
          v61 = v76;
          v62 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"UserName", a1 + 2634, a2, v76);
          v12 = v62;
          if ( v62 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 307, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v62);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 308;
            goto LABEL_14;
          }
          EncodePasswordW(a1 + 3148);
          v63 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"Password", a1 + 3148, a2, v61);
          v12 = v63;
          if ( v63
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v63);
          }
          EncodePasswordW(a1 + 3148);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
            {
              return v12;
            }
            v14 = 310;
            goto LABEL_14;
          }
          goto LABEL_410;
        }
        if ( v78 )
        {
          v51 = *(unsigned int *)(v10 + 132);
          v86 = 0;
          *(_OWORD *)pszDest = 0;
          v85 = 0;
          v52 = StringCchPrintfW(pszDest, 0x11u, L"%d", v51);
          v53 = v52;
          if ( v52 < 0 )
          {
            v54 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return (unsigned __int16)v53;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                282,
                WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                (unsigned int)v52);
              v54 = WPP_GLOBAL_Control;
            }
            if ( v54 == (_DWORD *)&WPP_GLOBAL_Control || (v54[7] & 0x800) == 0 || *((_BYTE *)v54 + 25) < 6u )
              return (unsigned __int16)v53;
            v55 = 283;
LABEL_278:
            WPP_SF_d(*((_QWORD *)v54 + 2), v55, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v53);
            return (unsigned __int16)v53;
          }
          v12 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"LineType", pszDest, a2, v76);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 285;
            goto LABEL_14;
          }
          v56 = L"1";
          if ( !*(_DWORD *)(v10 + 136) )
            v56 = L"0";
          v12 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"Fallback", v56, a2, v76);
          if ( v12 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 287;
            goto LABEL_14;
          }
          if ( !*(_DWORD *)(v10 + 140) )
            v35 = L"0";
          v57 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"EnableCompression", v35, a2, v76);
          v12 = v57;
          if ( v57 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v57);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 289;
            goto LABEL_14;
          }
          v58 = StringCchPrintfW(pszDest, 0x11u, L"%d", *(unsigned int *)(v10 + 144));
          v53 = v58;
          if ( v58 < 0 )
          {
            v54 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return (unsigned __int16)v53;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                290,
                WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                (unsigned int)v58);
              v54 = WPP_GLOBAL_Control;
            }
            if ( v54 == (_DWORD *)&WPP_GLOBAL_Control || (v54[7] & 0x800) == 0 || *((_BYTE *)v54 + 25) < 6u )
              return (unsigned __int16)v53;
            v55 = 291;
            goto LABEL_278;
          }
          v59 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"ChannelAggregation", pszDest, a2, v76);
          v12 = v59;
          if ( v59 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v59);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 293;
            goto LABEL_14;
          }
          v60 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"PhoneNumber", a1 + 4030, a2, v76);
          v12 = v60;
          if ( v60 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v60);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 295;
            goto LABEL_14;
          }
          if ( (_DWORD)v77 == 1 )
          {
            v34 = WPP_GLOBAL_Control;
            goto LABEL_345;
          }
LABEL_410:
          v34 = WPP_GLOBAL_Control;
LABEL_411:
          if ( v34 == &WPP_GLOBAL_Control || (*((_DWORD *)v34 + 7) & 0x800) == 0 || *((_BYTE *)v34 + 25) < 6u )
            return v12;
          v15 = v34[2];
          v14 = 311;
          goto LABEL_415;
        }
        if ( (_DWORD)v77 == 1 )
        {
          if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x800) != 0 && *((_BYTE *)v34 + 25) >= 5u )
          {
            WPP_SF_(v34[2], 296, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
            v34 = WPP_GLOBAL_Control;
          }
LABEL_345:
          if ( *(_DWORD *)v83 )
            goto LABEL_411;
          goto LABEL_346;
        }
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 1584) + 24LL) != 2 )
        {
          v74 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"PhoneNumber", a1 + 4030, a2, v76);
          v12 = v74;
          if ( !v74 )
            goto LABEL_410;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v12;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_423:
            if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
              return v12;
            v14 = 305;
            goto LABEL_14;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v74);
LABEL_422:
          v13 = WPP_GLOBAL_Control;
          goto LABEL_423;
        }
        Library = LoadLibraryExW(L"iphlpapi.dll", 0, 0x800u);
        v65 = Library;
        if ( !Library )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v12;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_379:
              if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
                return v12;
              v14 = 298;
              goto LABEL_14;
            }
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              297,
              WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
              LastError);
          }
          v13 = WPP_GLOBAL_Control;
          goto LABEL_379;
        }
        ProcAddress = GetProcAddress(Library, "GetSessionCompartmentId");
        if ( !ProcAddress )
        {
          v12 = GetLastError();
          if ( v12
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 299, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
          }
          FreeLibrary(v65);
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
          {
            return v12;
          }
          v14 = 300;
          goto LABEL_14;
        }
        v68 = SetDeviceParamString(*(_QWORD *)(a1 + 624), L"PhoneNumber", a1 + 4030, a2, v76);
        v12 = v68;
        if ( v68 )
        {
          v69 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v70 = 301;
LABEL_403:
            WPP_SF_d(v69[2], v70, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v68);
          }
        }
        else
        {
          v68 = SetDeviceSpecificInfo(a1, a2, v76);
          v12 = v68;
          if ( v68 )
          {
            v69 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v70 = 302;
              goto LABEL_403;
            }
          }
          else
          {
            v71 = *(_QWORD *)(a1 + 624);
            v72 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(*(unsigned int *)(a1 + 5536));
            v68 = SetDeviceParamNumber(v71, v73, v72, (_DWORD)a2, (__int64)v76);
            v12 = v68;
            if ( v68 )
            {
              v69 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v70 = 303;
                goto LABEL_403;
              }
            }
          }
        }
        FreeLibrary(v65);
        if ( !v12 )
          goto LABEL_410;
        goto LABEL_422;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v12;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v28);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 == (_DWORD *)&WPP_GLOBAL_Control || (v13[7] & 0x800) == 0 || *((_BYTE *)v13 + 25) < 6u )
        return v12;
      v14 = 252;
    }
    goto LABEL_14;
  }
LABEL_116:
  if ( v16 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    {
      WPP_SF_(v16[2], 253, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 6u )
      WPP_SF_d(v16[2], 254, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a1dac  mov     [rsp-8+arg_10], rbx
0x1800a1db1  push    rbp
0x1800a1db2  push    rsi
0x1800a1db3  push    rdi
0x1800a1db4  push    r12
0x1800a1db6  push    r13
0x1800a1db8  push    r14
0x1800a1dba  push    r15
0x1800a1dbc  lea     rbp, [rsp-17h]
0x1800a1dc1  sub     rsp, 0C0h
0x1800a1dc8  mov     rax, cs:__security_cookie
0x1800a1dcf  xor     rax, rsp
0x1800a1dd2  mov     [rbp+47h+var_40], rax
0x1800a1dd6  mov     rdi, [rbp+47h+arg_28]
0x1800a1dda  mov     rbx, r9
0x1800a1ddd  mov     [rbp+47h+var_B8], rbx
0x1800a1de1  mov     r13, rdx
0x1800a1de4  mov     qword ptr [rbp+47h+var_78], rdi
0x1800a1de8  mov     rsi, rcx
0x1800a1deb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1df2  lea     rax, WPP_GLOBAL_Control
0x1800a1df9  mov     r14d, 800h
0x1800a1dff  cmp     rcx, rax
0x1800a1e02  jz      short loc_1800A1E25
0x1800a1e04  test    [rcx+1Ch], r14d
0x1800a1e08  jz      short loc_1800A1E25
0x1800a1e0a  cmp     byte ptr [rcx+19h], 6
0x1800a1e0e  jb      short loc_1800A1E25
0x1800a1e10  mov     rcx, [rcx+10h]
0x1800a1e14  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1e1b  mov     edx, 0E9h
0x1800a1e20  call    WPP_SF_
0x1800a1e25  mov     r12, [rsi+630h]
0x1800a1e2c  lea     r8, [rsi+29Ah]
0x1800a1e33  mov     r15, [rsi+638h]
0x1800a1e3a  mov     edx, 602h
0x1800a1e3f  mov     rcx, rbx; pszDest
0x1800a1e42  mov     dword ptr [rdi], 0
0x1800a1e48  call    StringCchCopyWrapW
0x1800a1e4d  mov     ebx, eax
0x1800a1e4f  test    eax, eax
0x1800a1e51  jz      short loc_1800A1EC5
0x1800a1e53  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1e5a  lea     rsi, WPP_GLOBAL_Control
0x1800a1e61  cmp     rcx, rsi
0x1800a1e64  jz      loc_1800A36B1
0x1800a1e6a  test    [rcx+1Ch], r14d
0x1800a1e6e  jz      short loc_1800A1E9A
0x1800a1e70  mov     edi, 2
0x1800a1e75  cmp     [rcx+19h], dil
0x1800a1e79  jb      short loc_1800A1E9A
0x1800a1e7b  mov     rcx, [rcx+10h]
0x1800a1e7f  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1e86  mov     edx, 0EAh
0x1800a1e8b  mov     r9d, eax
0x1800a1e8e  call    WPP_SF_d
0x1800a1e93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1e9a  cmp     rcx, rsi
0x1800a1e9d  jz      loc_1800A36B1
0x1800a1ea3  test    [rcx+1Ch], r14d
0x1800a1ea7  jz      loc_1800A36B1
0x1800a1ead  cmp     byte ptr [rcx+19h], 6
0x1800a1eb1  jb      loc_1800A36B1
0x1800a1eb7  mov     edx, 0EBh
0x1800a1ebc  mov     rcx, [rcx+10h]
0x1800a1ec0  jmp     loc_1800A36A2
0x1800a1ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1ecc  lea     rbx, WPP_GLOBAL_Control
0x1800a1ed3  cmp     rcx, rbx
0x1800a1ed6  jz      short loc_1800A1F04
0x1800a1ed8  test    [rcx+1Ch], r14d
0x1800a1edc  jz      short loc_1800A1F04
0x1800a1ede  cmp     byte ptr [rcx+19h], 5
0x1800a1ee2  jb      short loc_1800A1F04
0x1800a1ee4  mov     r9d, [r15+28h]
0x1800a1ee8  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1eef  mov     rcx, [rcx+10h]
0x1800a1ef3  mov     edx, 0ECh
0x1800a1ef8  call    WPP_SF_d
0x1800a1efd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1f04  mov     edx, [r15+28h]
0x1800a1f08  mov     edi, 2
0x1800a1f0d  sub     edx, 3
0x1800a1f10  jz      loc_1800A2088
0x1800a1f16  sub     edx, edi
0x1800a1f18  jz      loc_1800A2088
0x1800a1f1e  cmp     edx, 1
0x1800a1f21  jz      loc_1800A1FDF
0x1800a1f27  cmp     rcx, rbx
0x1800a1f2a  jz      short loc_1800A1F4D
0x1800a1f2c  test    [rcx+1Ch], r14d
0x1800a1f30  jz      short loc_1800A1F4D
0x1800a1f32  cmp     byte ptr [rcx+19h], 5
0x1800a1f36  jb      short loc_1800A1F4D
0x1800a1f38  mov     rcx, [rcx+10h]
0x1800a1f3c  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1f43  mov     edx, 102h
0x1800a1f48  call    WPP_SF_
0x1800a1f4d  mov     r8, [r15+18h]
0x1800a1f51  mov     edx, 602h
0x1800a1f56  mov     rcx, r13; pszDest
0x1800a1f59  call    StringCchCopyWrapW
0x1800a1f5e  mov     ebx, eax
0x1800a1f60  test    eax, eax
0x1800a1f62  jz      short loc_1800A1FCD
0x1800a1f64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1f6b  lea     rsi, WPP_GLOBAL_Control
0x1800a1f72  cmp     rcx, rsi
0x1800a1f75  jz      loc_1800A36B1
0x1800a1f7b  test    [rcx+1Ch], r14d
0x1800a1f7f  jz      short loc_1800A1FA6
0x1800a1f81  cmp     [rcx+19h], dil
0x1800a1f85  jb      short loc_1800A1FA6
0x1800a1f87  mov     rcx, [rcx+10h]
0x1800a1f8b  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1f92  mov     edx, 103h
0x1800a1f97  mov     r9d, eax
0x1800a1f9a  call    WPP_SF_d
0x1800a1f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1fa6  cmp     rcx, rsi
0x1800a1fa9  jz      loc_1800A36B1
0x1800a1faf  test    [rcx+1Ch], r14d
0x1800a1fb3  jz      loc_1800A36B1
0x1800a1fb9  cmp     byte ptr [rcx+19h], 6
0x1800a1fbd  jb      loc_1800A36B1
0x1800a1fc3  mov     edx, 104h
0x1800a1fc8  jmp     loc_1800A1EBC
0x1800a1fcd  mov     r14d, 1
0x1800a1fd3  mov     [rsi+17Ch], r14d
0x1800a1fda  jmp     loc_1800A259A
0x1800a1fdf  cmp     rcx, rbx
0x1800a1fe2  jz      short loc_1800A2005
0x1800a1fe4  test    [rcx+1Ch], r14d
0x1800a1fe8  jz      short loc_1800A2005
0x1800a1fea  cmp     byte ptr [rcx+19h], 5
0x1800a1fee  jb      short loc_1800A2005
0x1800a1ff0  mov     rcx, [rcx+10h]
0x1800a1ff4  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a1ffb  mov     edx, 0FFh
0x1800a2000  call    WPP_SF_
0x1800a2005  lea     r8, aIsdn; "isdn"
0x1800a200c  mov     edx, 602h
0x1800a2011  mov     rcx, r13; pszDest
0x1800a2014  call    StringCchCopyWrapW
0x1800a2019  mov     ebx, eax
0x1800a201b  test    eax, eax
0x1800a201d  jz      short loc_1800A1FCD
0x1800a201f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2026  lea     rsi, WPP_GLOBAL_Control
0x1800a202d  cmp     rcx, rsi
0x1800a2030  jz      loc_1800A36B1
0x1800a2036  test    [rcx+1Ch], r14d
0x1800a203a  jz      short loc_1800A2061
0x1800a203c  cmp     [rcx+19h], dil
0x1800a2040  jb      short loc_1800A2061
0x1800a2042  mov     rcx, [rcx+10h]
0x1800a2046  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a204d  mov     edx, 100h
0x1800a2052  mov     r9d, eax
0x1800a2055  call    WPP_SF_d
0x1800a205a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2061  cmp     rcx, rsi
0x1800a2064  jz      loc_1800A36B1
0x1800a206a  test    [rcx+1Ch], r14d
0x1800a206e  jz      loc_1800A36B1
0x1800a2074  cmp     byte ptr [rcx+19h], 6
0x1800a2078  jb      loc_1800A36B1
0x1800a207e  mov     edx, 101h
0x1800a2083  jmp     loc_1800A1EBC
0x1800a2088  cmp     rcx, rbx
0x1800a208b  jz      short loc_1800A20E9
0x1800a208d  test    [rcx+1Ch], r14d
0x1800a2091  jz      short loc_1800A20B5
0x1800a2093  cmp     byte ptr [rcx+19h], 5
0x1800a2097  jb      short loc_1800A20B5
0x1800a2099  mov     rcx, [rcx+10h]
0x1800a209d  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a20a4  mov     edx, 0EDh
0x1800a20a9  call    WPP_SF_
0x1800a20ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a20b5  cmp     rcx, rbx
0x1800a20b8  jz      short loc_1800A20E9
0x1800a20ba  test    [rcx+1Ch], r14d
0x1800a20be  jz      short loc_1800A20E9
0x1800a20c0  cmp     byte ptr [rcx+19h], 5
0x1800a20c4  jb      short loc_1800A20E9
0x1800a20c6  mov     r9d, [rsi+17Ch]
0x1800a20cd  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a20d4  mov     rcx, [rcx+10h]
0x1800a20d8  mov     edx, 0EEh
0x1800a20dd  call    WPP_SF_d
0x1800a20e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a20e9  mov     edx, [rsi+17Ch]
0x1800a20ef  xor     eax, eax
0x1800a20f1  lea     r14d, [rax+1]
0x1800a20f5  test    edx, edx
0x1800a20f7  jz      short loc_1800A2119
0x1800a20f9  sub     edx, r14d
0x1800a20fc  jz      loc_1800A2295
0x1800a2102  sub     edx, r14d
0x1800a2105  jz      loc_1800A2375
0x1800a210b  cmp     edx, r14d
0x1800a210e  jz      loc_1800A23A5
0x1800a2114  jmp     loc_1800A23F5
0x1800a2119  cmp     rcx, rbx
0x1800a211c  jz      short loc_1800A214B
0x1800a211e  test    dword ptr [rcx+1Ch], 800h
0x1800a2125  jz      short loc_1800A214B
0x1800a2127  cmp     byte ptr [rcx+19h], 5
0x1800a212b  jb      short loc_1800A214B
0x1800a212d  mov     rcx, [rcx+10h]
0x1800a2131  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a2138  mov     edx, 0EFh
0x1800a213d  call    WPP_SF_
0x1800a2142  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2149  xor     eax, eax
0x1800a214b  cmp     [r15+5Ch], eax
0x1800a214f  jnz     short loc_1800A215B
0x1800a2151  cmp     [r15+58h], eax
0x1800a2155  jz      loc_1800A2295
0x1800a215b  cmp     dword ptr [r15+28h], 3
0x1800a2160  jz      loc_1800A2295
0x1800a2166  lea     r8, aSwitch_0; "switch"
0x1800a216d  mov     edx, 602h
0x1800a2172  mov     rcx, r13; pszDest
0x1800a2175  call    StringCchCopyWrapW
0x1800a217a  mov     ebx, eax
0x1800a217c  test    eax, eax
0x1800a217e  jz      short loc_1800A21EF
0x1800a2180  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2187  lea     rsi, WPP_GLOBAL_Control
0x1800a218e  cmp     rcx, rsi
0x1800a2191  jz      loc_1800A36B1
0x1800a2197  test    dword ptr [rcx+1Ch], 800h
0x1800a219e  jz      short loc_1800A21C5
0x1800a21a0  cmp     [rcx+19h], dil
0x1800a21a4  jb      short loc_1800A21C5
0x1800a21a6  mov     rcx, [rcx+10h]
0x1800a21aa  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a21b1  mov     edx, 0F0h
0x1800a21b6  mov     r9d, eax
0x1800a21b9  call    WPP_SF_d
0x1800a21be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a21c5  cmp     rcx, rsi
0x1800a21c8  jz      loc_1800A36B1
0x1800a21ce  test    dword ptr [rcx+1Ch], 800h
0x1800a21d5  jz      loc_1800A36B1
0x1800a21db  cmp     byte ptr [rcx+19h], 6
0x1800a21df  jb      loc_1800A36B1
0x1800a21e5  mov     edx, 0F1h
0x1800a21ea  jmp     loc_1800A1EBC
0x1800a21ef  mov     r8, [r15+60h]
0x1800a21f3  test    r8, r8
0x1800a21f6  jz      loc_1800A227F
0x1800a21fc  mov     rcx, [rbp+47h+var_B8]; pszDest
0x1800a2200  mov     edx, 602h
0x1800a2205  call    StringCchCopyWrapW
0x1800a220a  mov     ebx, eax
0x1800a220c  test    eax, eax
0x1800a220e  jz      short loc_1800A227F
0x1800a2210  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2217  lea     rsi, WPP_GLOBAL_Control
0x1800a221e  cmp     rcx, rsi
0x1800a2221  jz      loc_1800A36B1
0x1800a2227  test    dword ptr [rcx+1Ch], 800h
0x1800a222e  jz      short loc_1800A2255
0x1800a2230  cmp     [rcx+19h], dil
0x1800a2234  jb      short loc_1800A2255
0x1800a2236  mov     rcx, [rcx+10h]
0x1800a223a  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a2241  mov     edx, 0F2h
0x1800a2246  mov     r9d, eax
0x1800a2249  call    WPP_SF_d
0x1800a224e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2255  cmp     rcx, rsi
0x1800a2258  jz      loc_1800A36B1
0x1800a225e  test    dword ptr [rcx+1Ch], 800h
0x1800a2265  jz      loc_1800A36B1
0x1800a226b  cmp     byte ptr [rcx+19h], 6
0x1800a226f  jb      loc_1800A36B1
0x1800a2275  mov     edx, 0F3h
0x1800a227a  jmp     loc_1800A1EBC
0x1800a227f  mov     rcx, qword ptr [rbp+47h+var_78]
0x1800a2283  mov     [rsi+17Ch], r14d
0x1800a228a  mov     eax, [r15+58h]
0x1800a228e  mov     [rcx], eax
0x1800a2290  jmp     loc_1800A259A
0x1800a2295  cmp     rcx, rbx
0x1800a2298  jz      short loc_1800A22BE
0x1800a229a  test    dword ptr [rcx+1Ch], 800h
0x1800a22a1  jz      short loc_1800A22BE
0x1800a22a3  cmp     byte ptr [rcx+19h], 5
0x1800a22a7  jb      short loc_1800A22BE
0x1800a22a9  mov     rcx, [rcx+10h]
0x1800a22ad  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a22b4  mov     edx, 0F4h
0x1800a22b9  call    WPP_SF_
0x1800a22be  lea     rcx, [rsi+39Ch]; lpString1
0x1800a22c5  lea     rdx, aModem_0; "modem"
0x1800a22cc  call    CaseInsensitiveMatch
  ... truncated ...
```
