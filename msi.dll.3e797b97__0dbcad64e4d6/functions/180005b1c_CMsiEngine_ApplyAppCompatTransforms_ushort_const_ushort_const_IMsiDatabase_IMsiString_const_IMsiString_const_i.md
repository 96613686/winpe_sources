# CMsiEngine::ApplyAppCompatTransforms(ushort const *,ushort const *,IMsiDatabase &,IMsiString const &,IMsiString const &,iacpAppCompatTransformApplyPoint,iacsAppCompatShimFlags &,bool,bool,bool &)

- ea: `0x180005b1c`
- end: `0x180006969`
- name: `?ApplyAppCompatTransforms@CMsiEngine@@IEAA_NPEBG0AEAVIMsiDatabase@@AEBVIMsiString@@2W4iacpAppCompatTransformApplyPoint@@AEAW4iacsAppCompatShimFlags@@_N5AEA_N@Z`
- size: `3661`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801046a0`

## callees

- `0x180003b10`
- `0x18000543c`
- `0x180005af8`
- `0x180005b1c`
- `0x180006970`
- `0x1800069f8`
- `0x18000c4bc`
- `0x180019cc0`
- `0x18002e870`
- `0x180042810`
- `0x18011b664`
- `0x18014d614`
- `0x18021e3c0`
- `0x18021eb78`
- `0x18021ecd0`
- `0x18021ed60`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!wcstol` at `0x180005e17`
- `msvcrt!wcstol` at `0x180005eb4`
- `msvcrt!wcstol` at `0x180005f48`
- `msvcrt!wcstol` at `0x180005e17`
- `msvcrt!wcstol` at `0x180005eb4`
- `msvcrt!wcstol` at `0x180005f48`

## string_xrefs

- `0x180005bd3`: `CLIENTPROCESSID`
- `0x180005fe1`: `\SystemRoot\AppPatch\msimain.sdb`
- `0x180005ee9`: `ShimServicePackLevel`
- `0x180005ddb`: `APPCOMPAT: Uninstall Flags override found.`
- `0x180005f07`: `APPCOMPAT: Uninstall ServicePackLevel override found.`
- `0x180005e73`: `APPCOMPAT: Uninstall VersionNT override found.`
- `0x180005d36`: `APPCOMPAT: Compatibility mode property overrides found.`
- `0x180006063`: `APPCOMPAT: looking for appcompat database entry with ProductCode '%s'.`
- `0x180006008`: `APPCOMPAT: unable to initialize database.`
- `0x1800061c6`: `APPCOMPAT: found matching ProductCode in database, but other attributes do not match.`
- `0x18000671a`: `APPCOMPAT: found matching ProductCode in database, but other attributes do not match.`
- `0x180006142`: `APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...`
- `0x18000669d`: `APPCOMPAT: matching ProductCode found in database.  Entry name: '%s'.  Testing other attributes...`
- `0x180006296`: `APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.`
- `0x1800067c5`: `APPCOMPAT: SdbGetMsiPackageInformation failed unexpectedly.`
- `0x18000620f`: `APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.`
- `0x18000673e`: `APPCOMPAT: matching ProductCode found in database, and other attributes match.  Applying appcompat fix.`
- `0x1800064b2`: `APPCOMPAT: Failed to determine temp directory for appcompat transforms.`
- `0x180006441`: `APPCOMPAT: ApphelpCheckMsiPackage returned FALSE.  This product will not be installed due to application compatibility concerns.`
- `0x1800064f4`: `APPCOMPAT: no matching ProductCode found in database.`
- `0x180006603`: `APPCOMPAT: no matching ProductCode found in database.`
- `0x180006395`: `APPCOMPAT: Failed to apply appcompat transform.`
- `0x1800068c4`: `APPCOMPAT: Failed to apply appcompat transform.`
- `0x180006565`: `APPCOMPAT: Failed to create redistributable table.`
- `0x18000641a`: `APPCOMPAT: No redistributable processing. One or more matching SDB entries contain 'Skip redistributable checks' flag.`
- `0x1800065a3`: `APPCOMPAT: Failed to add redistributable data to table.`

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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl'::`2'::impl);
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
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl'::`2'::impl) )
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
0x180005b1c  mov     [rsp-8+arg_8], rbx
0x180005b21  push    rbp
0x180005b22  push    rsi
0x180005b23  push    rdi
0x180005b24  push    r12
0x180005b26  push    r13
0x180005b28  push    r14
0x180005b2a  push    r15
0x180005b2c  lea     rbp, [rsp-230h]
0x180005b34  sub     rsp, 330h
0x180005b3b  mov     rax, cs:__security_cookie
0x180005b42  xor     rax, rsp
0x180005b45  mov     [rbp+260h+var_40], rax
0x180005b4c  mov     rax, [rbp+260h+arg_28]
0x180005b53  mov     rdi, rdx
0x180005b56  mov     r12, [rbp+260h+arg_50]
0x180005b5d  xor     edx, edx; Val
0x180005b5f  mov     rsi, [rbp+260h+arg_20]
0x180005b66  mov     r14, r8
0x180005b69  mov     r13, [rbp+260h+arg_38]
0x180005b70  mov     rbx, rcx
0x180005b73  lea     rcx, [rbp+260h+var_290]; void *
0x180005b77  mov     [rsp+360h+var_2E8], rax
0x180005b7c  lea     r8d, [rdx+48h]; Size
0x180005b80  mov     [rbp+260h+var_2D8], r12
0x180005b84  mov     r15, r9
0x180005b87  call    memset_0
0x180005b8c  cmp     [rbp+260h+arg_30], 1
0x180005b93  mov     dword ptr [r13+0], 0
0x180005b9b  mov     byte ptr [r12], 0
0x180005ba0  lea     r12, aNull; "(NULL)"
0x180005ba7  jnz     loc_180005F7F
0x180005bad  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180005bb4  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180005bbb  mov     rcx, r12
0x180005bbe  mov     rax, [rax+10h]
0x180005bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc7  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180005bce  lea     r8, [rsp+360h+var_2F0]
0x180005bd3  lea     rdx, aClientprocessi; "CLIENTPROCESSID"
0x180005bda  mov     [rbp+260h+var_2E0], r12
0x180005bde  mov     rcx, r12
0x180005be1  mov     [rsp+360h+var_2F0], r12
0x180005be6  mov     rax, [rax+68h]
0x180005bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bef  xor     r12d, r12d
0x180005bf2  lea     rax, [rbp+260h+var_2E0]
0x180005bf6  mov     [rsp+360h+var_300], r12b
0x180005bfb  xor     r9d, r9d
0x180005bfe  mov     [rsp+360h+var_308], r12
0x180005c03  xor     r8d, r8d
0x180005c06  mov     qword ptr [rsp+360h+var_310], r12
0x180005c0b  xor     edx, edx
0x180005c0d  mov     dword ptr [rsp+360h+var_318], 1
0x180005c15  mov     rcx, r14
0x180005c18  mov     [rsp+360h+var_320], rax
0x180005c1d  mov     rax, [rsp+360h+var_2F0]
0x180005c22  mov     [rsp+360h+var_328], rax
0x180005c27  mov     [rsp+360h+var_330], r12
0x180005c2c  mov     [rsp+360h+var_338], r12
0x180005c31  mov     [rsp+360h+var_340], r12
0x180005c36  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x180005c3b  mov     rcx, [rsp+360h+var_2F0]
0x180005c40  mov     rax, [rcx]
0x180005c43  mov     rax, [rax+10h]
0x180005c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4c  mov     [r13+0], r12d
0x180005c50  lea     r14, [rbx+810h]
0x180005c57  xorps   xmm0, xmm0
0x180005c5a  xor     eax, eax
0x180005c5c  movups  xmmword ptr [r14], xmm0
0x180005c60  mov     rcx, rsi
0x180005c63  movups  xmmword ptr [r14+10h], xmm0
0x180005c68  movups  xmmword ptr [r14+20h], xmm0
0x180005c6d  mov     [r14+30h], rax
0x180005c71  mov     dword ptr [r14], 1
0x180005c78  mov     dword ptr [rbx+814h], 38h ; '8'
0x180005c82  mov     rax, [rsi]
0x180005c85  mov     rax, [rax+50h]
0x180005c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c8e  mov     rcx, [rsp+360h+var_2E8]
0x180005c93  mov     [rbx+818h], rax
0x180005c9a  mov     rax, [rcx]
0x180005c9d  mov     rax, [rax+50h]
0x180005ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca6  mov     [rbx+828h], rdi
0x180005cad  mov     rdi, [rbp+260h+var_2E0]
0x180005cb1  mov     [rbx+820h], rax
0x180005cb8  mov     rcx, rdi
0x180005cbb  mov     rax, [rdi]
0x180005cbe  mov     rax, [rax+38h]
0x180005cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc7  test    eax, eax
0x180005cc9  jz      short loc_180005CDC
0x180005ccb  mov     rax, [rdi]
0x180005cce  mov     rcx, rdi
0x180005cd1  mov     rax, [rax+20h]
0x180005cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cda  jmp     short loc_180005CDF
0x180005cdc  mov     eax, r12d
0x180005cdf  mov     [rbx+830h], eax
0x180005ce5  mov     rcx, rsi
0x180005ce8  mov     rax, [rsi]
0x180005ceb  mov     rax, [rax+50h]
0x180005cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf4  mov     rcx, rax; szProduct
0x180005cf7  call    MsiQueryProductStateW
0x180005cfc  dec     eax
0x180005cfe  test    eax, 0FFFFFFFBh
0x180005d03  jz      short loc_180005D77
0x180005d05  mov     rax, cs:?ApphelpGetMsiProperties@APPHELP@@3P6AHPEAUtagMSIPROPERTYOVERRIDES@SHIMDBNS@@@ZEA; int (*APPHELP::ApphelpGetMsiProperties)(SHIMDBNS::tagMSIPROPERTYOVERRIDES *)
0x180005d0c  mov     rcx, r14
0x180005d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d14  test    eax, eax
0x180005d16  jz      loc_180005F69
0x180005d1c  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180005d23  jz      short loc_180005D68
0x180005d25  mov     [rsp+360h+var_308], r12; void *
0x180005d2a  lea     rax, aNull; "(NULL)"
0x180005d31  mov     [rsp+360h+var_310], r12d; unsigned int
0x180005d36  lea     r9, aAppcompatCompa; "APPCOMPAT: Compatibility mode property "...
0x180005d3d  mov     [rsp+360h+var_318], rax; unsigned __int16 *
0x180005d42  xor     edx, edx; unsigned __int16
0x180005d44  mov     [rsp+360h+var_320], rax; unsigned __int16 *
0x180005d49  xor     r8d, r8d; int
0x180005d4c  mov     [rsp+360h+var_328], rax; unsigned __int16 *
0x180005d51  mov     [rsp+360h+var_330], rax; unsigned __int16 *
0x180005d56  mov     [rsp+360h+var_338], rax; unsigned __int16 *
0x180005d5b  lea     ecx, [rdx+9]; int
0x180005d5e  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x180005d63  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180005d68  mov     eax, [rbx+834h]
0x180005d6e  mov     [r13+0], eax
0x180005d72  jmp     loc_180005F69
0x180005d77  xor     edx, edx; Val
0x180005d79  lea     rcx, [rbp+260h+var_230]; void *
0x180005d7d  mov     r8d, 0C8h; Size
0x180005d83  call    memset_0
0x180005d88  mov     ecx, 64h ; 'd'
0x180005d8d  lea     rax, [rbp+260h+var_230]
0x180005d91  mov     [rbp+260h+String], rax
0x180005d95  mov     rax, [rsi]
0x180005d98  mov     [rbp+260h+var_238], ecx
0x180005d9b  mov     [rbp+260h+var_234], ecx
0x180005d9e  mov     rcx, rsi
0x180005da1  mov     rax, [rax+50h]
0x180005da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005daa  lea     r8, [rbp+260h+String]
0x180005dae  mov     rcx, rax; szProduct
0x180005db1  lea     rdx, aShimflags_1; "ShimFlags"
0x180005db8  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x180005dbd  test    eax, eax
0x180005dbf  jz      short loc_180005E2D
0x180005dc1  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180005dc8  jz      short loc_180005E0D
0x180005dca  mov     [rsp+360h+var_308], r12; void *
0x180005dcf  lea     rax, aNull; "(NULL)"
0x180005dd6  mov     [rsp+360h+var_310], r12d; unsigned int
0x180005ddb  lea     r9, aAppcompatUnins_0; "APPCOMPAT: Uninstall Flags override fou"...
0x180005de2  mov     [rsp+360h+var_318], rax; unsigned __int16 *
0x180005de7  xor     edx, edx; unsigned __int16
0x180005de9  mov     [rsp+360h+var_320], rax; unsigned __int16 *
0x180005dee  xor     r8d, r8d; int
0x180005df1  mov     [rsp+360h+var_328], rax; unsigned __int16 *
0x180005df6  mov     [rsp+360h+var_330], rax; unsigned __int16 *
0x180005dfb  mov     [rsp+360h+var_338], rax; unsigned __int16 *
0x180005e00  lea     ecx, [rdx+9]; int
0x180005e03  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x180005e08  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180005e0d  mov     rcx, [rbp+260h+String]; String
0x180005e11  xor     edx, edx; EndPtr
0x180005e13  lea     r8d, [rdx+0Ah]; Radix
0x180005e17  call    cs:__imp_wcstol
0x180005e1e  nop     dword ptr [rax+rax+00h]
0x180005e23  mov     [rbx+834h], eax
0x180005e29  mov     [r13+0], eax
0x180005e2d  mov     rax, [rsi]
0x180005e30  mov     rcx, rsi
0x180005e33  mov     [rbp+260h+var_234], 64h ; 'd'
0x180005e3a  mov     rax, [rax+50h]
0x180005e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e43  lea     r8, [rbp+260h+String]
0x180005e47  mov     rcx, rax; szProduct
0x180005e4a  lea     rdx, aShimversionnt; "ShimVersionNT"
0x180005e51  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x180005e56  test    eax, eax
0x180005e58  jz      loc_180005F5A
0x180005e5e  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180005e65  lea     r14, aNull; "(NULL)"
0x180005e6c  jz      short loc_180005EAA
0x180005e6e  mov     [rsp+360h+var_308], r12; void *
0x180005e73  lea     r9, aAppcompatUnins_1; "APPCOMPAT: Uninstall VersionNT override"...
0x180005e7a  mov     [rsp+360h+var_310], r12d; unsigned int
0x180005e7f  xor     edx, edx; unsigned __int16
0x180005e81  mov     [rsp+360h+var_318], r14; unsigned __int16 *
0x180005e86  xor     r8d, r8d; int
0x180005e89  mov     [rsp+360h+var_320], r14; unsigned __int16 *
0x180005e8e  mov     [rsp+360h+var_328], r14; unsigned __int16 *
0x180005e93  mov     [rsp+360h+var_330], r14; unsigned __int16 *
0x180005e98  lea     ecx, [rdx+9]; int
0x180005e9b  mov     [rsp+360h+var_338], r14; unsigned __int16 *
0x180005ea0  mov     [rsp+360h+var_340], r14; unsigned __int16 *
0x180005ea5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180005eaa  mov     rcx, [rbp+260h+String]; String
0x180005eae  xor     edx, edx; EndPtr
0x180005eb0  lea     r8d, [rdx+0Ah]; Radix
0x180005eb4  call    cs:__imp_wcstol
0x180005ebb  nop     dword ptr [rax+rax+00h]
0x180005ec0  mov     rcx, rsi
0x180005ec3  mov     [rbp+260h+var_234], 64h ; 'd'
0x180005eca  mov     [rbx+838h], eax
0x180005ed0  mov     [rbx+83Ch], eax
0x180005ed6  mov     rax, [rsi]
0x180005ed9  mov     rax, [rax+50h]
0x180005edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee2  lea     r8, [rbp+260h+String]
0x180005ee6  mov     rcx, rax; szProduct
0x180005ee9  lea     rdx, aShimservicepac_1; "ShimServicePackLevel"
0x180005ef0  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x180005ef5  test    eax, eax
0x180005ef7  jz      short loc_180005F5A
0x180005ef9  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180005f00  jz      short loc_180005F3E
0x180005f02  mov     [rsp+360h+var_308], r12; void *
0x180005f07  lea     r9, aAppcompatUnins; "APPCOMPAT: Uninstall ServicePackLevel o"...
0x180005f0e  mov     [rsp+360h+var_310], r12d; unsigned int
0x180005f13  xor     edx, edx; unsigned __int16
0x180005f15  mov     [rsp+360h+var_318], r14; unsigned __int16 *
0x180005f1a  xor     r8d, r8d; int
0x180005f1d  mov     [rsp+360h+var_320], r14; unsigned __int16 *
0x180005f22  mov     [rsp+360h+var_328], r14; unsigned __int16 *
0x180005f27  mov     [rsp+360h+var_330], r14; unsigned __int16 *
0x180005f2c  lea     ecx, [rdx+9]; int
0x180005f2f  mov     [rsp+360h+var_338], r14; unsigned __int16 *
0x180005f34  mov     [rsp+360h+var_340], r14; unsigned __int16 *
0x180005f39  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180005f3e  mov     rcx, [rbp+260h+String]; String
0x180005f42  xor     edx, edx; EndPtr
0x180005f44  lea     r8d, [rdx+0Ah]; Radix
0x180005f48  call    cs:__imp_wcstol
0x180005f4f  nop     dword ptr [rax+rax+00h]
0x180005f54  mov     [rbx+840h], eax
0x180005f5a  cmp     [rbp+260h+var_238], 64h ; 'd'
0x180005f5e  jle     short loc_180005F69
0x180005f60  mov     rcx, [rbp+260h+String]; void *
0x180005f64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005f69  mov     rax, [rdi]
0x180005f6c  mov     rcx, rdi
0x180005f6f  mov     rax, [rax+10h]
0x180005f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f78  lea     r12, aNull; "(NULL)"
0x180005f7f  xor     r14d, r14d
0x180005f82  cmp     [rbp+260h+arg_48], r14b
0x180005f89  jz      short loc_180005FC1
0x180005f8b  mov     rax, [rbx]
0x180005f8e  mov     edx, 100h
0x180005f93  mov     rcx, rbx
0x180005f96  mov     rax, [rax+250h]
0x180005f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa2  test    al, al
0x180005fa4  jnz     short loc_180005FC1
0x180005fa6  mov     [rbx+7E8h], r14b
0x180005fad  xorps   xmm0, xmm0
0x180005fb0  xorps   xmm1, xmm1
0x180005fb3  movups  xmmword ptr [rbx+7ECh], xmm0
0x180005fba  movups  xmmword ptr [rbx+7FCh], xmm1
0x180005fc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides> `wil::Feature<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::GetImpl(void)'::`2'::impl
0x180005fc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiReinstallModeOverrides@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiReinstallModeOverrides>::__private_IsEnabled(void)
0x180005fcd  test    al, al
0x180005fcf  mov     rax, cs:?SdbInitDatabase@APPHELP@@3P6APEAXKPEBG@ZEA; void * (*APPHELP::SdbInitDatabase)(ulong,ushort const *)
0x180005fd6  jz      short loc_180005FE1
0x180005fd8  xor     edx, edx
0x180005fda  mov     ecx, 80020000h
0x180005fdf  jmp     short loc_180005FED
0x180005fe1  lea     rdx, aSystemrootAppp; "\\SystemRoot\\AppPatch\\msimain.sdb"
0x180005fe8  mov     ecx, 80020002h
0x180005fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff2  mov     rdi, rax
0x180005ff5  test    rax, rax
0x180005ff8  jnz     short loc_180006046
0x180005ffa  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180006001  jz      short loc_18000603F
0x180006003  mov     [rsp+360h+var_308], r14; void *
0x180006008  lea     r9, aAppcompatUnabl_0; "APPCOMPAT: unable to initialize databas"...
0x18000600f  mov     [rsp+360h+var_310], r14d; unsigned int
0x180006014  lea     ecx, [rax+9]; int
0x180006017  mov     [rsp+360h+var_318], r12; unsigned __int16 *
0x18000601c  xor     edx, edx; unsigned __int16
0x18000601e  mov     [rsp+360h+var_320], r12; unsigned __int16 *
0x180006023  xor     r8d, r8d; int
0x180006026  mov     [rsp+360h+var_328], r12; unsigned __int16 *
0x18000602b  mov     [rsp+360h+var_330], r12; unsigned __int16 *
0x180006030  mov     [rsp+360h+var_338], r12; unsigned __int16 *
0x180006035  mov     [rsp+360h+var_340], r12; unsigned __int16 *
0x18000603a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000603f  xor     al, al
0x180006041  jmp     loc_18000693E
0x180006046  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18000604d  jz      short loc_18000609A
0x18000604f  mov     rax, [rsi]
  ... truncated ...
```
