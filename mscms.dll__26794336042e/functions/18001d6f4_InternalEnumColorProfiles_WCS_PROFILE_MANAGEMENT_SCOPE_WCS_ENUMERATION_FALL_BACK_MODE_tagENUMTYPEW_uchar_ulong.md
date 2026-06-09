# InternalEnumColorProfiles(WCS_PROFILE_MANAGEMENT_SCOPE,WCS_ENUMERATION_FALL_BACK_MODE,tagENUMTYPEW *,uchar *,ulong *,ulong *)

- ea: `0x18001d6f4`
- end: `0x18001e26b`
- name: `?InternalEnumColorProfiles@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4WCS_ENUMERATION_FALL_BACK_MODE@@PEAUtagENUMTYPEW@@PEAEPEAK4@Z`
- size: `2935`
- prototype: `int __high(enum WCS_PROFILE_MANAGEMENT_SCOPE, enum WCS_ENUMERATION_FALL_BACK_MODE, struct tagENUMTYPEW *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18001d650`
- `0x18001d6b0`
- `0x1800444e0`
- `0x180045550`
- `0x18004d390`

## callees

- `0x180001298`
- `0x18000271c`
- `0x180008bf0`
- `0x180008cc0`
- `0x1800098b0`
- `0x180009974`
- `0x18000b828`
- `0x18000be44`
- `0x18001b3a8`
- `0x18001d6f4`
- `0x18001fdc8`
- `0x1800212e0`
- `0x180023428`
- `0x180023a4c`
- `0x18002a8a8`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x1800417d4`
- `0x180043a88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d920`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dbff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001de5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e208`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d920`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dbff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001de5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1fa`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001dc83`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001dc83`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001dd7e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001dd7e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001e21b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001e21b`

## string_xrefs

- `0x18001d8ac`: `Error getting color directory\n`
- `0x18001dbe9`: `StringCchCopy failed: 0x%x\n`
- `0x18001db9a`: `StringCbCopy failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall InternalEnumColorProfiles(
        int a1,
        int a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int *v6; // rsi
  unsigned int v7; // r10d
  __int64 v9; // rbx
  unsigned __int16 *v10; // r13
  unsigned __int8 *v11; // r14
  __int64 v12; // r9
  const OLECHAR *v13; // rdi
  BOOL ColorDirectory; // eax
  int *v15; // r8
  int *v16; // r9
  __int32 v17; // r10d
  __int64 v18; // rsi
  int v19; // eax
  DWORD v20; // ecx
  __int64 v21; // rax
  bool v22; // zf
  const unsigned __int16 *v23; // rcx
  DWORD v24; // ecx
  int v25; // eax
  int v26; // r14d
  int AdvancedColorState; // eax
  unsigned int v28; // edi
  int UsePerUserProfiles; // eax
  enum WCS_PROFILE_MANAGEMENT_SCOPE v30; // ecx
  unsigned int DeviceProfileEnumMode; // eax
  int v32; // edx
  enum WCS_PROFILE_MANAGEMENT_SCOPE v33; // ecx
  unsigned __int16 *v34; // rdi
  unsigned int v35; // r13d
  __int64 v36; // rsi
  int v37; // eax
  DWORD v38; // ecx
  int v39; // r14d
  int v40; // edx
  __int64 v41; // r8
  __int64 v42; // rsi
  int v43; // edx
  int v44; // r13d
  HANDLE v45; // rsi
  int v46; // eax
  DWORD v47; // ecx
  int matched; // r8d
  __int64 v49; // rax
  __int64 v50; // rdi
  unsigned int v51; // edx
  _WORD *v52; // r9
  unsigned int v53; // eax
  unsigned int v54; // ecx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int16 v57; // dx
  int v58; // r8d
  unsigned int v59; // r10d
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // edi
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // r9
  int v68; // [rsp+150h] [rbp-80h]
  unsigned int *v69; // [rsp+158h] [rbp-78h] BYREF
  unsigned __int16 *v70; // [rsp+160h] [rbp-70h] BYREF
  unsigned __int8 *v71; // [rsp+168h] [rbp-68h] BYREF
  unsigned int v72; // [rsp+170h] [rbp-60h] BYREF
  int v73; // [rsp+174h] [rbp-5Ch] BYREF
  int v74; // [rsp+178h] [rbp-58h] BYREF
  unsigned int v75; // [rsp+17Ch] [rbp-54h] BYREF
  int v76; // [rsp+180h] [rbp-50h] BYREF
  unsigned int v77; // [rsp+184h] [rbp-4Ch] BYREF
  int v78; // [rsp+188h] [rbp-48h] BYREF
  int v79; // [rsp+18Ch] [rbp-44h] BYREF
  const OLECHAR *v80; // [rsp+190h] [rbp-40h] BYREF
  int v81; // [rsp+198h] [rbp-38h] BYREF
  unsigned __int8 *v82; // [rsp+1A0h] [rbp-30h] BYREF
  unsigned __int16 *v83; // [rsp+1A8h] [rbp-28h] BYREF
  unsigned int v84; // [rsp+1B0h] [rbp-20h] BYREF
  unsigned int v85; // [rsp+1B4h] [rbp-1Ch] BYREF
  unsigned int v86; // [rsp+1B8h] [rbp-18h] BYREF
  unsigned int v87; // [rsp+1BCh] [rbp-14h] BYREF
  unsigned int v88; // [rsp+1C0h] [rbp-10h] BYREF
  unsigned int v89; // [rsp+1C4h] [rbp-Ch] BYREF
  DWORD pcbNeeded; // [rsp+1C8h] [rbp-8h] BYREF
  unsigned int v91; // [rsp+1CCh] [rbp-4h] BYREF
  int v92; // [rsp+1D0h] [rbp+0h]
  unsigned int v93; // [rsp+1D4h] [rbp+4h] BYREF
  unsigned int v94; // [rsp+1D8h] [rbp+8h] BYREF
  unsigned int v95; // [rsp+1DCh] [rbp+Ch] BYREF
  unsigned int v96; // [rsp+1E0h] [rbp+10h] BYREF
  unsigned int v97; // [rsp+1E4h] [rbp+14h] BYREF
  unsigned __int16 *v98; // [rsp+1E8h] [rbp+18h] BYREF
  const OLECHAR *v99; // [rsp+1F0h] [rbp+20h] BYREF
  LPVOID lpMem; // [rsp+1F8h] [rbp+28h]
  HANDLE hFindFile; // [rsp+200h] [rbp+30h]
  __int64 v102; // [rsp+208h] [rbp+38h] BYREF
  const OLECHAR *v103; // [rsp+210h] [rbp+40h] BYREF
  unsigned int *v104; // [rsp+218h] [rbp+48h] BYREF
  unsigned int *v105; // [rsp+220h] [rbp+50h] BYREF
  unsigned __int8 *v106; // [rsp+228h] [rbp+58h] BYREF
  unsigned __int8 *v107; // [rsp+230h] [rbp+60h] BYREF
  __int64 v108; // [rsp+238h] [rbp+68h] BYREF
  const OLECHAR *v109; // [rsp+240h] [rbp+70h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+250h] [rbp+80h] BYREF
  unsigned __int16 v111[264]; // [rsp+4A0h] [rbp+2D0h] BYREF
  WCHAR FileName[264]; // [rsp+6B0h] [rbp+4E0h] BYREF

  v6 = a6;
  v7 = 0;
  v9 = a3;
  v81 = a2;
  v73 = a1;
  LODWORD(a3) = a1;
  v69 = a6;
  v10 = 0;
  v70 = 0;
  v11 = 0;
  v83 = 0;
  v75 = 0;
  v68 = 0;
  pcbNeeded = 0;
  v78 = 0;
  lpMem = 0;
  v79 = 0;
  v92 = 0;
  hFindFile = (HANDLE)-1LL;
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v99 = (const OLECHAR *)v9;
    v76 = v12;
    LODWORD(v82) = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)&dword_18009E080,
      (__int64)word_180090DDA,
      a3,
      v12,
      (__int64)&v82,
      (__int64)&v76,
      (__int64)&v99);
    LODWORD(a3) = v73;
    v7 = 0;
  }
  if ( !a5 || !v9 )
  {
    v13 = L"Invalid parameter to EnumColorProfiles\n";
    goto LABEL_8;
  }
  if ( (unsigned int)a3 > 1 )
  {
    v13 = L"Invalid scope parameter to EnumColorProfiles\n";
LABEL_8:
    SetLastError(0x57u);
    goto LABEL_136;
  }
  if ( a4 )
  {
    if ( *a5 < 2 )
    {
      v13 = L"Invalid parameter to EnumColorProfiles - buffer too small\n";
      goto LABEL_8;
    }
    v72 = *a5;
  }
  else
  {
    v72 = v7;
  }
  if ( *(_DWORD *)(v9 + 4) < 0x300u )
  {
    if ( *(_DWORD *)(v9 + 4) != 512 )
    {
      v13 = L"Invalid parameter to EnumColorProfiles - Unknown version \n";
      goto LABEL_8;
    }
    if ( *(_DWORD *)v9 < 0x5Cu )
    {
      v13 = L"Invalid parameter to EnumColorProfiles - dwSize in enum record is too small for Version 2\n";
      goto LABEL_8;
    }
    if ( (*(_DWORD *)(v9 + 8) & 0x10000) != 0 )
    {
      v13 = L"Invalid parameter to EnumColorProfiles - Version 2 should not have ET_DEVICECLASS bit\n";
      goto LABEL_8;
    }
  }
  else if ( *(_DWORD *)v9 < 0x60u )
  {
    v13 = L"Invalid parameter to EnumColorProfiles - dwSize in enum record is too small\n";
    goto LABEL_8;
  }
  pcbNeeded = 520;
  ColorDirectory = InternalGetColorDirectory(0, v111, &pcbNeeded);
  v17 = 0;
  if ( !ColorDirectory )
  {
    v13 = L"Error getting color directory\n";
    goto LABEL_136;
  }
  v111[259] = 0;
  v18 = -1;
  do
    ++v18;
  while ( v111[v18] );
  if ( v111[(unsigned int)(v18 - 1)] != 92 )
  {
    v19 = StringCchCatW(v111, 0x104u, gszBackslash);
    v17 = 0;
    v20 = v19;
    if ( v19 < 0 )
    {
      v13 = L"StringCchCat failed, 0x%x.\n";
      if ( (v19 & 0x1FFF0000) == 0x70000 )
        v20 = (unsigned __int16)v19;
      SetLastError(v20);
      v6 = v69;
      v10 = v70;
      goto LABEL_136;
    }
    v21 = -1;
    do
      ++v21;
    while ( gszBackslash[v21] );
    LODWORD(v18) = v21 + v18;
  }
  v13 = &word_1800884E0;
  v80 = &word_1800884E0;
  *a5 = 0;
  v98 = &v111[(unsigned int)v18];
  if ( v69 )
    *v69 = 0;
  if ( a4 )
    *(_WORD *)a4 = 0;
  v22 = (*(_BYTE *)(v9 + 8) & 1) == 0;
  v11 = a4;
  v71 = a4;
  v82 = a4;
  if ( v22 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v43 = StringCchCopyW(FileName, 0x104u, v111);
    if ( v43 < 0 || (v43 = StringCchCatW(FileName, 0x104u, L"*"), v43 < 0) )
    {
      v24 = (unsigned __int16)v43;
      if ( (v43 & 0x1FFF0000) != 0x70000 )
        v24 = v43;
      goto LABEL_42;
    }
    v44 = 260 - v18;
    hFindFile = FindFirstFileW(FileName, &FindFileData);
    v45 = hFindFile;
    if ( hFindFile != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v46 = StringCchCopyW(v98, v44, FindFileData.cFileName);
          v47 = v46;
          if ( v46 < 0 )
            goto LABEL_106;
          matched = DoesProfileMatchEnumRecord(v111, v9);
          if ( matched )
          {
            v49 = -1;
            do
              ++v49;
            while ( FindFileData.cFileName[v49] );
            v50 = 2 * v49 + 2;
            v51 = v50 + *a5;
            *a5 = v51;
            if ( a4 && v51 <= (unsigned __int64)v72 - 2 )
            {
              if ( matched == 1 )
              {
                v46 = StringCbCopyW((unsigned __int16 *)a4, v50 + v72 - v51, FindFileData.cFileName);
                v47 = v46;
                if ( v46 < 0 )
                {
LABEL_106:
                  if ( (v46 & 0x1FFF0000) == 0x70000 )
                    v47 = (unsigned __int16)v47;
                  SetLastError(v47);
                  v13 = v80;
                  goto LABEL_43;
                }
              }
              else
              {
                InsertInBuffer(v11, a4, FindFileData.cFileName);
              }
              a4 += v50;
            }
            if ( v69 )
              ++*v69;
          }
        }
      }
      while ( FindNextFileW(v45, &FindFileData) );
      v13 = v80;
    }
    goto LABEL_116;
  }
  v23 = *(const unsigned __int16 **)(v9 + 16);
  v74 = 0;
  if ( !v23 )
  {
    v13 = L"Invalid parameter to EnumColorProfiles - device name in enum record is null\n";
LABEL_41:
    v24 = 87;
LABEL_42:
    SetLastError(v24);
    goto LABEL_43;
  }
  v25 = *(_DWORD *)(v9 + 8) & 0x20000;
  if ( (*(_DWORD *)(v9 + 8) & 0x40000) != 0 )
  {
    if ( v25 )
    {
      v13 = L"Invalid parameters to EnumColorProfiles - flags to search Advanced Color and Non-Advanced Color are both set.\n";
      goto LABEL_41;
    }
    v26 = 1;
  }
  else
  {
    v26 = 0;
    if ( !v25 )
    {
      v77 = 0;
      AdvancedColorState = InternalGetAdvancedColorState(
                             v23,
                             (enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *)&v77,
                             v15,
                             v16,
                             0);
      v17 = 0;
      if ( AdvancedColorState >= 0 && v77 && !(unsigned int)InternalIsLegacyColorManagedShimEnabled() )
        goto LABEL_52;
      v26 = v17;
    }
  }
  if ( (*(_DWORD *)(v9 + 8) & 0x10000) != 0 )
    v28 = *(_DWORD *)(v9 + 92);
  else
    v28 = 1936744803;
  if ( v73 == 1 )
  {
    UsePerUserProfiles = InternalGetUsePerUserProfiles(*(const unsigned __int16 **)(v9 + 16), v28, &v74);
    v17 = 0;
    if ( !UsePerUserProfiles )
    {
      v13 = v80;
      v11 = a4;
      v6 = v69;
      v10 = v70;
      goto LABEL_136;
    }
  }
  v30 = v17;
  LOBYTE(v30) = v74 != v17;
  DeviceProfileEnumMode = GetDeviceProfileEnumMode(v30, *(const unsigned __int16 **)(v9 + 16), v28, &v78);
  v32 = v78;
  if ( DeviceProfileEnumMode )
    v32 = 0;
  v76 = v32;
  if ( v73 == 1 )
  {
    if ( v74 )
    {
      v33 = WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER;
      goto LABEL_67;
    }
    if ( v81 != 1 )
    {
LABEL_69:
      v13 = v80;
LABEL_52:
      *a5 = 2;
      v68 = 1;
      v11 = a4;
LABEL_53:
      v6 = v69;
      v10 = v70;
      goto LABEL_136;
    }
  }
  v33 = WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE;
LABEL_67:
  if ( GetAssociatedProfileList(v33, *(const unsigned __int16 **)(v9 + 16), v28, 1, v26, &v83, &v75) )
  {
    v10 = v83;
    v11 = a4;
    v13 = v80;
    goto LABEL_128;
  }
  v34 = v83;
  v70 = v83;
  if ( !v83 )
    goto LABEL_69;
  v71 = a4;
  if ( !*v83 )
  {
    v13 = v80;
    v11 = a4;
LABEL_116:
    *a5 += 2;
    v92 = 1;
    if ( !a4 || *a5 > v72 )
    {
      SetLastError(0x7Au);
      goto LABEL_43;
    }
    *(_WORD *)a4 = 0;
    v68 = 1;
    if ( !v11 || *a5 < 4 || *a5 >= 0xF000 )
      goto LABEL_53;
    lpMem = (LPVOID)MemAlloc(*a5);
    v52 = lpMem;
    if ( lpMem )
    {
      v53 = 0;
      v54 = *a5 >> 1;
      v22 = v54 == 2;
      v55 = v54 - 2;
      if ( !v22 )
      {
        do
        {
          v56 = v53;
          v57 = *(_WORD *)&v11[2 * v53];
          if ( !v57 )
            v57 = 124;
          ++v53;
          v52[v56] = v57;
        }
        while ( v53 < (unsigned int)v55 );
      }
      v52[v55] = 0;
      v79 = 1;
      goto LABEL_53;
    }
    v10 = v70;
LABEL_128:
    v6 = v69;
    goto LABEL_136;
  }
  v35 = 260 - v18;
  while ( 1 )
  {
    v36 = -1;
    do
      ++v36;
    while ( v34[v36] );
    v37 = StringCchCopyW(v98, v35, v34);
    v38 = v37;
    if ( v37 < 0 )
      break;
    v39 = v36 + 1;
    if ( v76 )
    {
      v40 = 2;
    }
    else
    {
      v40 = DoesProfileMatchEnumRecord(v111, v9);
      if ( !v40 )
        goto LABEL_87;
    }
    if ( a4 )
    {
      v41 = *a5;
      v42 = 2LL * v39;
      if ( v42 + v41 <= (unsigned __int64)v72 - 2 )
      {
        if ( v40 == 1 )
        {
          v37 = StringCbCopyW((unsigned __int16 *)a4, v72 - (unsigned int)v41, v34);
          v38 = v37;
          if ( v37 < 0 )
          {
            v13 = L"StringCbCopy failed: 0x%x\n";
            goto LABEL_90;
          }
        }
        else
        {
          InsertInBuffer(v71, a4, v34);
        }
        a4 += v42;
      }
    }
    *a5 += 2 * v39;
    if ( v69 )
      ++*v69;
LABEL_87:
    v34 += v39;
    if ( !*v34 )
    {
      v13 = v80;
      v11 = v82;
      goto LABEL_116;
    }
  }
  v13 = L"StringCchCopy failed: 0x%x\n";
LABEL_90:
  if ( (v37 & 0x1FFF0000) == 0x70000 )
    v38 = (unsigned __int16)v38;
  SetLastError(v38);
  v11 = v71;
LABEL_43:
  v6 = v69;
  v10 = v70;
LABEL_136:
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v103 = (const OLECHAR *)lpMem;
    LODWORD(v98) = v79;
    v102 = 0x2000000;
    if ( v58 && v6 )
      v60 = *v6;
    else
      v60 = v59;
    LODWORD(v83) = v60;
    v104 = v6;
    if ( a4 && a5 )
      v61 = *a5;
    else
      v61 = v59;
    LODWORD(v80) = v61;
    v105 = a5;
    v106 = v11;
    v107 = a4;
    if ( v9 )
    {
      v22 = (*(_BYTE *)(v9 + 8) & 1) == 0;
      v79 = *(_DWORD *)(v9 + 92);
      v78 = *(_DWORD *)(v9 + 88);
      v77 = *(_DWORD *)(v9 + 84);
      v75 = *(_DWORD *)(v9 + 80);
      v74 = *(_DWORD *)(v9 + 76);
      v72 = *(_DWORD *)(v9 + 72);
      v91 = *(_DWORD *)(v9 + 68);
      v93 = *(_DWORD *)(v9 + 64);
      v95 = *(_DWORD *)(v9 + 60);
      v96 = *(_DWORD *)(v9 + 56);
      v97 = *(_DWORD *)(v9 + 52);
      v84 = *(_DWORD *)(v9 + 48);
      v85 = *(_DWORD *)(v9 + 44);
      v94 = *(_DWORD *)(v9 + 40);
      v86 = *(_DWORD *)(v9 + 36);
      v87 = *(_DWORD *)(v9 + 32);
      v88 = *(_DWORD *)(v9 + 28);
      v89 = *(_DWORD *)(v9 + 24);
      if ( !v22 )
      {
        v99 = *(const OLECHAR **)(v9 + 16);
        goto LABEL_151;
      }
    }
    else
    {
      v79 = v59;
      v78 = v59;
      v77 = v59;
      v75 = v59;
      v74 = v59;
      v72 = v59;
      v91 = v59;
      v93 = v59;
      v95 = v59;
      v96 = v59;
      v97 = v59;
      v84 = v59;
      v85 = v59;
      v94 = v59;
      v86 = v59;
      v87 = v59;
      v88 = v59;
      v89 = v59;
    }
    v99 = &word_1800884E0;
    if ( v9 )
    {
LABEL_151:
      LODWORD(v82) = *(_DWORD *)(v9 + 8);
      v76 = *(_DWORD *)(v9 + 4);
      v62 = *(_DWORD *)v9;
    }
    else
    {
      LODWORD(v82) = v59;
      v62 = v59;
      v76 = v59;
    }
    LODWORD(v71) = v62;
    v108 = v9;
    v109 = v13;
    LODWORD(v70) = GetLastError();
    v63 = v68;
    LODWORD(v69) = v68;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v64,
      (__int64)byte_1800914AB,
      v65,
      v66,
      (__int64)&v69,
      (__int64)&v70,
      &v109,
      (__int64)&v73,
      (__int64)&v81,
      (__int64)&v108,
      (__int64)&v71,
      (__int64)&v76,
      (__int64)&v82,
      &v99,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v87,
      (__int64)&v86,
      (__int64)&v94,
      (__int64)&v85,
      (__int64)&v84,
      (__int64)&v97,
      (__int64)&v96,
      (__int64)&v95,
      (__int64)&v93,
      (__int64)&v91,
      (__int64)&v72,
      (__int64)&v74,
      (__int64)&v75,
      (__int64)&v77,
      (__int64)&v78,
      (__int64)&v79,
      (__int64)&v107,
      (__int64)&v106,
      (__int64)&v105,
      (__int64)&v80,
      (__int64)&v104,
      (__int64)&v83,
      (__int64)&v98,
      &v103,
      (__int64)&v102);
  }
  else
  {
    v63 = v68;
  }
  if ( !v63 && !a4 && !v92 && GetLastError() == 122 )
    SetLastError(0x57u);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  if ( v10 )
    MemFree(v10);
  if ( lpMem )
    MemFree(lpMem);
  return v63;
}

```

## disassembly

```asm
0x18001d6f4  mov     [rsp-8+arg_0], rbx
0x18001d6f9  push    rbp
0x18001d6fa  push    rsi
0x18001d6fb  push    rdi
0x18001d6fc  push    r12
0x18001d6fe  push    r13
0x18001d700  push    r14
0x18001d702  push    r15
0x18001d704  lea     rbp, [rsp-700h]
0x18001d70c  sub     rsp, 8D0h
0x18001d713  mov     rax, cs:__security_cookie
0x18001d71a  xor     rax, rsp
0x18001d71d  mov     [rbp+730h+var_40], rax
0x18001d724  mov     rsi, [rbp+730h+arg_28]
0x18001d72b  xor     r10d, r10d
0x18001d72e  mov     eax, cs:dword_18009E080
0x18001d734  mov     r15, r9
0x18001d737  mov     r12, [rbp+730h+arg_20]
0x18001d73e  mov     rbx, r8
0x18001d741  mov     [rbp+730h+var_768], edx
0x18001d744  mov     r9d, edx
0x18001d747  mov     [rbp+730h+var_78C], ecx
0x18001d74a  mov     r8d, ecx
0x18001d74d  mov     [rbp+730h+var_7A8], rsi
0x18001d751  mov     r13d, r10d
0x18001d754  mov     [rbp+730h+var_7A0], r10
0x18001d758  mov     r14d, r10d
0x18001d75b  mov     [rbp+730h+var_758], r10
0x18001d75f  mov     [rbp+730h+var_784], r10d
0x18001d763  mov     [rbp+730h+var_7B0], r10d
0x18001d767  mov     [rbp+730h+pcbNeeded], r10d
0x18001d76b  mov     [rbp+730h+var_778], r10d
0x18001d76f  mov     [rbp+730h+lpMem], r10
0x18001d773  mov     [rbp+730h+var_774], r10d
0x18001d777  mov     [rbp+730h+var_730], r10d
0x18001d77b  mov     [rbp+730h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18001d783  cmp     eax, 5
0x18001d786  jbe     short loc_18001D7E3
0x18001d788  mov     rdx, 200000000000h
0x18001d792  lea     rcx, dword_18009E080
0x18001d799  call    _tlgKeywordOn
0x18001d79e  test    al, al
0x18001d7a0  jz      short loc_18001D7E3
0x18001d7a2  lea     rax, [rbp+730h+var_710]
0x18001d7a6  mov     [rbp+730h+var_710], rbx
0x18001d7aa  mov     [rsp+900h+var_8D0], rax
0x18001d7af  lea     rdx, word_180090DDA
0x18001d7b6  lea     rax, [rbp+730h+var_780]
0x18001d7ba  mov     [rbp+730h+var_780], r9d
0x18001d7be  mov     [rsp+900h+var_8D8], rax
0x18001d7c3  lea     rcx, dword_18009E080
0x18001d7ca  lea     rax, [rbp+730h+var_760]
0x18001d7ce  mov     dword ptr [rbp+730h+var_760], r8d
0x18001d7d2  mov     [rsp+900h+var_8E0], rax
0x18001d7d7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001d7dc  mov     r8d, [rbp+730h+var_78C]
0x18001d7e0  xor     r10d, r10d
0x18001d7e3  mov     eax, 57h ; 'W'
0x18001d7e8  test    r12, r12
0x18001d7eb  jz      loc_18001DE8C
0x18001d7f1  test    rbx, rbx
0x18001d7f4  jz      loc_18001DE8C
0x18001d7fa  cmp     r8d, 1
0x18001d7fe  jbe     short loc_18001D81A
0x18001d800  lea     rdi, aInvalidScopePa; "Invalid scope parameter to EnumColorPro"...
0x18001d807  mov     ecx, eax; dwErrCode
0x18001d809  call    cs:__imp_SetLastError
0x18001d80f  mov     r8d, r13d
0x18001d812  xor     r10d, r10d
0x18001d815  jmp     loc_18001DEAA
0x18001d81a  test    r15, r15
0x18001d81d  jz      short loc_18001D83D
0x18001d81f  cmp     dword ptr [r12], 2
0x18001d824  jnb     short loc_18001D82F
0x18001d826  lea     rdi, aInvalidParamet_5; "Invalid parameter to EnumColorProfiles "...
0x18001d82d  jmp     short loc_18001D807
0x18001d82f  mov     eax, [r12]
0x18001d833  mov     [rbp+730h+var_790], eax
0x18001d836  mov     eax, 57h ; 'W'
0x18001d83b  jmp     short loc_18001D841
0x18001d83d  mov     [rbp+730h+var_790], r10d
0x18001d841  cmp     dword ptr [rbx+4], 300h
0x18001d848  mov     edi, 5Ch ; '\'
0x18001d84d  jb      short loc_18001D85D
0x18001d84f  cmp     dword ptr [rbx], 60h ; '`'
0x18001d852  jnb     short loc_18001D88C
0x18001d854  lea     rdi, aInvalidParamet_6; "Invalid parameter to EnumColorProfiles "...
0x18001d85b  jmp     short loc_18001D807
0x18001d85d  cmp     dword ptr [rbx+4], 200h
0x18001d864  jnz     loc_18001DE80
0x18001d86a  cmp     [rbx], edi
0x18001d86c  jnb     short loc_18001D877
0x18001d86e  lea     rdi, aInvalidParamet_0; "Invalid parameter to EnumColorProfiles "...
0x18001d875  jmp     short loc_18001D807
0x18001d877  test    dword ptr [rbx+8], 10000h
0x18001d87e  jz      short loc_18001D88C
0x18001d880  lea     rdi, aInvalidParamet_2; "Invalid parameter to EnumColorProfiles "...
0x18001d887  jmp     loc_18001D807
0x18001d88c  lea     r8, [rbp+730h+pcbNeeded]; pcbNeeded
0x18001d890  mov     [rbp+730h+pcbNeeded], 208h
0x18001d897  lea     rdx, [rbp+730h+var_460]; unsigned __int16 *
0x18001d89e  xor     ecx, ecx; pName
0x18001d8a0  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x18001d8a5  xor     r10d, r10d
0x18001d8a8  test    eax, eax
0x18001d8aa  jnz     short loc_18001D8B8
0x18001d8ac  lea     rdi, aErrorGettingCo; "Error getting color directory\n"
0x18001d8b3  jmp     loc_18001DEA7
0x18001d8b8  mov     [rbp+730h+var_25A], r10w
0x18001d8c0  lea     rax, [rbp+730h+var_460]
0x18001d8c7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001d8cb  inc     rsi
0x18001d8ce  cmp     [rax+rsi*2], r10w
0x18001d8d3  jnz     short loc_18001D8CB
0x18001d8d5  lea     eax, [rsi-1]
0x18001d8d8  mov     r13d, 104h
0x18001d8de  cmp     [rbp+rax*2+730h+var_460], di
0x18001d8e6  jz      short loc_18001D946
0x18001d8e8  lea     rdi, gszBackslash; "\\"
0x18001d8ef  mov     edx, r13d; unsigned __int64
0x18001d8f2  mov     r8, rdi; unsigned __int16 *
0x18001d8f5  lea     rcx, [rbp+730h+var_460]; unsigned __int16 *
0x18001d8fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d901  xor     r10d, r10d
0x18001d904  mov     ecx, eax
0x18001d906  test    eax, eax
0x18001d908  jns     short loc_18001D936
0x18001d90a  and     eax, 1FFF0000h
0x18001d90f  lea     rdi, aStringcchcatFa; "StringCchCat failed, 0x%x.\n"
0x18001d916  cmp     eax, 70000h
0x18001d91b  jnz     short loc_18001D920
0x18001d91d  movzx   ecx, cx; dwErrCode
0x18001d920  call    cs:__imp_SetLastError
0x18001d926  mov     rsi, [rbp+730h+var_7A8]
0x18001d92a  mov     r8d, r14d
0x18001d92d  mov     r13, [rbp+730h+var_7A0]
0x18001d931  jmp     loc_18001D812
0x18001d936  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d93a  inc     rax
0x18001d93d  cmp     [rdi+rax*2], r10w
0x18001d942  jnz     short loc_18001D93A
0x18001d944  add     esi, eax
0x18001d946  mov     eax, esi
0x18001d948  lea     rdi, word_1800884E0
0x18001d94f  mov     [rbp+730h+var_770], rdi
0x18001d953  mov     [r12], r10d
0x18001d957  lea     rax, [rbp+rax*2+730h+var_460]
0x18001d95f  mov     [rbp+730h+var_718], rax
0x18001d963  mov     rax, [rbp+730h+var_7A8]
0x18001d967  test    rax, rax
0x18001d96a  jz      short loc_18001D96F
0x18001d96c  mov     [rax], r10d
0x18001d96f  test    r15, r15
0x18001d972  jz      short loc_18001D978
0x18001d974  mov     [r15], r10w
0x18001d978  test    byte ptr [rbx+8], 1
0x18001d97c  mov     r14, r15
0x18001d97f  mov     [rbp+730h+var_798], r15
0x18001d983  mov     [rbp+730h+var_760], r15
0x18001d987  jz      loc_18001DC1E
0x18001d98d  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001d991  mov     [rbp+730h+var_788], r10d
0x18001d995  test    rcx, rcx
0x18001d998  jnz     short loc_18001D9BD
0x18001d99a  lea     rdi, aInvalidParamet; "Invalid parameter to EnumColorProfiles "...
0x18001d9a1  mov     ecx, 57h ; 'W'; dwErrCode
0x18001d9a6  call    cs:__imp_SetLastError
0x18001d9ac  mov     rsi, [rbp+730h+var_7A8]
0x18001d9b0  mov     r13, [rbp+730h+var_7A0]
0x18001d9b4  mov     r8d, [rbp+730h+var_7B0]
0x18001d9b8  jmp     loc_18001D812
0x18001d9bd  mov     eax, [rbx+8]
0x18001d9c0  and     eax, 20000h
0x18001d9c5  test    dword ptr [rbx+8], 40000h
0x18001d9cc  jz      short loc_18001D9E3
0x18001d9ce  test    eax, eax
0x18001d9d0  jz      short loc_18001D9DB
0x18001d9d2  lea     rdi, aInvalidParamet_1; "Invalid parameters to EnumColorProfiles"...
0x18001d9d9  jmp     short loc_18001D9A1
0x18001d9db  mov     r14d, 1
0x18001d9e1  jmp     short loc_18001DA37
0x18001d9e3  mov     r14d, r10d
0x18001d9e6  test    eax, eax
0x18001d9e8  jnz     short loc_18001DA37
0x18001d9ea  lea     rdx, [rbp+730h+var_77C]; enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *
0x18001d9ee  mov     [rbp+730h+var_77C], r10d
0x18001d9f2  mov     [rsp+900h+var_8E0], r10; struct DISPLAYCONFIG_PATH_TARGET_INFO *
0x18001d9f7  call    ?InternalGetAdvancedColorState@@YAJPEBGPEAW4_DISPLAYCONFIG_ADVANCED_COLOR_MODE@@PEAH2PEAUDISPLAYCONFIG_PATH_TARGET_INFO@@@Z; InternalGetAdvancedColorState(ushort const *,_DISPLAYCONFIG_ADVANCED_COLOR_MODE *,int *,int *,DISPLAYCONFIG_PATH_TARGET_INFO *)
0x18001d9fc  xor     r10d, r10d
0x18001d9ff  test    eax, eax
0x18001da01  js      short loc_18001DA34
0x18001da03  cmp     [rbp+730h+var_77C], r10d
0x18001da07  jz      short loc_18001DA34
0x18001da09  call    ?InternalIsLegacyColorManagedShimEnabled@@YAHXZ; InternalIsLegacyColorManagedShimEnabled(void)
0x18001da0e  test    eax, eax
0x18001da10  jnz     short loc_18001DA34
0x18001da12  mov     r8d, 1
0x18001da18  mov     dword ptr [r12], 2
0x18001da20  mov     [rbp+730h+var_7B0], r8d
0x18001da24  mov     r14, r15
0x18001da27  mov     rsi, [rbp+730h+var_7A8]
0x18001da2b  mov     r13, [rbp+730h+var_7A0]
0x18001da2f  jmp     loc_18001DEAA
0x18001da34  mov     r14d, r10d
0x18001da37  test    dword ptr [rbx+8], 10000h
0x18001da3e  jz      short loc_18001DA45
0x18001da40  mov     edi, [rbx+5Ch]
0x18001da43  jmp     short loc_18001DA4A
0x18001da45  mov     edi, 73706163h
0x18001da4a  cmp     [rbp+730h+var_78C], 1
0x18001da4e  jnz     short loc_18001DA6A
0x18001da50  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001da54  lea     r8, [rbp+730h+var_788]; int *
0x18001da58  mov     edx, edi; unsigned int
0x18001da5a  call    ?InternalGetUsePerUserProfiles@@YAHPEBGKPEAH@Z; InternalGetUsePerUserProfiles(ushort const *,ulong,int *)
0x18001da5f  xor     r10d, r10d
0x18001da62  test    eax, eax
0x18001da64  jz      loc_18001DE98
0x18001da6a  cmp     [rbp+730h+var_788], r10d
0x18001da6e  lea     r9, [rbp+730h+var_778]; int *
0x18001da72  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18001da76  mov     ecx, r10d
0x18001da79  setnz   cl; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18001da7c  mov     r8d, edi; unsigned int
0x18001da7f  call    ?GetDeviceProfileEnumMode@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKPEAH@Z; GetDeviceProfileEnumMode(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int *)
0x18001da84  mov     edx, [rbp+730h+var_778]
0x18001da87  xor     r10d, r10d
0x18001da8a  test    eax, eax
0x18001da8c  cmovnz  edx, r10d
0x18001da90  cmp     [rbp+730h+var_78C], 1
0x18001da94  mov     [rbp+730h+var_780], edx
0x18001da97  jnz     short loc_18001DAAE
0x18001da99  cmp     [rbp+730h+var_788], r10d
0x18001da9d  jz      short loc_18001DAA8
0x18001da9f  lea     r9d, [r10+1]
0x18001daa3  mov     ecx, r9d
0x18001daa6  jmp     short loc_18001DAB4
0x18001daa8  cmp     [rbp+730h+var_768], 1
0x18001daac  jnz     short loc_18001DAEF
0x18001daae  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18001dab0  lea     r9d, [rcx+1]; int
0x18001dab4  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18001dab8  lea     rax, [rbp+730h+var_784]
0x18001dabc  mov     [rsp+900h+var_8D0], rax; unsigned int *
0x18001dac1  mov     r8d, edi; unsigned int
0x18001dac4  lea     rax, [rbp+730h+var_758]
0x18001dac8  mov     [rsp+900h+var_8D8], rax; unsigned __int16 **
0x18001dacd  mov     dword ptr [rsp+900h+var_8E0], r14d; int
0x18001dad2  call    ?GetAssociatedProfileList@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKHHPEAPEAGPEAK@Z; GetAssociatedProfileList(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int,int,ushort * *,ulong *)
0x18001dad7  xor     r10d, r10d
0x18001dada  test    eax, eax
0x18001dadc  jnz     loc_18001DC0E
0x18001dae2  mov     rdi, [rbp+730h+var_758]
0x18001dae6  mov     [rbp+730h+var_7A0], rdi
0x18001daea  test    rdi, rdi
0x18001daed  jnz     short loc_18001DAF8
0x18001daef  mov     rdi, [rbp+730h+var_770]
0x18001daf3  jmp     loc_18001DA12
0x18001daf8  mov     [rbp+730h+var_798], r15
0x18001dafc  cmp     [rdi], r10w
0x18001db00  jz      loc_18001DD95
0x18001db06  sub     r13d, esi
0x18001db09  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001db0d  inc     rsi
0x18001db10  cmp     [rdi+rsi*2], r10w
0x18001db15  jnz     short loc_18001DB0D
0x18001db17  mov     rcx, [rbp+730h+var_718]; unsigned __int16 *
0x18001db1b  mov     r8, rdi; unsigned __int16 *
0x18001db1e  mov     rdx, r13; unsigned __int64
0x18001db21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001db26  xor     r10d, r10d
0x18001db29  mov     ecx, eax
0x18001db2b  test    eax, eax
0x18001db2d  js      loc_18001DBE9
0x18001db33  lea     r14d, [rsi+1]
0x18001db37  cmp     [rbp+730h+var_780], r10d
0x18001db3b  jz      short loc_18001DB43
0x18001db3d  lea     edx, [r10+2]
0x18001db41  jmp     short loc_18001DB5B
0x18001db43  mov     rdx, rbx
0x18001db46  lea     rcx, [rbp+730h+var_460]
0x18001db4d  call    ?DoesProfileMatchEnumRecord@@YA?AW4MATCHTYPE@@PEAGPEAUtagENUMTYPEW@@@Z; DoesProfileMatchEnumRecord(ushort *,tagENUMTYPEW *)
0x18001db52  xor     r10d, r10d
0x18001db55  mov     edx, eax
0x18001db57  test    eax, eax
0x18001db59  jz      short loc_18001DBCB
0x18001db5b  test    r15, r15
0x18001db5e  jz      short loc_18001DBB8
0x18001db60  mov     r8d, [r12]
0x18001db64  mov     r9d, [rbp+730h+var_790]
0x18001db68  movsxd  rsi, r14d
0x18001db6b  add     rsi, rsi
0x18001db6e  lea     rax, [r9-2]
0x18001db72  lea     rcx, [rsi+r8]
0x18001db76  cmp     rcx, rax
0x18001db79  ja      short loc_18001DBB8
0x18001db7b  cmp     edx, 1
0x18001db7e  jnz     short loc_18001DBA3
0x18001db80  mov     edx, r9d
0x18001db83  mov     rcx, r15; unsigned __int16 *
  ... truncated ...
```
