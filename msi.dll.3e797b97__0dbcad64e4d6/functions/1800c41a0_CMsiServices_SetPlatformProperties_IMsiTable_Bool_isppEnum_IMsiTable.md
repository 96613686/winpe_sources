# CMsiServices::SetPlatformProperties(IMsiTable &,Bool,isppEnum,IMsiTable *)

- ea: `0x1800c41a0`
- end: `0x1800c6156`
- name: `?SetPlatformProperties@CMsiServices@@UEAA?AW4Bool@@AEAVIMsiTable@@W42@W4isppEnum@@PEAV3@@Z`
- size: `8118`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180010ac0`
- `0x180014160`
- `0x180014e38`
- `0x180018ee0`
- `0x180019cc0`
- `0x18002e870`
- `0x180077470`
- `0x18007cf38`
- `0x18008c93c`
- `0x18009bf74`
- `0x18009ca0c`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800ae46c`
- `0x1800c41a0`
- `0x1800c615c`
- `0x1800c6420`
- `0x1800c6514`
- `0x1800c65c4`
- `0x1800c6a5c`
- `0x1800c6b30`
- `0x1800c6b80`
- `0x1800c6c2c`
- `0x1800d04fc`
- `0x1800ee66c`
- `0x180114470`
- `0x18015257c`
- `0x180152c54`
- `0x18015b74c`
- `0x180182d58`
- `0x180264f88`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800c44e0`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800c44e0`
- `ADVAPI32!GetUserNameW` at `0x1800c58e1`
- `ADVAPI32!GetUserNameW` at `0x1800c58e1`
- `ADVAPI32!RegQueryValueExW` at `0x1800c52bd`
- `ADVAPI32!RegQueryValueExW` at `0x1800c52bd`
- `ADVAPI32!RegCloseKey` at `0x1800c50ef`
- `ADVAPI32!RegCloseKey` at `0x1800c5410`
- `ADVAPI32!RegCloseKey` at `0x1800c50ef`
- `ADVAPI32!RegCloseKey` at `0x1800c5410`
- `KERNEL32!GetVersionExW` at `0x1800c45b9`
- `KERNEL32!GetVersionExW` at `0x1800c45b9`
- `KERNEL32!lstrlenW` at `0x1800c4b51`
- `KERNEL32!lstrlenW` at `0x1800c523c`
- `KERNEL32!lstrlenW` at `0x1800c4b51`
- `KERNEL32!lstrlenW` at `0x1800c523c`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800c5a81`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800c5a81`
- `KERNEL32!GetSystemDirectoryW` at `0x1800c498f`
- `KERNEL32!GetSystemDirectoryW` at `0x1800c4b3b`
- `KERNEL32!GetSystemDirectoryW` at `0x1800c498f`
- `KERNEL32!GetSystemDirectoryW` at `0x1800c4b3b`
- `KERNEL32!GetNativeSystemInfo` at `0x1800c446f`
- `KERNEL32!GetNativeSystemInfo` at `0x1800c446f`
- `KERNEL32!GetUserDefaultLangID` at `0x1800c59b0`
- `KERNEL32!GetUserDefaultLangID` at `0x1800c59b0`
- `KERNEL32!GetComputerNameW` at `0x1800c5a1e`
- `KERNEL32!GetComputerNameW` at `0x1800c5a1e`
- `KERNEL32!MulDiv` at `0x1800c5d40`
- `KERNEL32!MulDiv` at `0x1800c5d40`
- `USER32!ReleaseDC` at `0x1800c5f57`
- `USER32!ReleaseDC` at `0x1800c5f57`
- `USER32!GetSystemMetrics` at `0x1800c5ad8`
- `USER32!GetSystemMetrics` at `0x1800c5b31`
- `USER32!GetSystemMetrics` at `0x1800c5b8a`
- `USER32!GetSystemMetrics` at `0x1800c5be3`
- `USER32!GetSystemMetrics` at `0x1800c5c3c`
- `USER32!GetSystemMetrics` at `0x1800c5c95`
- `USER32!GetSystemMetrics` at `0x1800c5ad8`
- `USER32!GetSystemMetrics` at `0x1800c5b31`
- `USER32!GetSystemMetrics` at `0x1800c5b8a`
- `USER32!GetSystemMetrics` at `0x1800c5be3`
- `USER32!GetSystemMetrics` at `0x1800c5c3c`
- `USER32!GetSystemMetrics` at `0x1800c5c95`
- `USER32!GetDC` at `0x1800c5cd8`
- `USER32!GetDC` at `0x1800c5cd8`
- `GDI32!DeleteObject` at `0x1800c5e97`
- `GDI32!DeleteObject` at `0x1800c5e97`
- `GDI32!GetTextMetricsW` at `0x1800c5df8`
- `GDI32!GetTextMetricsW` at `0x1800c5df8`
- `GDI32!GetTextFaceW` at `0x1800c5de2`
- `GDI32!GetTextFaceW` at `0x1800c5de2`
- `GDI32!CreateFontIndirectW` at `0x1800c5db2`
- `GDI32!CreateFontIndirectW` at `0x1800c5db2`
- `GDI32!GetDeviceCaps` at `0x1800c5d29`
- `GDI32!GetDeviceCaps` at `0x1800c5f11`
- `GDI32!GetDeviceCaps` at `0x1800c5d29`
- `GDI32!GetDeviceCaps` at `0x1800c5f11`
- `GDI32!SelectObject` at `0x1800c5dc7`
- `GDI32!SelectObject` at `0x1800c5e83`
- `GDI32!SelectObject` at `0x1800c5dc7`
- `GDI32!SelectObject` at `0x1800c5e83`
- `ole32!CoTaskMemFree` at `0x1800c5056`
- `ole32!CoTaskMemFree` at `0x1800c5056`

## string_xrefs

- `0x1800c4e60`: `MSIINSTALLPERUSER`
- `0x1800c4d1d`: `CommonFiles64Folder`
- `0x1800c45d1`: `ServicePackLevel`
- `0x1800c4d12`: `CommonFilesFolder`
- `0x1800c461b`: `ServicePackLevelMinor`
- `0x1800c4c14`: `TempFolder`
- `0x1800c5c55`: `BorderSide`
- `0x1800c4665`: `MsiNTProductType`
- `0x1800c4ce3`: `Common Files (x86)`
- `0x1800c4ccd`: `CommonFilesDir (x86)`
- `0x1800c5972`: `UserSID`
- `0x1800c4cf2`: `CommonFilesDir`
- `0x1800c4363`: `VersionMsi`
- `0x1800c4d04`: `Common Files`
- `0x1800c563f`: `TemplateFolder`
- `0x1800c46ad`: `MsiNTSuiteBackOffice`
- `0x1800c46f3`: `MsiNTSuiteDataCenter`
- `0x1800c472d`: `MsiNTSuiteEnterprise`
- `0x1800c4767`: `MsiNTSuiteSmallBusiness`
- `0x1800c47a1`: `MsiNTSuiteSmallBusinessRestricted`
- `0x1800c47df`: `MsiNTSuitePersonal`
- `0x1800c481d`: `MsiNTSuiteWebServer`
- `0x1800c4fd2`: `SHELL32::SHGetKnownFolderPath returned error E_INVALIDARG. Falling back to ProgramFiles/ProgramFilesCommon.`
- `0x1800c53be`: `SHELL32::SHGetKnownFolderPath failed with error: %d`
- `0x1800c55d1`: `Common Templates`
- `0x1800c5891`: `MsiTrueAdminUser`
- `0x1800c5a3f`: `ComputerName`
- `0x1800c5ca8`: `MsiTabletPC`

## pseudocode

```c
__int64 __fastcall CMsiServices::SetPlatformProperties(__int64 *a1, __int64 a2, int a3, int a4, __int64 a5)
{
  unsigned int v7; // r15d
  bool v9; // r14
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  struct IMsiCursor *v13; // rdi
  WCHAR *v14; // rax
  bool v15; // sf
  __int64 v16; // rax
  void (__fastcall *v17)(void *, LPWSTR, int *); // rax
  __int64 v18; // rbx
  unsigned int v19; // ebx
  int v20; // eax
  MsiString *v21; // rax
  unsigned int v22; // ebx
  char v23; // al
  MsiString *v24; // rax
  MsiString *v25; // rax
  MsiString *v26; // rax
  MsiString *v27; // rax
  MsiString *v28; // rax
  __int16 v29; // ax
  MsiString *v30; // rax
  MsiString *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  const unsigned __int16 *v34; // rax
  __int64 v35; // rax
  __int64 (__fastcall *v36)(__int64 *, LPCWSTR, __int64); // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  LPVOID v40; // r14
  __int64 (__fastcall *v41)(LPVOID, _QWORD); // rbx
  MsiString *v42; // rax
  __int64 v43; // rax
  char v44; // bl
  __int64 v45; // rbx
  LPWSTR v46; // rbx
  MsiString *v47; // rax
  MsiString *v48; // rax
  __int64 v49; // rbx
  MsiString *v50; // rax
  _QWORD *v51; // r12
  int v52; // edx
  const struct IMsiString *v53; // rbx
  int i; // eax
  const struct IMsiString *Property; // r14
  int v56; // r15d
  const struct IMsiString *v57; // r14
  const struct IMsiString **v58; // rax
  void *UserToken; // rax
  __int64 v60; // r10
  const unsigned __int16 *v61; // r14
  MsiUIMessageContext *v62; // rcx
  bool v63; // cl
  char v64; // r14
  __int64 v65; // r14
  int v66; // ecx
  HKEY v67; // r10
  int v68; // r14d
  const wchar_t *v69; // rdx
  int v70; // r9d
  __int64 v71; // r9
  int v72; // eax
  int v73; // r14d
  struct IMsiRecord *v74; // rax
  int v75; // eax
  LPCWSTR v76; // r9
  const WCHAR *v77; // r14
  const unsigned __int16 *v78; // rax
  struct IMsiRecord *v79; // rax
  struct IMsiString *v80; // r14
  LPVOID v81; // rbx
  const struct ShellFolder near *const *v82; // r15
  int v83; // r12d
  __int64 (__fastcall *v84)(__int64 *, __int64, __int64, void **, LPBYTE); // r14
  __int64 v85; // r8
  __int64 v86; // rdx
  void *v87; // r14
  __int64 (__fastcall *v88)(__int64 *, __int64, const wchar_t *, void **, LPBYTE); // rbx
  __int64 v89; // rax
  void (__fastcall *v90)(__int64 *, void **); // r14
  MsiString *v91; // rax
  MsiString *v92; // rax
  MsiString *v93; // rax
  MsiString *v94; // rax
  __int64 v95; // r14
  MsiString *v96; // rax
  struct IMsiString *v97; // r12
  LANGID UserDefaultLangID; // ax
  unsigned int v99; // r14d
  bool v100; // cl
  __int64 v101; // r14
  MsiString *v102; // rax
  LANGID SystemDefaultLangID; // ax
  unsigned int v104; // r14d
  int SystemMetrics; // eax
  unsigned int v106; // r14d
  int v107; // eax
  unsigned int v108; // r14d
  int v109; // eax
  unsigned int v110; // r14d
  int v111; // eax
  unsigned int v112; // r14d
  int v113; // eax
  unsigned int v114; // r14d
  unsigned int v115; // r14d
  MsiString *v116; // rax
  HDC DC; // r15
  int DeviceCaps; // eax
  int v119; // eax
  HFONT v120; // r13
  HGDIOBJ v121; // r14
  const struct IMsiString *v122; // rbx
  const struct IMsiString **v123; // rax
  struct IMsiRecord *v124; // rax
  MsiString *v125; // rax
  MsiString *v126; // rax
  unsigned int v127; // ebx
  MsiString *v128; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  struct IMsiString *v131; // [rsp+68h] [rbp-98h] BYREF
  void *v132; // [rsp+70h] [rbp-90h] BYREF
  bool v133; // [rsp+78h] [rbp-88h]
  const struct IMsiString *v134; // [rsp+80h] [rbp-80h] BYREF
  int v135[2]; // [rsp+88h] [rbp-78h] BYREF
  void *v136; // [rsp+90h] [rbp-70h] BYREF
  int v137; // [rsp+98h] [rbp-68h] BYREF
  __int64 v138; // [rsp+A0h] [rbp-60h] BYREF
  void *v139; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v140; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v141; // [rsp+B8h] [rbp-48h] BYREF
  int v142; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  DWORD pcbBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v145; // [rsp+D8h] [rbp-28h] BYREF
  int v146; // [rsp+E0h] [rbp-20h]
  DWORD cbData; // [rsp+E4h] [rbp-1Ch] BYREF
  int v148; // [rsp+E8h] [rbp-18h]
  _QWORD v149[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v150; // [rsp+110h] [rbp+10h]
  const wchar_t *v151; // [rsp+118h] [rbp+18h]
  const wchar_t *v152; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v153; // [rsp+128h] [rbp+28h]
  const GUID *v154; // [rsp+130h] [rbp+30h]
  int v155; // [rsp+138h] [rbp+38h]
  _QWORD v156[4]; // [rsp+140h] [rbp+40h] BYREF
  int v157; // [rsp+160h] [rbp+60h]
  const wchar_t *v158; // [rsp+168h] [rbp+68h]
  const wchar_t *v159; // [rsp+170h] [rbp+70h]
  const unsigned __int16 *v160; // [rsp+178h] [rbp+78h]
  const GUID *v161; // [rsp+180h] [rbp+80h]
  int v162; // [rsp+188h] [rbp+88h]
  const wchar_t *v163; // [rsp+190h] [rbp+90h]
  const wchar_t *v164; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v165; // [rsp+1A0h] [rbp+A0h]
  const GUID *v166; // [rsp+1A8h] [rbp+A8h]
  int v167; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v168; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v169; // [rsp+1C0h] [rbp+C0h]
  const unsigned __int16 *v170; // [rsp+1C8h] [rbp+C8h]
  const GUID *v171; // [rsp+1D0h] [rbp+D0h]
  int v172; // [rsp+1D8h] [rbp+D8h]
  struct tagTEXTMETRICW SystemInfo; // [rsp+1E0h] [rbp+E0h] BYREF
  LOGFONTW lf; // [rsp+220h] [rbp+120h] BYREF
  LPWSTR lpBuffer; // [rsp+280h] [rbp+180h] BYREF
  UINT uSize; // [rsp+288h] [rbp+188h]
  LPCWSTR lpString; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v178; // [rsp+2A0h] [rbp+1A0h]
  int v179; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v180; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int64 v181; // [rsp+2D0h] [rbp+1D0h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v183; // [rsp+404h] [rbp+304h]
  unsigned __int16 v184; // [rsp+406h] [rbp+306h]
  __int16 v185; // [rsp+408h] [rbp+308h]
  unsigned __int8 v186; // [rsp+40Ah] [rbp+30Ah]
  WCHAR Name[48]; // [rsp+410h] [rbp+310h] BYREF

  LODWORD(v132) = a4;
  v146 = a3;
  v135[0] = 0;
  v7 = 0;
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      v9 = 0;
    }
    else
    {
      if ( (unsigned int)(a4 - 2) >= 2 )
        return 0;
      v9 = 1;
    }
  }
  else
  {
    v9 = g_fWinNT64;
  }
  v138 = 0;
  v10 = 0;
  if ( a5 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a5 + 128LL))(a5, 0);
    CComPointer<IMsiDatabase>::operator=(&v138, v11);
    v10 = v138;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 128LL))(a2, 0);
  v140 = v12;
  v13 = (struct IMsiCursor *)v12;
  if ( !v12 )
    goto LABEL_11;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 48LL))(v12, 1);
  uSize = 261;
  v14 = (WCHAR *)operator new(0x20Au);
  lpBuffer = v14;
  if ( !v14 )
  {
    uSize = 0;
    goto LABEL_14;
  }
  v139 = &MsiString::s_NullString;
  v15 = (int)StringCchPrintfW(v14, (int)uSize, L"%d.%02d", 5, 0) < 0;
  v16 = MsiString::s_NullString;
  if ( v15 )
    goto LABEL_16;
  v17 = *(void (__fastcall **)(void *, LPWSTR, int *))(MsiString::s_NullString + 96LL);
  *(_QWORD *)v135 = &MsiString::s_NullString;
  v17(&MsiString::s_NullString, lpBuffer, v135);
  v18 = *(_QWORD *)v135;
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"VersionMsi",
    &pv);
  LODWORD(v18) = SetProperty(v13, pv, v18);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v135 + 16LL))(*(_QWORD *)v135);
  if ( !(_DWORD)v18 )
    goto LABEL_19;
  v178 = 261;
  lpString = (LPCWSTR)operator new(0x20Au);
  if ( !lpString )
  {
    v178 = 0;
    goto LABEL_22;
  }
  pv = &MsiString::s_NullString;
  v19 = g_iMinorVersion + 100 * g_iMajorVersion;
  (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"VersionNT",
    &pv);
  SetPropertyInt(v13, pv, v19);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  memset(&SystemInfo, 0, 48);
  GetNativeSystemInfo((LPSYSTEM_INFO)&SystemInfo);
  if ( LOWORD(SystemInfo.tmHeight) == 12 )
  {
    pv = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"VersionNT64",
      &pv);
    SetPropertyInt(v13, pv, v19);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  }
  else if ( v9 )
  {
    v137 = 0;
    if ( !(unsigned int)RtlGetCurrentServiceSessionId()
      || (v15 = (int)RtlpQueryContainersCompatMode(&v137) < 0, v20 = v137, v15) )
    {
      v20 = 0;
    }
    if ( !v20 )
    {
      v21 = MsiString::MsiString((MsiString *)&v131, L"VersionNT64");
      SetPropertyInt(v13, *(_QWORD *)v21, v19);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    }
  }
  v22 = g_iWindowsBuild;
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"WindowsBuild",
    &pv);
  SetPropertyInt(v13, pv, v22);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  hKey = 0;
  cbData = 4;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  GetVersionExW(&VersionInformation);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ServicePackLevel",
    &pv);
  SetPropertyInt(v13, pv, v183);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ServicePackLevelMinor",
    &pv);
  SetPropertyInt(v13, pv, v184);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"MsiNTProductType",
    &pv);
  SetPropertyInt(v13, pv, v186);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  v23 = v185;
  if ( (v185 & 4) != 0 )
  {
    v24 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteBackOffice");
    SetPropertyInt(v13, *(_QWORD *)v24, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v23 = v185;
  }
  if ( v23 < 0 )
  {
    v25 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteDataCenter");
    SetPropertyInt(v13, *(_QWORD *)v25, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v23 = v185;
  }
  if ( (v23 & 2) != 0 )
  {
    v26 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteEnterprise");
    SetPropertyInt(v13, *(_QWORD *)v26, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v23 = v185;
  }
  if ( (v23 & 1) != 0 )
  {
    v27 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteSmallBusiness");
    SetPropertyInt(v13, *(_QWORD *)v27, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v23 = v185;
  }
  if ( (v23 & 0x20) != 0 )
  {
    v28 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteSmallBusinessRestricted");
    SetPropertyInt(v13, *(_QWORD *)v28, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  v29 = v185;
  if ( (v185 & 0x200) != 0 )
  {
    v30 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuitePersonal");
    SetPropertyInt(v13, *(_QWORD *)v30, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v29 = v185;
  }
  if ( (v29 & 0x400) != 0 )
  {
    v31 = MsiString::MsiString((MsiString *)&v131, L"MsiNTSuiteWebServer");
    SetPropertyInt(v13, *(_QWORD *)v31, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  if ( !MsiGetWindowsDirectory((unsigned __int16 *)lpString, v178) )
  {
LABEL_46:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    goto LABEL_17;
  }
  SetDirectoryProperty(v13, L"WindowsFolder", lpString, v178);
  (*(void (__fastcall **)(void *, LPCWSTR, void **))(*(_QWORD *)v139 + 96LL))(v139, lpString, &v139);
  v32 = *a1;
  v145 = 0;
  v141 = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR, __int64 *))(v32 + 128))(a1, lpString, &v145);
  if ( v145 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v145 + 168LL))(v145);
    v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 80LL))(v33);
    if ( (int)StringCchCopyW(lpBuffer, (int)uSize, v34) < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_50:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v141);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v145);
      goto LABEL_46;
    }
    SetDirectoryProperty(v13, L"WindowsVolume", lpBuffer, uSize);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  GetSystemDirectoryW(lpBuffer, uSize);
  if ( g_fWinNT64 )
  {
    SetDirectoryProperty(v13, L"System64Folder", lpBuffer, uSize);
    if ( (int)StringCchCopyW((unsigned __int16 *)lpString, (int)v178, lpBuffer) < 0 )
      goto LABEL_50;
    v35 = *a1;
    pv = 0;
    v36 = *(__int64 (__fastcall **)(__int64 *, LPCWSTR, __int64))(v35 + 120);
    v37 = CComPointer<IEnumMsiRecord>::operator=(&pv);
    v38 = v36(a1, lpString, v37);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v141, v38)
      || (v39 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 112LL))(pv),
          *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v141, v39))
      || (v40 = pv,
          v41 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)pv + 104LL),
          v42 = MsiString::MsiString((MsiString *)&v131, L"SysWOW64"),
          v7 = 1,
          v43 = v41(v40, *(_QWORD *)v42),
          v44 = 1,
          *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v141, v43)) )
    {
      v44 = 0;
    }
    if ( (v7 & 1) != 0 )
    {
      v7 &= ~1u;
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    }
    if ( v44 )
    {
      v45 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 56LL))(pv);
      (*(void (__fastcall **)(__int64, LPWSTR, _QWORD))(*(_QWORD *)v45 + 88LL))(v45, lpBuffer, uSize - 1);
      SetDirectoryProperty(v13, L"SystemFolder", lpBuffer, uSize);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&pv);
  }
  else
  {
    SetDirectoryProperty(v13, L"SystemFolder", lpBuffer, uSize);
  }
  if ( !g_fWinNT64 )
  {
    GetSystemDirectoryW(lpBuffer, uSize);
    v46 = lpBuffer;
    v46[lstrlenW(lpBuffer) - 2] = 0;
    SetDirectoryProperty(v13, L"System16Folder", lpBuffer, uSize);
  }
  if ( (unsigned int)IsTerminalServerSKU() )
  {
    v47 = MsiString::MsiString((MsiString *)&v131, L"TerminalServer");
    SetPropertyInt(v13, *(_QWORD *)v47, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  if ( IsRemoteAdminTSInstalled() )
  {
    v48 = MsiString::MsiString((MsiString *)&v131, L"RemoteAdminTS");
    SetPropertyInt(v13, *(_QWORD *)v48, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  MsiGetTempPath(uSize, lpBuffer);
  SetDirectoryProperty(v13, L"TempFolder", lpBuffer, uSize);
  if ( g_fShortFileNames )
  {
    v49 = *(_QWORD *)MsiString::MsiString((MsiString *)&pv, L"1");
    v50 = MsiString::MsiString((MsiString *)&v131, L"SHORTFILENAMES");
    SetProperty(v13, *(_QWORD *)v50, v49);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  }
  v149[3] = &FOLDERID_UserProgramFiles;
  v150 = 0;
  v156[0] = L"ProgramFilesDir (x86)";
  v149[0] = L"ProgramFilesDir";
  v156[1] = L"Program Files (x86)";
  v149[1] = L"Program Files";
  v158 = L"CommonFilesDir (x86)";
  v149[2] = L"ProgramFilesFolder";
  v159 = L"Common Files (x86)";
  v151 = L"CommonFilesDir";
  v165 = L"ProgramFiles64Folder";
  v152 = L"Common Files";
  v153 = L"CommonFilesFolder";
  v170 = L"CommonFiles64Folder";
  v154 = &FOLDERID_UserProgramFilesCommon;
  v155 = 0;
  v156[2] = L"ProgramFilesFolder";
  v156[3] = &FOLDERID_UserProgramFiles;
  v157 = 0;
  v160 = L"CommonFilesFolder";
  v161 = &FOLDERID_UserProgramFilesCommon;
  v162 = 0;
  v163 = L"ProgramFilesDir";
  v164 = L"Program Files";
  v166 = &FOLDERID_UserProgramFiles;
  v167 = 1;
  v168 = L"CommonFilesDir";
  v169 = L"Common Files";
  v171 = &FOLDERID_UserProgramFilesCommon;
  v172 = 1;
  if ( g_fWinNT64 )
  {
    v51 = v156;
    v52 = 4;
  }
  else
  {
    v51 = v149;
    v52 = 2;
  }
  v148 = v52;
  if ( hKey )
    hKey = 0;
  v53 = v134;
  *lpString = 0;
  v137 = *((_DWORD *)v51 + 8);
  for ( i = 0; ; i = v142 + 1 )
  {
    v142 = i;
    if ( i >= v52 )
      break;
    pv = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"ALLUSERS",
      &pv);
    Property = GetProperty(v13, (const struct IMsiString *)pv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    v135[0] = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)Property + 32LL))(Property);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)Property + 16LL))(Property);
    pv = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"MSIINSTALLPERUSER",
      &pv);
    v56 = v7 | 6;
    v57 = GetProperty(v13, (const struct IMsiString *)pv);
    v133 = (*(unsigned int (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 56LL))(v57)
        && ((v58 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v134, L"ALLUSERS"),
             v56 |= 0x18u,
             v53 = GetProperty(v13, *v58),
             !(*(unsigned int (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v53 + 56LL))(v53))
         || v135[0] == 2);
    if ( (v56 & 0x10) != 0 )
    {
      v56 &= ~0x10u;
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v53 + 16LL))(v53);
    }
    if ( (v56 & 8) != 0 )
    {
      v56 &= ~8u;
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    }
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 16LL))(v57);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( !v133 )
      goto LABEL_99;
    pv = 0;
    StartImpersonating();
    ++HIDWORD(qword_1803136AC);
    v131 = (struct IMsiString *)(5LL * v142);
    UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    v61 = (const unsigned __int16 *)(int)((__int64 (__fastcall *)(_QWORD, __int64, void *, LPVOID *))SHELL32::SHGetKnownFolderPath)(
                                           v51[v60 + 3],
                                           0x8000,
                                           UserToken,
                                           &pv);
    MsiUIMessageContext::EnableTimeout(v62);
    StopImpersonating(v63);
    if ( (_DWORD)v61 )
    {
      if ( (_DWORD)v61 != -2147024809 && (_DWORD)v61 != -2147024894 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SHELL32::SHGetKnownFolderPath failed with error: %d",
            v61,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_132:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v141);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v145);
LABEL_22:
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
LABEL_19:
        v16 = MsiString::s_NullString;
LABEL_16:
        (*(void (__fastcall **)(void *))(v16 + 16))(&MsiString::s_NullString);
LABEL_17:
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v139 + 16LL))(v139);
LABEL_14:
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
LABEL_11:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v140);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v138);
        return 0;
      }
      v64 = 0;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"SHELL32::SHGetKnownFolderPath returned error E_INVALIDARG. Falling back to ProgramFiles/ProgramFilesCommon.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
    }
    else
    {
      if ( (int)StringCchCopyW(lpBuffer, (int)uSize, (const unsigned __int16 *)pv) < 0 )
        goto LABEL_132;
      v64 = 1;
      SetDirectoryProperty(v13, v51[(_QWORD)v131 + 2], lpBuffer, uSize);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v64 )
    {
LABEL_99:
      v65 = v142;
      wcscpy(Name, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion");
      pv = &MsiString::s_NullString;
      v66 = v51[5 * v142 + 4];
      v131 = (struct IMsiString *)(5LL * v142);
      if ( v137 != v66 )
      {
        v137 = v66;
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
      }
      *lpBuffer = 0;
      v67 = hKey;
      if ( !hKey )
      {
        MsiString::operator=(&pv, L"HKEY_LOCAL_MACHINE");
        v68 = v137;
        if ( g_fWinNT64 )
        {
          v69 = L"64";
          if ( v137 != 1 )
            v69 = L"32";
          MsiString::operator+=(&pv, v69);
        }
        MsiString::operator+=(&pv, L"\\");
        MsiString::operator+=(&pv, Name);
        if ( g_fWinNT64 )
        {
          v70 = 256;
          if ( v68 != 1 )
            v70 = 512;
          v71 = v70 | 0x20019u;
        }
        else
        {
          v71 = 131097;
        }
        v72 = ((__int64 (__fastcall *)(__int64, WCHAR *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                -2147483646,
                Name,
                0,
                v71,
                &hKey);
        v73 = v72;
        if ( v72 )
        {
          v74 = PostError(1402, (const struct IMsiString *)pv, v72);
          CComPointer<IMsiDatabase>::operator=(&v141, v74);
        }
        v67 = hKey;
        if ( !hKey )
        {
          if ( !v73 )
            goto LABEL_116;
LABEL_117:
          if ( !*lpString )
          {
            MsiGetWindowsDirectory((unsigned __int16 *)lpString, v178);
            v75 = lstrlenW(lpString);
            v76 = lpString;
            if ( lpString[v75 - 1] != 92 )
            {
              lpString[v75] = 92;
              if ( v75 >= (int)(v178 - 1) )
                v76[v75] = 0;
              else
                v76[v75 + 1] = 0;
            }
          }
          v80 = v131;
          lpData = (LPBYTE)v51[(_QWORD)v131 + 1];
          if ( (int)StringCchPrintfW(lpBuffer, (int)uSize, L"%s%s") < 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            goto LABEL_132;
          }
          goto LABEL_128;
        }
        v65 = v142;
      }
      cbData = 2 * uSize;
      v77 = (const WCHAR *)v51[5 * v65];
      v135[0] = RegQueryValueExW(v67, v77, 0, 0, (LPBYTE)lpBuffer, &cbData);
      if ( v135[0] )
      {
        v78 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 80LL))(pv);
        v79 = PostError(1405, v77, v78, v135[0]);
        CComPointer<IMsiDatabase>::operator=(&v141, v79);
        goto LABEL_117;
      }
LABEL_116:
      if ( !*lpBuffer )
        goto LABEL_117;
      v80 = v131;
LABEL_128:
      SetDirectoryProperty(v13, v51[(_QWORD)v80 + 2], lpBuffer, uSize);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    v7 = v56 & 0xFFFFFFF9;
    v52 = v148;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v81 = 0;
  v136 = &MsiString::s_NullString;
  v82 = 0;
  pv = 0;
  v83 = 0;
  while ( 2 )
  {
    switch ( v83 )
    {
      case 0:
        v82 = &rgShellFolders;
        goto LABEL_148;
      case 1:
        v82 = &rgAllUsersProfileShellFolders;
        if ( !v146 )
          v82 = &rgPersonalProfileShellFolders;
LABEL_147:
        if ( *(int *)v82 >= 0 )
          goto LABEL_148;
        break;
      case 2:
        if ( v10 )
        {
          if ( !v146 )
          {
            v82 = &rgAllUsersProfileShellFolders;
            goto LABEL_147;
          }
          v82 = &rgPersonalProfileShellFolders;
          do
          {
LABEL_148:
            v84 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, void **, LPBYTE))(*a1 + 344);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v136 + 16LL))(v136);
            v85 = *((_QWORD *)v82 + 2);
            v86 = *(unsigned int *)v82;
            v136 = &MsiString::s_NullString;
            LOBYTE(lpData) = 1;
            v87 = (void *)v84(a1, v86, v85, &v136, lpData);
            if ( v81 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v81 + 16LL))(v81);
            v81 = v87;
            if ( !v87 && (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v136 + 56LL))(v136) )
            {
              (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v136 + 88LL))(v136, lpBuffer, uSize - 1);
              if ( v83 != 2 )
                SetDirectoryProperty(v13, *((_QWORD *)v82 + 1), lpBuffer, uSize);
              if ( v10 )
                CacheFolderProperty(v10, *(unsigned int *)v82, lpBuffer, uSize);
            }
            v82 += 4;
          }
          while ( *(int *)v82 >= 0 );
          pv = v87;
        }
        break;
      default:
        goto LABEL_147;
    }
    if ( ++v83 < 3 )
      continue;
    break;
  }
  if ( v146 )
  {
    v88 = *(__int64 (__fastcall **)(__int64 *, __int64, const wchar_t *, void **, LPBYTE))(*a1 + 344);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v136 + 16LL))(v136);
    v136 = &MsiString::s_NullString;
    LOBYTE(lpData) = 0;
    v89 = v88(a1, 45, L"Common Templates", &v136, lpData);
    CComPointer<IMsiDatabase>::operator=(&pv, v89);
    v81 = pv;
    if ( !pv )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v136 + 56LL))(v136) )
      {
        (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v136 + 88LL))(v136, lpBuffer, uSize - 1);
        SetDirectoryProperty(v13, L"TemplateFolder", lpBuffer, uSize);
      }
    }
  }
  v90 = *(void (__fastcall **)(__int64 *, void **))(*a1 + 384);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v136 + 16LL))(v136);
  v136 = &MsiString::s_NullString;
  v90(a1, &v136);
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v136 + 56LL))(v136) )
  {
    (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v136 + 88LL))(v136, lpBuffer, uSize - 1);
    SetDirectoryProperty(v13, L"FontsFolder", lpBuffer, uSize);
  }
  *(_QWORD *)v135 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"GPTSupport",
    v135);
  SetPropertyInt(v13, *(_QWORD *)v135, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v135 + 16LL))(*(_QWORD *)v135);
  *(_QWORD *)v135 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"OLEAdvtSupport",
    v135);
  SetPropertyInt(v13, *(_QWORD *)v135, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v135 + 16LL))(*(_QWORD *)v135);
  *(_QWORD *)v135 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ShellAdvtSupport",
    v135);
  SetPropertyInt(v13, *(_QWORD *)v135, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v135 + 16LL))(*(_QWORD *)v135);
  SetProcessorProperty(v13, (unsigned int)v132);
  memset_0(&v179, 0, 0x40u);
  v179 = 64;
  if ( (unsigned int)((__int64 (__fastcall *)(int *))KERNEL32::GlobalMemoryStatusEx)(&v179) )
  {
    v91 = MsiString::MsiString((MsiString *)&v134, L"PhysicalMemory");
    SetPropertyInt(v13, *(_QWORD *)v91, (unsigned __int64)(v180 + 650000) >> 20);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    v92 = MsiString::MsiString((MsiString *)&v134, L"VirtualMemory");
    SetPropertyInt(v13, *(_QWORD *)v92, v181 >> 20);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
  }
  if ( IsAdmin() )
  {
    v93 = MsiString::MsiString((MsiString *)&v134, L"AdminUser");
    SetPropertyInt(v13, *(_QWORD *)v93, 1);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    v94 = MsiString::MsiString((MsiString *)&v134, L"MsiTrueAdminUser");
    SetPropertyInt(v13, *(_QWORD *)v94, 1);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
  }
  pcbBuffer = uSize;
  StartImpersonating();
  pcbBuffer = uSize;
  if ( GetUserNameW(lpBuffer, &pcbBuffer) )
  {
    v95 = *(_QWORD *)MsiString::MsiString((MsiString *)&v131, lpBuffer);
    v96 = MsiString::MsiString((MsiString *)&v134, L"LogonUser");
    SetProperty(v13, *(_QWORD *)v96, v95);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v131 = (struct IMsiString *)&MsiString::s_NullString;
  GetCurrentUserStringSID(&v131);
  v132 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"UserSID",
    &v132);
  v97 = v131;
  SetProperty(v13, v132, v131);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  UserDefaultLangID = GetUserDefaultLangID();
  v132 = &MsiString::s_NullString;
  v99 = UserDefaultLangID;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"UserLanguageID",
    &v132);
  SetPropertyInt(v13, v132, v99);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  StopImpersonating(v100);
  pcbBuffer = uSize;
  if ( GetComputerNameW(lpBuffer, &pcbBuffer) )
  {
    v101 = *(_QWORD *)MsiString::MsiString((MsiString *)&v131, lpBuffer);
    v102 = MsiString::MsiString((MsiString *)&v134, L"ComputerName");
    SetProperty(v13, *(_QWORD *)v102, v101);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
  }
  SystemDefaultLangID = GetSystemDefaultLangID();
  v132 = &MsiString::s_NullString;
  v104 = SystemDefaultLangID;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"SystemLanguageID",
    &v132);
  SetPropertyInt(v13, v132, v104);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  SystemMetrics = GetSystemMetrics(0);
  v132 = &MsiString::s_NullString;
  v106 = SystemMetrics;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ScreenX",
    &v132);
  SetPropertyInt(v13, v132, v106);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  v107 = GetSystemMetrics(1);
  v132 = &MsiString::s_NullString;
  v108 = v107;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ScreenY",
    &v132);
  SetPropertyInt(v13, v132, v108);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  v109 = GetSystemMetrics(4);
  v132 = &MsiString::s_NullString;
  v110 = v109;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"CaptionHeight",
    &v132);
  SetPropertyInt(v13, v132, v110);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  v111 = GetSystemMetrics(5);
  v132 = &MsiString::s_NullString;
  v112 = v111;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"BorderTop",
    &v132);
  SetPropertyInt(v13, v132, v112);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  v113 = GetSystemMetrics(6);
  v132 = &MsiString::s_NullString;
  v114 = v113;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"BorderSide",
    &v132);
  SetPropertyInt(v13, v132, v114);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v132 + 16LL))(v132);
  v115 = GetSystemMetrics(86);
  if ( v115 )
  {
    v116 = MsiString::MsiString((MsiString *)&v134, L"MsiTabletPC");
    SetPropertyInt(v13, *(_QWORD *)v116, v115);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
  }
  DC = GetDC(0);
  if ( DC )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    memset_0(&lf, 0, sizeof(lf));
    DeviceCaps = GetDeviceCaps(DC, 90);
    v119 = MulDiv(10, DeviceCaps, 72);
    lf.lfWeight = 400;
    lf.lfHeight = -v119;
    if ( (int)StringCchCopyW(lf.lfFaceName, 0x20u, L"MS Sans Serif") < 0 )
    {
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v97 + 16LL))(v97);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v136 + 16LL))(v136);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&pv);
      goto LABEL_132;
    }
    v120 = CreateFontIndirectW(&lf);
    v121 = SelectObject(DC, v120);
    GetTextFaceW(DC, 32, Name);
    GetTextMetricsW(DC, &SystemInfo);
    v122 = *(const struct IMsiString **)MsiString::MsiString((MsiString *)&v131, Name);
    v123 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v134, L"MS Sans Serif");
    v124 = PostError(2898, *v123, v122, lf.lfCharSet, SystemInfo.tmHeight, 1);
    CComPointer<IMsiDatabase>::operator=(&pv, v124);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    SelectObject(DC, v121);
    if ( v120 )
      DeleteObject(v120);
    v125 = MsiString::MsiString((MsiString *)&v134, L"TextHeight");
    SetPropertyInt(v13, *(_QWORD *)v125, (unsigned int)SystemInfo.tmHeight);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    v126 = MsiString::MsiString((MsiString *)&v131, L"TextInternalLeading");
    SetPropertyInt(v13, *(_QWORD *)v126, (unsigned int)SystemInfo.tmInternalLeading);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v131 + 16LL))(v131);
    v127 = GetDeviceCaps(DC, 12);
    v128 = MsiString::MsiString((MsiString *)&v134, L"ColorBits");
    SetPropertyInt(v13, *(_QWORD *)v128, v127);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v134 + 16LL))(v134);
    v81 = pv;
  }
  ReleaseDC(0, DC);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"TTCSupport",
    &pv);
  SetPropertyInt(v13, pv, 1);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"Time",
    &pv);
  SetProperty(v13, pv, &g_MsiStringTime);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"Date",
    &pv);
  SetProperty(v13, pv, &g_MsiStringDate);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v97 + 16LL))(v97);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v136 + 16LL))(v136);
  if ( v81 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v81 + 16LL))(v81);
  if ( v141 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
  if ( v145 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v145 + 16LL))(v145);
  if ( (int)v178 > 1 )
    operator delete((void *)lpString);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v139 + 16LL))(v139);
  if ( (int)uSize > 1 )
    operator delete(lpBuffer);
  (*(void (__fastcall **)(struct IMsiCursor *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return 1;
}

```

## disassembly

```asm
0x1800c41a0  mov     [rsp-8+arg_10], rbx
0x1800c41a5  push    rbp
0x1800c41a6  push    rsi
0x1800c41a7  push    rdi
0x1800c41a8  push    r12
0x1800c41aa  push    r13
0x1800c41ac  push    r14
0x1800c41ae  push    r15
0x1800c41b0  lea     rbp, [rsp-380h]
0x1800c41b8  sub     rsp, 480h
0x1800c41bf  mov     rax, cs:__security_cookie
0x1800c41c6  xor     rax, rsp
0x1800c41c9  mov     [rbp+3B0h+var_40], rax
0x1800c41d0  mov     r10, [rbp+3B0h+arg_20]
0x1800c41d7  xor     r12d, r12d
0x1800c41da  mov     dword ptr [rsp+4B0h+var_440], r9d
0x1800c41df  mov     r13, rcx
0x1800c41e2  mov     [rbp+3B0h+var_3D0], r8d
0x1800c41e6  mov     rbx, rdx
0x1800c41e9  mov     [rbp+3B0h+var_428], r12d
0x1800c41ed  mov     r15d, r12d
0x1800c41f0  mov     ecx, r9d
0x1800c41f3  test    r9d, r9d
0x1800c41f6  jz      short loc_1800C4218
0x1800c41f8  sub     ecx, 1
0x1800c41fb  jz      short loc_1800C4213
0x1800c41fd  sub     ecx, 1
0x1800c4200  jz      short loc_1800C420E
0x1800c4202  cmp     ecx, 1
0x1800c4205  jz      short loc_1800C420E
0x1800c4207  xor     eax, eax
0x1800c4209  jmp     loc_1800C612B
0x1800c420e  mov     r14b, 1
0x1800c4211  jmp     short loc_1800C421F
0x1800c4213  mov     r14b, r12b
0x1800c4216  jmp     short loc_1800C421F
0x1800c4218  mov     r14b, cs:?g_fWinNT64@@3_NA; bool g_fWinNT64
0x1800c421f  mov     [rbp+3B0h+var_410], r12
0x1800c4223  mov     rsi, r12
0x1800c4226  test    r10, r10
0x1800c4229  jz      short loc_1800C424F
0x1800c422b  mov     rax, [r10]
0x1800c422e  xor     edx, edx
0x1800c4230  mov     rcx, r10
0x1800c4233  mov     rax, [rax+80h]
0x1800c423a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c423f  mov     rdx, rax
0x1800c4242  lea     rcx, [rbp+3B0h+var_410]
0x1800c4246  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800c424b  mov     rsi, [rbp+3B0h+var_410]
0x1800c424f  mov     rax, [rbx]
0x1800c4252  xor     edx, edx
0x1800c4254  mov     rcx, rbx
0x1800c4257  mov     rax, [rax+80h]
0x1800c425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4263  mov     [rbp+3B0h+var_400], rax
0x1800c4267  mov     rdi, rax
0x1800c426a  test    rax, rax
0x1800c426d  jnz     short loc_1800C4283
0x1800c426f  lea     rcx, [rbp+3B0h+var_400]
0x1800c4273  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800c4278  lea     rcx, [rbp+3B0h+var_410]
0x1800c427c  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800c4281  jmp     short loc_1800C4207
0x1800c4283  mov     rax, [rax]
0x1800c4286  mov     edx, 1
0x1800c428b  mov     rcx, rdi
0x1800c428e  mov     rax, [rax+30h]
0x1800c4292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4297  mov     ecx, 20Ah; unsigned __int64
0x1800c429c  mov     [rbp+3B0h+uSize], 105h
0x1800c42a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c42ab  mov     [rbp+3B0h+lpBuffer], rax
0x1800c42b2  test    rax, rax
0x1800c42b5  jnz     short loc_1800C42CC
0x1800c42b7  mov     [rbp+3B0h+uSize], r12d
0x1800c42be  lea     rcx, [rbp+3B0h+lpBuffer]
0x1800c42c5  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1800c42ca  jmp     short loc_1800C426F
0x1800c42cc  movsxd  rdx, [rbp+3B0h+uSize]; unsigned __int64
0x1800c42d3  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c42da  mov     r9d, 5
0x1800c42e0  mov     [rbp+3B0h+var_408], rbx
0x1800c42e4  lea     r8, aD02d; "%d.%02d"
0x1800c42eb  mov     [rsp+4B0h+lpData], r12
0x1800c42f0  mov     rcx, rax; unsigned __int16 *
0x1800c42f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c42f8  test    eax, eax
0x1800c42fa  mov     rcx, rbx
0x1800c42fd  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4304  jns     short loc_1800C4334
0x1800c4306  mov     rax, [rax+10h]
0x1800c430a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c430f  mov     rcx, rbx
0x1800c4312  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4319  mov     rax, [rax+10h]
0x1800c431d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4322  mov     rcx, [rbp+3B0h+var_408]
0x1800c4326  mov     rax, [rcx]
0x1800c4329  mov     rax, [rax+10h]
0x1800c432d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4332  jmp     short loc_1800C42BE
0x1800c4334  mov     rdx, [rbp+3B0h+lpBuffer]
0x1800c433b  lea     r8, [rbp+3B0h+var_428]
0x1800c433f  mov     rax, [rax+60h]
0x1800c4343  mov     qword ptr [rbp+3B0h+var_428], rbx
0x1800c4347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c434c  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4353  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c435a  mov     rbx, qword ptr [rbp+3B0h+var_428]
0x1800c435e  lea     r8, [rsp+4B0h+pv]
0x1800c4363  lea     rdx, aVersionmsi; "VersionMsi"
0x1800c436a  mov     [rsp+4B0h+pv], rcx
0x1800c436f  mov     rax, [rax+68h]
0x1800c4373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4378  mov     rdx, [rsp+4B0h+pv]
0x1800c437d  mov     r8, rbx
0x1800c4380  mov     rcx, rdi
0x1800c4383  call    SetProperty
0x1800c4388  mov     rcx, [rsp+4B0h+pv]
0x1800c438d  mov     ebx, eax
0x1800c438f  mov     rax, [rcx]
0x1800c4392  mov     rax, [rax+10h]
0x1800c4396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c439b  mov     rcx, qword ptr [rbp+3B0h+var_428]
0x1800c439f  mov     rax, [rcx]
0x1800c43a2  mov     rax, [rax+10h]
0x1800c43a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c43ab  test    ebx, ebx
0x1800c43ad  jnz     short loc_1800C43C5
0x1800c43af  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c43b6  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c43bd  mov     rcx, rbx
0x1800c43c0  jmp     loc_1800C4306
0x1800c43c5  mov     ecx, 20Ah; unsigned __int64
0x1800c43ca  mov     [rbp+3B0h+var_210], 105h
0x1800c43d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c43d9  mov     [rbp+3B0h+lpString], rax
0x1800c43e0  test    rax, rax
0x1800c43e3  jnz     short loc_1800C43FA
0x1800c43e5  mov     [rbp+3B0h+var_210], r12d
0x1800c43ec  lea     rcx, [rbp+3B0h+lpString]
0x1800c43f3  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1800c43f8  jmp     short loc_1800C43AF
0x1800c43fa  imul    ebx, cs:?g_iMajorVersion@@3HA, 64h ; 'd'; int g_iMajorVersion
0x1800c4401  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4408  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c440f  lea     r8, [rsp+4B0h+pv]
0x1800c4414  lea     rdx, aVersionnt; "VersionNT"
0x1800c441b  mov     [rsp+4B0h+pv], rcx
0x1800c4420  mov     rax, [rax+68h]
0x1800c4424  add     ebx, cs:?g_iMinorVersion@@3HA; int g_iMinorVersion
0x1800c442a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c442f  mov     rdx, [rsp+4B0h+pv]
0x1800c4434  mov     r8d, ebx
0x1800c4437  mov     rcx, rdi
0x1800c443a  call    SetPropertyInt
0x1800c443f  mov     rcx, [rsp+4B0h+pv]
0x1800c4444  mov     rax, [rcx]
0x1800c4447  mov     rax, [rax+10h]
0x1800c444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4450  xorps   xmm0, xmm0
0x1800c4453  lea     rcx, [rbp+3B0h+SystemInfo]; lpSystemInfo
0x1800c445a  movups  xmmword ptr [rbp+3B0h+SystemInfo], xmm0
0x1800c4461  movups  xmmword ptr [rbp+3B0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800c4468  movups  xmmword ptr [rbp+3B0h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800c446f  call    cs:__imp_GetNativeSystemInfo
0x1800c4476  nop     dword ptr [rax+rax+00h]
0x1800c447b  mov     eax, 0Ch
0x1800c4480  cmp     word ptr [rbp+3B0h+SystemInfo], ax
0x1800c4487  jnz     short loc_1800C44D7
0x1800c4489  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4490  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4497  lea     r8, [rsp+4B0h+pv]
0x1800c449c  mov     [rsp+4B0h+pv], r14
0x1800c44a1  lea     rdx, aVersionnt64; "VersionNT64"
0x1800c44a8  mov     rcx, r14
0x1800c44ab  mov     rax, [rax+68h]
0x1800c44af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c44b4  mov     rdx, [rsp+4B0h+pv]
0x1800c44b9  mov     r8d, ebx
0x1800c44bc  mov     rcx, rdi
0x1800c44bf  call    SetPropertyInt
0x1800c44c4  mov     rcx, [rsp+4B0h+pv]
0x1800c44c9  mov     rax, [rcx]
0x1800c44cc  mov     rax, [rax+10h]
0x1800c44d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c44d5  jmp     short loc_1800C453E
0x1800c44d7  test    r14b, r14b
0x1800c44da  jz      short loc_1800C4537
0x1800c44dc  mov     [rbp+3B0h+var_418], r12d
0x1800c44e0  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800c44e7  nop     dword ptr [rax+rax+00h]
0x1800c44ec  test    eax, eax
0x1800c44ee  jz      short loc_1800C4500
0x1800c44f0  lea     rcx, [rbp+3B0h+var_418]
0x1800c44f4  call    RtlpQueryContainersCompatMode
0x1800c44f9  test    eax, eax
0x1800c44fb  mov     eax, [rbp+3B0h+var_418]
0x1800c44fe  jns     short loc_1800C4503
0x1800c4500  mov     eax, r12d
0x1800c4503  test    eax, eax
0x1800c4505  jnz     short loc_1800C4537
0x1800c4507  lea     rdx, aVersionnt64; "VersionNT64"
0x1800c450e  lea     rcx, [rsp+4B0h+var_448]; this
0x1800c4513  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1800c4518  mov     r8d, ebx
0x1800c451b  mov     rcx, rdi
0x1800c451e  mov     rdx, [rax]
0x1800c4521  call    SetPropertyInt
0x1800c4526  mov     rcx, [rsp+4B0h+var_448]
0x1800c452b  mov     rax, [rcx]
0x1800c452e  mov     rax, [rax+10h]
0x1800c4532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4537  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c453e  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4545  lea     r8, [rsp+4B0h+pv]
0x1800c454a  mov     ebx, cs:?g_iWindowsBuild@@3HA; int g_iWindowsBuild
0x1800c4550  lea     rdx, aWindowsbuild; "WindowsBuild"
0x1800c4557  mov     rcx, r14
0x1800c455a  mov     [rsp+4B0h+pv], r14
0x1800c455f  mov     rax, [rax+68h]
0x1800c4563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4568  mov     rdx, [rsp+4B0h+pv]
0x1800c456d  mov     r8d, ebx
0x1800c4570  mov     rcx, rdi
0x1800c4573  call    SetPropertyInt
0x1800c4578  mov     rcx, [rsp+4B0h+pv]
0x1800c457d  mov     rax, [rcx]
0x1800c4580  mov     rax, [rax+10h]
0x1800c4584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4589  xor     edx, edx; Val
0x1800c458b  mov     [rbp+3B0h+hKey], r12
0x1800c458f  mov     r8d, 118h; Size
0x1800c4595  mov     [rbp+3B0h+cbData], 4
0x1800c459c  lea     rcx, [rbp+3B0h+VersionInformation.dwMajorVersion]; void *
0x1800c45a3  call    memset_0
0x1800c45a8  lea     rcx, [rbp+3B0h+VersionInformation]; lpVersionInformation
0x1800c45af  mov     [rbp+3B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800c45b9  call    cs:__imp_GetVersionExW
0x1800c45c0  nop     dword ptr [rax+rax+00h]
0x1800c45c5  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c45cc  lea     r8, [rsp+4B0h+pv]
0x1800c45d1  lea     rdx, aServicepacklev; "ServicePackLevel"
0x1800c45d8  mov     [rsp+4B0h+pv], r14
0x1800c45dd  mov     rcx, r14
0x1800c45e0  mov     rax, [rax+68h]
0x1800c45e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c45e9  movzx   r8d, [rbp+3B0h+var_AC]
0x1800c45f1  mov     rcx, rdi
0x1800c45f4  mov     rdx, [rsp+4B0h+pv]
0x1800c45f9  call    SetPropertyInt
0x1800c45fe  mov     rcx, [rsp+4B0h+pv]
0x1800c4603  mov     rax, [rcx]
0x1800c4606  mov     rax, [rax+10h]
0x1800c460a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c460f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4616  lea     r8, [rsp+4B0h+pv]
0x1800c461b  lea     rdx, aServicepacklev_0; "ServicePackLevelMinor"
0x1800c4622  mov     [rsp+4B0h+pv], r14
0x1800c4627  mov     rcx, r14
0x1800c462a  mov     rax, [rax+68h]
0x1800c462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4633  movzx   r8d, [rbp+3B0h+var_AA]
0x1800c463b  mov     rcx, rdi
0x1800c463e  mov     rdx, [rsp+4B0h+pv]
0x1800c4643  call    SetPropertyInt
0x1800c4648  mov     rcx, [rsp+4B0h+pv]
0x1800c464d  mov     rax, [rcx]
0x1800c4650  mov     rax, [rax+10h]
0x1800c4654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4659  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800c4660  lea     r8, [rsp+4B0h+pv]
0x1800c4665  lea     rdx, aMsintproductty; "MsiNTProductType"
0x1800c466c  mov     [rsp+4B0h+pv], r14
0x1800c4671  mov     rcx, r14
0x1800c4674  mov     rax, [rax+68h]
0x1800c4678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c467d  movzx   r8d, [rbp+3B0h+var_A6]
0x1800c4685  mov     rcx, rdi
0x1800c4688  mov     rdx, [rsp+4B0h+pv]
0x1800c468d  call    SetPropertyInt
0x1800c4692  mov     rcx, [rsp+4B0h+pv]
0x1800c4697  mov     rax, [rcx]
0x1800c469a  mov     rax, [rax+10h]
0x1800c469e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c46a3  mov     al, byte ptr [rbp+3B0h+var_A8]
0x1800c46a9  test    al, 4
0x1800c46ab  jz      short loc_1800C46EA
0x1800c46ad  lea     rdx, aMsintsuiteback; "MsiNTSuiteBackOffice"
0x1800c46b4  lea     rcx, [rsp+4B0h+var_448]; this
0x1800c46b9  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1800c46be  mov     ebx, 1
0x1800c46c3  mov     rcx, rdi
0x1800c46c6  mov     r8d, ebx
0x1800c46c9  mov     rdx, [rax]
0x1800c46cc  call    SetPropertyInt
0x1800c46d1  mov     rcx, [rsp+4B0h+var_448]
0x1800c46d6  mov     rax, [rcx]
0x1800c46d9  mov     rax, [rax+10h]
  ... truncated ...
```
