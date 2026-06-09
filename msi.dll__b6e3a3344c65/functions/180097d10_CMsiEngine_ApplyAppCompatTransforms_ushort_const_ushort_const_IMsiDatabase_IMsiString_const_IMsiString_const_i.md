# CMsiEngine::ApplyAppCompatTransforms(ushort const *,ushort const *,IMsiDatabase &,IMsiString const &,IMsiString const &,iacpAppCompatTransformApplyPoint,iacsAppCompatShimFlags &,bool,bool,bool &)

- ea: `0x180097d10`
- end: `0x180098b4a`
- name: `?ApplyAppCompatTransforms@CMsiEngine@@IEAA_NPEBG0AEAVIMsiDatabase@@AEBVIMsiString@@2W4iacpAppCompatTransformApplyPoint@@AEAW4iacsAppCompatShimFlags@@_N5AEA_N@Z`
- size: `3642`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f94d0`

## callees

- `0x18001db00`
- `0x180025a18`
- `0x180035a8c`
- `0x1800620e4`
- `0x180066074`
- `0x180076e28`
- `0x1800976bc`
- `0x180097d10`
- `0x180098b50`
- `0x180098bd8`
- `0x18011414c`
- `0x180148078`
- `0x1802149e0`
- `0x180215198`
- `0x1802152f0`
- `0x18021537c`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!wcstol` at `0x18009800b`
- `msvcrt!wcstol` at `0x1800980a2`
- `msvcrt!wcstol` at `0x180098130`
- `msvcrt!wcstol` at `0x18009800b`
- `msvcrt!wcstol` at `0x1800980a2`
- `msvcrt!wcstol` at `0x180098130`

## string_xrefs

- `0x180097dc7`: `CLIENTPROCESSID`
- `0x1800981c3`: `\SystemRoot\AppPatch\msimain.sdb`
- `0x1800980d1`: `ShimServicePackLevel`
- `0x180098061`: `APPCOMPAT: Uninstall VersionNT override found.`
- `0x180097fcf`: `APPCOMPAT: Uninstall Flags override found.`
- `0x180097f2a`: `APPCOMPAT: Compatibility mode property overrides found.`
- `0x1800980ef`: `APPCOMPAT: Uninstall ServicePackLevel override found.`
- `0x1800981ea`: `APPCOMPAT: unable to initialize database.`
- `0x180098324`: `APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...`
- `0x18009887f`: `APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...`
- `0x180098245`: `APPCOMPAT: looking for appcompat database entry with ProductCode '%s'.`
- `0x1800983f1`: `APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.`
- `0x180098920`: `APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.`
- `0x1800983a8`: `APPCOMPAT: found matching ProductCode in database, but other attributes do not match.`
- `0x1800988fc`: `APPCOMPAT: found matching ProductCode in database, but other attributes do not match.`
- `0x180098623`: `APPCOMPAT: ApphelpCheckMsiPackage returned FALSE.  This product will not be installed due to application compatibility concerns.`
- `0x180098478`: `APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.`
- `0x1800989a7`: `APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.`
- `0x180098577`: `APPCOMPAT: Failed to apply appcompat transform.`
- `0x180098aa6`: `APPCOMPAT: Failed to apply appcompat transform.`
- `0x180098694`: `APPCOMPAT: Failed to determine temp directory for appcompat transforms.`
- `0x1800985fc`: `APPCOMPAT: No redistributable processing. One or more matching SDB entries contain 'Skip redistributable checks' flag.`
- `0x1800986d6`: `APPCOMPAT: no matching ProductCode found in database.`
- `0x1800987e5`: `APPCOMPAT: no matching ProductCode found in database.`
- `0x180098785`: `APPCOMPAT: Failed to add redistributable data to table.`
- `0x180098747`: `APPCOMPAT: Failed to create redistributable table.`

## pseudocode

```c
char __fastcall CMsiEngine::ApplyAppCompatTransforms(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IMsiDatabase *a4,
        __int64 *a5,
        __int64 a6,
        unsigned int a7,
        int *a8,
        unsigned __int8 a9,
        char a10,
        _BYTE *a11)
{
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rdi
  int v19; // eax
  const WCHAR *v20; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rax
  int v23; // eax
  __int64 v24; // rax
  const WCHAR *v25; // rax
  int v26; // eax
  const WCHAR *v27; // rax
  char v28; // r14
  void *inited; // rdi
  const unsigned __int16 *v31; // rax
  __int64 v32; // rax
  unsigned int v33; // esi
  unsigned int v34; // eax
  __int64 v35; // r8
  const unsigned __int16 *v36; // r9
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  struct IMsiPath *v39; // rax
  struct IMsiPath **v40; // rax
  const unsigned __int16 *v41; // r9
  struct IMsiTable **v42; // rax
  unsigned int v43; // eax
  const unsigned __int16 *v44; // r9
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  struct IMsiPath *v47; // rax
  struct IMsiPath **v48; // rax
  struct IMsiPath *v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h]
  void *v51; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v52; // [rsp+88h] [rbp-78h]
  __int128 v53; // [rsp+90h] [rbp-70h] BYREF
  __int128 v54; // [rsp+A0h] [rbp-60h]
  __int128 v55; // [rsp+B0h] [rbp-50h] BYREF
  int v56; // [rsp+C0h] [rbp-40h]
  _BYTE v57[80]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String; // [rsp+120h] [rbp+20h] BYREF
  int v59; // [rsp+128h] [rbp+28h]
  int v60; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v61[496]; // [rsp+130h] [rbp+30h] BYREF

  v50 = a6;
  v52 = a11;
  memset_0(v57, 0, 0x48u);
  *a8 = 0;
  *a11 = 0;
  if ( a7 == 1 )
  {
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v51 = &MsiString::s_NullString;
    v49 = (struct IMsiPath *)&MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, struct IMsiPath **))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"CLIENTPROCESSID",
      &v49);
    ProcessCommandLine(a3, 0, 0, 0, 0, 0, 0, v49, &v51, 1, 0, 0, 0);
    (*(void (__fastcall **)(struct IMsiPath *))(*(_QWORD *)v49 + 16LL))(v49);
    *a8 = 0;
    *(_OWORD *)(a1 + 2064) = 0;
    *(_OWORD *)(a1 + 2080) = 0;
    *(_OWORD *)(a1 + 2096) = 0;
    *(_QWORD *)(a1 + 2112) = 0;
    *(_DWORD *)(a1 + 2064) = 1;
    *(_DWORD *)(a1 + 2068) = 56;
    v15 = (*(__int64 (__fastcall **)(__int64 *))(*a5 + 80))(a5);
    v16 = v50;
    *(_QWORD *)(a1 + 2072) = v15;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 80LL))(v16);
    *(_QWORD *)(a1 + 2088) = a2;
    v18 = v51;
    *(_QWORD *)(a1 + 2080) = v17;
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v18 + 56LL))(v18) )
      v19 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v18 + 32LL))(v18);
    else
      v19 = 0;
    *(_DWORD *)(a1 + 2096) = v19;
    v20 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(*a5 + 80))(a5);
    if ( ((MsiQueryProductStateW(v20) - 1) & 0xFFFFFFFB) != 0 )
    {
      if ( (unsigned int)((__int64 (__fastcall *)(__int64))APPHELP::ApphelpGetMsiProperties)(a1 + 2064) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: Compatibility mode property overrides found.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        *a8 = *(_DWORD *)(a1 + 2100);
      }
    }
    else
    {
      memset_0(v61, 0, 0xC8u);
      String = (wchar_t *)v61;
      v21 = *a5;
      v59 = 100;
      v60 = 100;
      v22 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(v21 + 80))(a5);
      if ( (unsigned int)GetProductInfo(v22, L"ShimFlags") )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: Uninstall Flags override found.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v23 = wcstol(String, 0, 10);
        *(_DWORD *)(a1 + 2100) = v23;
        *a8 = v23;
      }
      v24 = *a5;
      v60 = 100;
      v25 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(v24 + 80))(a5);
      if ( (unsigned int)GetProductInfo(v25, L"ShimVersionNT") )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: Uninstall VersionNT override found.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v26 = wcstol(String, 0, 10);
        v60 = 100;
        *(_DWORD *)(a1 + 2104) = v26;
        *(_DWORD *)(a1 + 2108) = v26;
        v27 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *))(*a5 + 80))(a5);
        if ( (unsigned int)GetProductInfo(v27, L"ShimServicePackLevel") )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"APPCOMPAT: Uninstall ServicePackLevel override found.",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          *(_DWORD *)(a1 + 2112) = wcstol(String, 0, 10);
        }
      }
      if ( v59 > 100 )
        operator delete(String);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v28 = 0;
  if ( a10 && !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 592LL))(a1, 256) )
  {
    *(_BYTE *)(a1 + 2024) = 0;
    *(_OWORD *)(a1 + 2028) = 0;
    *(_OWORD *)(a1 + 2044) = 0;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl'::`2'::impl);
  inited = (void *)APPHELP::SdbInitDatabase();
  if ( !inited )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: unable to initialize database.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    return 0;
  }
  if ( g_dmDiagnosticMode )
  {
    v31 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(*a5 + 80))(a5);
    DebugString(
      9,
      0,
      0,
      L"APPCOMPAT: looking for appcompat database entry with ProductCode '%s'.",
      v31,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v32 = (*(__int64 (__fastcall **)(__int64 *))(*a5 + 80))(a5);
  v33 = ((__int64 (__fastcall *)(void *, __int64, _QWORD, _BYTE *))APPHELP::SdbFindFirstMsiPackage_Str)(
          inited,
          v32,
          0,
          v57);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl'::`2'::impl) )
  {
    if ( !v33 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: no matching ProductCode found in database.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_112;
    }
    v49 = 0;
    while ( 1 )
    {
      memset_0(&String, 0, 0x1FEu);
      v43 = ((__int64 (__fastcall *)(void *, _QWORD, __int64))APPHELP::SdbFindFirstTagRef)(inited, v33, 24577);
      if ( v43 )
        ((void (__fastcall *)(void *, _QWORD, wchar_t **, __int64))APPHELP::SdbReadStringTagRef)(
          inited,
          v43,
          &String,
          255);
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...",
          (const unsigned __int16 *)&String,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( (unsigned __int8)FIsMatchingAppCompatEntry(inited, v33, v50, a7, a1 + 2104, a1 + 2112, a1, a4) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        *a8 = GetShimFlags(inited, v33);
        v56 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        if ( (unsigned int)((__int64 (__fastcall *)(void *, _QWORD, __int128 *))APPHELP::SdbGetMsiPackageInformation)(
                             inited,
                             v33,
                             &v53) )
        {
          if ( (v56 & 1) != 0
            && !(unsigned int)((__int64 (__fastcall *)(__int128 *, __int128 *, _QWORD, _QWORD))APPHELP::ApphelpCheckMsiPackage)(
                                &v55,
                                &v53,
                                0,
                                a9) )
          {
LABEL_66:
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"APPCOMPAT: ApphelpCheckMsiPackage returned FALSE.  This product will not be installed due to application"
                 " compatibility concerns.",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            *v52 = 1;
LABEL_69:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
            ((void (__fastcall *)(void *))APPHELP::SdbReleaseDatabase)(inited);
            return 0;
          }
          if ( !*(_BYTE *)(a1 + 2024)
            && (unsigned int)((__int64 (__fastcall *)(void *, _QWORD, __int64))APPHELP::SdbFindFirstTagRef)(
                               inited,
                               v33,
                               28692) )
          {
            v45 = v55;
            *(_BYTE *)(a1 + 2024) = 1;
            v46 = v53;
            *(_OWORD *)(a1 + 2028) = v45;
            *(_OWORD *)(a1 + 2044) = v46;
          }
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            9,
            0,
            0,
            L"APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v47 = v49;
        if ( !v49 )
        {
          v48 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v49);
          if ( !GetTransformTempDir(*(struct IMsiServices **)(a1 + 128), v48) )
          {
LABEL_70:
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"APPCOMPAT: Failed to determine temp directory for appcompat transforms.",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            goto LABEL_69;
          }
          v47 = v49;
        }
        if ( !ApplyTransforms(inited, v33, *(struct IMsiServices **)(a1 + 128), a4, v47) && g_dmDiagnosticMode )
        {
          v44 = L"APPCOMPAT: Failed to apply appcompat transform.";
          goto LABEL_109;
        }
      }
      else if ( g_dmDiagnosticMode )
      {
        v44 = L"APPCOMPAT: found matching ProductCode in database, but other attributes do not match.";
LABEL_109:
        DebugString(9, 0, 0, v44, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
      v33 = ((__int64 (__fastcall *)(void *, _BYTE *))APPHELP::SdbFindNextMsiPackage)(inited, v57);
      if ( !v33 )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
        goto LABEL_112;
      }
    }
  }
  if ( !v33 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: no matching ProductCode found in database.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
LABEL_74:
    if ( a7 != 2 )
      goto LABEL_112;
    v42 = (struct IMsiTable **)CComPointer<IEnumMsiRecord>::operator=(a1 + 2216);
    if ( (unsigned int)LocalMsiCreateAppCompatTable(a4, v42) )
    {
      if ( (unsigned int)LocalSdbLoadMsiFileOverrideData(inited, a4, *(struct IMsiTable **)(a1 + 2216)) )
        goto LABEL_112;
      CComPointer<IMsiDatabase>::operator=(a1 + 2216, 0);
      if ( !g_dmDiagnosticMode )
        goto LABEL_112;
      v41 = L"APPCOMPAT: Failed to add redistributable data to table.";
    }
    else
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_112;
      v41 = L"APPCOMPAT: Failed to create redistributable table.";
    }
LABEL_81:
    DebugString(9, 0, 0, v41, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    goto LABEL_112;
  }
  v49 = 0;
  do
  {
    memset_0(&String, 0, 0x1FEu);
    v34 = ((__int64 (__fastcall *)(void *, _QWORD, __int64))APPHELP::SdbFindFirstTagRef)(inited, v33, 24577);
    if ( v34 )
      ((void (__fastcall *)(void *, _QWORD, wchar_t **, __int64))APPHELP::SdbReadStringTagRef)(
        inited,
        v34,
        &String,
        255);
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...",
        (const unsigned __int16 *)&String,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( !(unsigned __int8)FIsMatchingAppCompatEntry(inited, v33, v50, a7, a1 + 2104, a1 + 2112, a1, a4) )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_62;
      v36 = L"APPCOMPAT: found matching ProductCode in database, but other attributes do not match.";
      goto LABEL_61;
    }
    LOWORD(v35) = 4125;
    if ( (unsigned int)((__int64 (__fastcall *)(void *, _QWORD, __int64))APPHELP::SdbFindFirstTagRef)(inited, v33, v35) )
      v28 = 1;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    *a8 = GetShimFlags(inited, v33);
    v56 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    if ( (unsigned int)((__int64 (__fastcall *)(void *, _QWORD, __int128 *))APPHELP::SdbGetMsiPackageInformation)(
                         inited,
                         v33,
                         &v53) )
    {
      if ( (v56 & 1) != 0
        && !(unsigned int)((__int64 (__fastcall *)(__int128 *, __int128 *, _QWORD, _QWORD))APPHELP::ApphelpCheckMsiPackage)(
                            &v55,
                            &v53,
                            0,
                            a9) )
      {
        goto LABEL_66;
      }
      if ( !*(_BYTE *)(a1 + 2024)
        && (unsigned int)((__int64 (__fastcall *)(void *, _QWORD, __int64))APPHELP::SdbFindFirstTagRef)(
                           inited,
                           v33,
                           28692) )
      {
        v37 = v55;
        *(_BYTE *)(a1 + 2024) = 1;
        v38 = v53;
        *(_OWORD *)(a1 + 2028) = v37;
        *(_OWORD *)(a1 + 2044) = v38;
      }
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v39 = v49;
    if ( !v49 )
    {
      v40 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v49);
      if ( !GetTransformTempDir(*(struct IMsiServices **)(a1 + 128), v40) )
        goto LABEL_70;
      v39 = v49;
    }
    if ( !ApplyTransforms(inited, v33, *(struct IMsiServices **)(a1 + 128), a4, v39) && g_dmDiagnosticMode )
    {
      v36 = L"APPCOMPAT: Failed to apply appcompat transform.";
LABEL_61:
      DebugString(9, 0, 0, v36, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    }
LABEL_62:
    v33 = ((__int64 (__fastcall *)(void *, _BYTE *))APPHELP::SdbFindNextMsiPackage)(inited, v57);
  }
  while ( v33 );
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v49);
  if ( !v28 )
    goto LABEL_74;
  if ( g_dmDiagnosticMode )
  {
    v41 = L"APPCOMPAT: No redistributable processing. One or more matching SDB entries contain 'Skip redistributable checks' flag.";
    goto LABEL_81;
  }
LABEL_112:
  ((void (__fastcall *)(void *))APPHELP::SdbReleaseDatabase)(inited);
  return 1;
}

```

## disassembly

```asm
0x180097d10  mov     [rsp-8+arg_8], rbx
0x180097d15  push    rbp
0x180097d16  push    rsi
0x180097d17  push    rdi
0x180097d18  push    r12
0x180097d1a  push    r13
0x180097d1c  push    r14
0x180097d1e  push    r15
0x180097d20  lea     rbp, [rsp-230h]
0x180097d28  sub     rsp, 330h
0x180097d2f  mov     rax, cs:__security_cookie
0x180097d36  xor     rax, rsp
0x180097d39  mov     [rbp+260h+var_40], rax
0x180097d40  mov     rax, [rbp+260h+arg_28]
0x180097d47  mov     rdi, rdx
0x180097d4a  mov     r12, [rbp+260h+arg_50]
0x180097d51  xor     edx, edx; Val
0x180097d53  mov     rsi, [rbp+260h+arg_20]
0x180097d5a  mov     r14, r8
0x180097d5d  mov     r13, [rbp+260h+arg_38]
0x180097d64  mov     rbx, rcx
0x180097d67  lea     rcx, [rbp+260h+var_290]; void *
0x180097d6b  mov     [rsp+360h+var_2E8], rax
0x180097d70  lea     r8d, [rdx+48h]; Size
0x180097d74  mov     [rbp+260h+var_2D8], r12
0x180097d78  mov     r15, r9
0x180097d7b  call    memset_0
0x180097d80  cmp     [rbp+260h+arg_30], 1
0x180097d87  mov     dword ptr [r13+0], 0
0x180097d8f  mov     byte ptr [r12], 0
0x180097d94  lea     r12, aNull; "(NULL)"
0x180097d9b  jnz     loc_180098161
0x180097da1  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180097da8  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180097daf  mov     rcx, r12
0x180097db2  mov     rax, [rax+10h]
0x180097db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097dbb  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180097dc2  lea     r8, [rsp+360h+var_2F0]
0x180097dc7  lea     rdx, aClientprocessi; "CLIENTPROCESSID"
0x180097dce  mov     [rbp+260h+var_2E0], r12
0x180097dd2  mov     rcx, r12
0x180097dd5  mov     [rsp+360h+var_2F0], r12
0x180097dda  mov     rax, [rax+68h]
0x180097dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097de3  xor     r12d, r12d
0x180097de6  lea     rax, [rbp+260h+var_2E0]
0x180097dea  mov     [rsp+360h+var_300], r12b
0x180097def  xor     r9d, r9d
0x180097df2  mov     [rsp+360h+var_308], r12
0x180097df7  xor     r8d, r8d
0x180097dfa  mov     qword ptr [rsp+360h+var_310], r12
0x180097dff  xor     edx, edx
0x180097e01  mov     dword ptr [rsp+360h+var_318], 1
0x180097e09  mov     rcx, r14
0x180097e0c  mov     [rsp+360h+var_320], rax
0x180097e11  mov     rax, [rsp+360h+var_2F0]
0x180097e16  mov     [rsp+360h+var_328], rax
0x180097e1b  mov     [rsp+360h+var_330], r12
0x180097e20  mov     [rsp+360h+var_338], r12
0x180097e25  mov     [rsp+360h+var_340], r12
0x180097e2a  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x180097e2f  mov     rcx, [rsp+360h+var_2F0]
0x180097e34  mov     rax, [rcx]
0x180097e37  mov     rax, [rax+10h]
0x180097e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e40  mov     [r13+0], r12d
0x180097e44  lea     r14, [rbx+810h]
0x180097e4b  xorps   xmm0, xmm0
0x180097e4e  xor     eax, eax
0x180097e50  movups  xmmword ptr [r14], xmm0
0x180097e54  mov     rcx, rsi
0x180097e57  movups  xmmword ptr [r14+10h], xmm0
0x180097e5c  movups  xmmword ptr [r14+20h], xmm0
0x180097e61  mov     [r14+30h], rax
0x180097e65  mov     dword ptr [r14], 1
0x180097e6c  mov     dword ptr [rbx+814h], 38h ; '8'
0x180097e76  mov     rax, [rsi]
0x180097e79  mov     rax, [rax+50h]
0x180097e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e82  mov     rcx, [rsp+360h+var_2E8]
0x180097e87  mov     [rbx+818h], rax
0x180097e8e  mov     rax, [rcx]
0x180097e91  mov     rax, [rax+50h]
0x180097e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e9a  mov     [rbx+828h], rdi
0x180097ea1  mov     rdi, [rbp+260h+var_2E0]
0x180097ea5  mov     [rbx+820h], rax
0x180097eac  mov     rcx, rdi
0x180097eaf  mov     rax, [rdi]
0x180097eb2  mov     rax, [rax+38h]
0x180097eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ebb  test    eax, eax
0x180097ebd  jz      short loc_180097ED0
0x180097ebf  mov     rax, [rdi]
0x180097ec2  mov     rcx, rdi
0x180097ec5  mov     rax, [rax+20h]
0x180097ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ece  jmp     short loc_180097ED3
0x180097ed0  mov     eax, r12d
0x180097ed3  mov     [rbx+830h], eax
0x180097ed9  mov     rcx, rsi
0x180097edc  mov     rax, [rsi]
0x180097edf  mov     rax, [rax+50h]
0x180097ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ee8  mov     rcx, rax; szProduct
0x180097eeb  call    MsiQueryProductStateW
0x180097ef0  dec     eax
0x180097ef2  test    eax, 0FFFFFFFBh
0x180097ef7  jz      short loc_180097F6B
0x180097ef9  mov     rax, cs:?ApphelpGetMsiProperties@APPHELP@@3P6AHPEAUtagMSIPROPERTYOVERRIDES@SHIMDBNS@@@ZEA; int (*APPHELP::ApphelpGetMsiProperties)(SHIMDBNS::tagMSIPROPERTYOVERRIDES *)
0x180097f00  mov     rcx, r14
0x180097f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f08  test    eax, eax
0x180097f0a  jz      loc_18009814B
0x180097f10  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180097f17  jz      short loc_180097F5C
0x180097f19  mov     [rsp+360h+var_308], r12; void *
0x180097f1e  lea     rax, aNull; "(NULL)"
0x180097f25  mov     [rsp+360h+var_310], r12d; unsigned int
0x180097f2a  lea     r9, aAppcompatCompa; "APPCOMPAT: Compatibility mode property "...
0x180097f31  mov     [rsp+360h+var_318], rax; unsigned __int16 *
0x180097f36  xor     edx, edx; unsigned __int16
0x180097f38  mov     [rsp+360h+var_320], rax; unsigned __int16 *
0x180097f3d  xor     r8d, r8d; int
0x180097f40  mov     [rsp+360h+var_328], rax; unsigned __int16 *
0x180097f45  mov     [rsp+360h+var_330], rax; unsigned __int16 *
0x180097f4a  mov     [rsp+360h+var_338], rax; unsigned __int16 *
0x180097f4f  lea     ecx, [rdx+9]; int
0x180097f52  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x180097f57  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180097f5c  mov     eax, [rbx+834h]
0x180097f62  mov     [r13+0], eax
0x180097f66  jmp     loc_18009814B
0x180097f6b  xor     edx, edx; Val
0x180097f6d  lea     rcx, [rbp+260h+var_230]; void *
0x180097f71  mov     r8d, 0C8h; Size
0x180097f77  call    memset_0
0x180097f7c  mov     ecx, 64h ; 'd'
0x180097f81  lea     rax, [rbp+260h+var_230]
0x180097f85  mov     [rbp+260h+String], rax
0x180097f89  mov     rax, [rsi]
0x180097f8c  mov     [rbp+260h+var_238], ecx
0x180097f8f  mov     [rbp+260h+var_234], ecx
0x180097f92  mov     rcx, rsi
0x180097f95  mov     rax, [rax+50h]
0x180097f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f9e  lea     r8, [rbp+260h+String]
0x180097fa2  mov     rcx, rax; szProduct
0x180097fa5  lea     rdx, aShimflags_1; "ShimFlags"
0x180097fac  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x180097fb1  test    eax, eax
0x180097fb3  jz      short loc_18009801B
0x180097fb5  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180097fbc  jz      short loc_180098001
0x180097fbe  mov     [rsp+360h+var_308], r12; void *
0x180097fc3  lea     rax, aNull; "(NULL)"
0x180097fca  mov     [rsp+360h+var_310], r12d; unsigned int
0x180097fcf  lea     r9, aAppcompatUnins_0; "APPCOMPAT: Uninstall Flags override fou"...
0x180097fd6  mov     [rsp+360h+var_318], rax; unsigned __int16 *
0x180097fdb  xor     edx, edx; unsigned __int16
0x180097fdd  mov     [rsp+360h+var_320], rax; unsigned __int16 *
0x180097fe2  xor     r8d, r8d; int
0x180097fe5  mov     [rsp+360h+var_328], rax; unsigned __int16 *
0x180097fea  mov     [rsp+360h+var_330], rax; unsigned __int16 *
0x180097fef  mov     [rsp+360h+var_338], rax; unsigned __int16 *
0x180097ff4  lea     ecx, [rdx+9]; int
0x180097ff7  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x180097ffc  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180098001  mov     rcx, [rbp+260h+String]; String
0x180098005  xor     edx, edx; EndPtr
0x180098007  lea     r8d, [rdx+0Ah]; Radix
0x18009800b  call    cs:__imp_wcstol
0x180098011  mov     [rbx+834h], eax
0x180098017  mov     [r13+0], eax
0x18009801b  mov     rax, [rsi]
0x18009801e  mov     rcx, rsi
0x180098021  mov     [rbp+260h+var_234], 64h ; 'd'
0x180098028  mov     rax, [rax+50h]
0x18009802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098031  lea     r8, [rbp+260h+String]
0x180098035  mov     rcx, rax; szProduct
0x180098038  lea     rdx, aShimversionnt; "ShimVersionNT"
0x18009803f  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x180098044  test    eax, eax
0x180098046  jz      loc_18009813C
0x18009804c  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180098053  lea     r14, aNull; "(NULL)"
0x18009805a  jz      short loc_180098098
0x18009805c  mov     [rsp+360h+var_308], r12; void *
0x180098061  lea     r9, aAppcompatUnins_1; "APPCOMPAT: Uninstall VersionNT override"...
0x180098068  mov     [rsp+360h+var_310], r12d; unsigned int
0x18009806d  xor     edx, edx; unsigned __int16
0x18009806f  mov     [rsp+360h+var_318], r14; unsigned __int16 *
0x180098074  xor     r8d, r8d; int
0x180098077  mov     [rsp+360h+var_320], r14; unsigned __int16 *
0x18009807c  mov     [rsp+360h+var_328], r14; unsigned __int16 *
0x180098081  mov     [rsp+360h+var_330], r14; unsigned __int16 *
0x180098086  lea     ecx, [rdx+9]; int
0x180098089  mov     [rsp+360h+var_338], r14; unsigned __int16 *
0x18009808e  mov     [rsp+360h+var_340], r14; unsigned __int16 *
0x180098093  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180098098  mov     rcx, [rbp+260h+String]; String
0x18009809c  xor     edx, edx; EndPtr
0x18009809e  lea     r8d, [rdx+0Ah]; Radix
0x1800980a2  call    cs:__imp_wcstol
0x1800980a8  mov     rcx, rsi
0x1800980ab  mov     [rbp+260h+var_234], 64h ; 'd'
0x1800980b2  mov     [rbx+838h], eax
0x1800980b8  mov     [rbx+83Ch], eax
0x1800980be  mov     rax, [rsi]
0x1800980c1  mov     rax, [rax+50h]
0x1800980c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980ca  lea     r8, [rbp+260h+String]
0x1800980ce  mov     rcx, rax; szProduct
0x1800980d1  lea     rdx, aShimservicepac_1; "ShimServicePackLevel"
0x1800980d8  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x1800980dd  test    eax, eax
0x1800980df  jz      short loc_18009813C
0x1800980e1  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1800980e8  jz      short loc_180098126
0x1800980ea  mov     [rsp+360h+var_308], r12; void *
0x1800980ef  lea     r9, aAppcompatUnins; "APPCOMPAT: Uninstall ServicePackLevel o"...
0x1800980f6  mov     [rsp+360h+var_310], r12d; unsigned int
0x1800980fb  xor     edx, edx; unsigned __int16
0x1800980fd  mov     [rsp+360h+var_318], r14; unsigned __int16 *
0x180098102  xor     r8d, r8d; int
0x180098105  mov     [rsp+360h+var_320], r14; unsigned __int16 *
0x18009810a  mov     [rsp+360h+var_328], r14; unsigned __int16 *
0x18009810f  mov     [rsp+360h+var_330], r14; unsigned __int16 *
0x180098114  lea     ecx, [rdx+9]; int
0x180098117  mov     [rsp+360h+var_338], r14; unsigned __int16 *
0x18009811c  mov     [rsp+360h+var_340], r14; unsigned __int16 *
0x180098121  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180098126  mov     rcx, [rbp+260h+String]; String
0x18009812a  xor     edx, edx; EndPtr
0x18009812c  lea     r8d, [rdx+0Ah]; Radix
0x180098130  call    cs:__imp_wcstol
0x180098136  mov     [rbx+840h], eax
0x18009813c  cmp     [rbp+260h+var_238], 64h ; 'd'
0x180098140  jle     short loc_18009814B
0x180098142  mov     rcx, [rbp+260h+String]; void *
0x180098146  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009814b  mov     rax, [rdi]
0x18009814e  mov     rcx, rdi
0x180098151  mov     rax, [rax+10h]
0x180098155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009815a  lea     r12, aNull; "(NULL)"
0x180098161  xor     r14d, r14d
0x180098164  cmp     [rbp+260h+arg_48], r14b
0x18009816b  jz      short loc_1800981A3
0x18009816d  mov     rax, [rbx]
0x180098170  mov     edx, 100h
0x180098175  mov     rcx, rbx
0x180098178  mov     rax, [rax+250h]
0x18009817f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098184  test    al, al
0x180098186  jnz     short loc_1800981A3
0x180098188  mov     [rbx+7E8h], r14b
0x18009818f  xorps   xmm0, xmm0
0x180098192  xorps   xmm1, xmm1
0x180098195  movups  xmmword ptr [rbx+7ECh], xmm0
0x18009819c  movups  xmmword ptr [rbx+7FCh], xmm1
0x1800981a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides> `wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl(void)'::`2'::impl
0x1800981aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(void)
0x1800981af  test    al, al
0x1800981b1  mov     rax, cs:?SdbInitDatabase@APPHELP@@3P6APEAXKPEBG@ZEA; void * (*APPHELP::SdbInitDatabase)(ulong,ushort const *)
0x1800981b8  jz      short loc_1800981C3
0x1800981ba  xor     edx, edx
0x1800981bc  mov     ecx, 80020000h
0x1800981c1  jmp     short loc_1800981CF
0x1800981c3  lea     rdx, aSystemrootAppp; "\\SystemRoot\\AppPatch\\msimain.sdb"
0x1800981ca  mov     ecx, 80020002h
0x1800981cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981d4  mov     rdi, rax
0x1800981d7  test    rax, rax
0x1800981da  jnz     short loc_180098228
0x1800981dc  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800981e3  jz      short loc_180098221
0x1800981e5  mov     [rsp+360h+var_308], r14; void *
0x1800981ea  lea     r9, aAppcompatUnabl_0; "APPCOMPAT: unable to initialize databas"...
0x1800981f1  mov     [rsp+360h+var_310], r14d; unsigned int
0x1800981f6  lea     ecx, [rax+9]; int
0x1800981f9  mov     [rsp+360h+var_318], r12; unsigned __int16 *
0x1800981fe  xor     edx, edx; unsigned __int16
0x180098200  mov     [rsp+360h+var_320], r12; unsigned __int16 *
0x180098205  xor     r8d, r8d; int
0x180098208  mov     [rsp+360h+var_328], r12; unsigned __int16 *
0x18009820d  mov     [rsp+360h+var_330], r12; unsigned __int16 *
0x180098212  mov     [rsp+360h+var_338], r12; unsigned __int16 *
0x180098217  mov     [rsp+360h+var_340], r12; unsigned __int16 *
0x18009821c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180098221  xor     al, al
0x180098223  jmp     loc_180098B20
0x180098228  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18009822f  jz      short loc_18009827C
0x180098231  mov     rax, [rsi]
0x180098234  mov     rcx, rsi
0x180098237  mov     rax, [rax+50h]
0x18009823b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
