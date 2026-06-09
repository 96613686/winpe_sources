# CMsiServices::SetPlatformProperties(IMsiTable &,Bool,isppEnum,IMsiTable *)

- ea: `0x180083700`
- end: `0x1800855fe`
- name: `?SetPlatformProperties@CMsiServices@@UEAA?AW4Bool@@AEAVIMsiTable@@W42@W4isppEnum@@PEAV3@@Z`
- size: `7934`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180022120`
- `0x180025560`
- `0x180025a18`
- `0x180035a8c`
- `0x18004295c`
- `0x180061334`
- `0x1800620e4`
- `0x180064a78`
- `0x180066074`
- `0x180076e28`
- `0x180079dd0`
- `0x18007ed2c`
- `0x180082fc8`
- `0x180083178`
- `0x1800833ec`
- `0x180083700`
- `0x180085604`
- `0x1800856c0`
- `0x1800857ac`
- `0x180085858`
- `0x180085cec`
- `0x180085db8`
- `0x180085e08`
- `0x180085eac`
- `0x1800a5fc4`
- `0x1800c2854`
- `0x1800e80a4`
- `0x18010a5b8`
- `0x18014bb48`
- `0x18014c08c`
- `0x180155cfc`
- `0x18017c7c4`
- `0x18025a8e4`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x180083a3a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180083a3a`
- `ADVAPI32!GetUserNameW` at `0x180084e08`
- `ADVAPI32!GetUserNameW` at `0x180084e08`
- `ADVAPI32!RegQueryValueExW` at `0x1800847f0`
- `ADVAPI32!RegQueryValueExW` at `0x1800847f0`
- `ADVAPI32!RegCloseKey` at `0x180084632`
- `ADVAPI32!RegCloseKey` at `0x18008493d`
- `ADVAPI32!RegCloseKey` at `0x180084632`
- `ADVAPI32!RegCloseKey` at `0x18008493d`
- `KERNEL32!GetVersionExW` at `0x180083b0d`
- `KERNEL32!GetVersionExW` at `0x180083b0d`
- `KERNEL32!lstrlenW` at `0x180084093`
- `KERNEL32!lstrlenW` at `0x180084775`
- `KERNEL32!lstrlenW` at `0x180084093`
- `KERNEL32!lstrlenW` at `0x180084775`
- `KERNEL32!GetSystemDefaultLangID` at `0x180084f96`
- `KERNEL32!GetSystemDefaultLangID` at `0x180084f96`
- `KERNEL32!GetSystemDirectoryW` at `0x180083edd`
- `KERNEL32!GetSystemDirectoryW` at `0x180084083`
- `KERNEL32!GetSystemDirectoryW` at `0x180083edd`
- `KERNEL32!GetSystemDirectoryW` at `0x180084083`
- `KERNEL32!GetNativeSystemInfo` at `0x1800839cf`
- `KERNEL32!GetNativeSystemInfo` at `0x1800839cf`
- `KERNEL32!GetUserDefaultLangID` at `0x180084ed1`
- `KERNEL32!GetUserDefaultLangID` at `0x180084ed1`
- `KERNEL32!GetComputerNameW` at `0x180084f39`
- `KERNEL32!GetComputerNameW` at `0x180084f39`
- `KERNEL32!MulDiv` at `0x18008521f`
- `KERNEL32!MulDiv` at `0x18008521f`
- `USER32!ReleaseDC` at `0x180085406`
- `USER32!ReleaseDC` at `0x180085406`
- `USER32!GetSystemMetrics` at `0x180084fe7`
- `USER32!GetSystemMetrics` at `0x18008503a`
- `USER32!GetSystemMetrics` at `0x18008508d`
- `USER32!GetSystemMetrics` at `0x1800850e0`
- `USER32!GetSystemMetrics` at `0x180085133`
- `USER32!GetSystemMetrics` at `0x180085186`
- `USER32!GetSystemMetrics` at `0x180084fe7`
- `USER32!GetSystemMetrics` at `0x18008503a`
- `USER32!GetSystemMetrics` at `0x18008508d`
- `USER32!GetSystemMetrics` at `0x1800850e0`
- `USER32!GetSystemMetrics` at `0x180085133`
- `USER32!GetSystemMetrics` at `0x180085186`
- `USER32!GetDC` at `0x1800851c3`
- `USER32!GetDC` at `0x1800851c3`
- `GDI32!DeleteObject` at `0x180085352`
- `GDI32!DeleteObject` at `0x180085352`
- `GDI32!GetTextMetricsW` at `0x1800852bf`
- `GDI32!GetTextMetricsW` at `0x1800852bf`
- `GDI32!GetTextFaceW` at `0x1800852af`
- `GDI32!GetTextFaceW` at `0x1800852af`
- `GDI32!CreateFontIndirectW` at `0x18008528b`
- `GDI32!CreateFontIndirectW` at `0x18008528b`
- `GDI32!GetDeviceCaps` at `0x18008520e`
- `GDI32!GetDeviceCaps` at `0x1800853c6`
- `GDI32!GetDeviceCaps` at `0x18008520e`
- `GDI32!GetDeviceCaps` at `0x1800853c6`
- `GDI32!SelectObject` at `0x18008529a`
- `GDI32!SelectObject` at `0x180085344`
- `GDI32!SelectObject` at `0x18008529a`
- `GDI32!SelectObject` at `0x180085344`
- `ole32!CoTaskMemFree` at `0x18008459f`
- `ole32!CoTaskMemFree` at `0x18008459f`

## string_xrefs

- `0x18008439c`: `MSIINSTALLPERUSER`
- `0x180084259`: `CommonFiles64Folder`
- `0x180083b1f`: `ServicePackLevel`
- `0x18008424e`: `CommonFilesFolder`
- `0x180083b69`: `ServicePackLevelMinor`
- `0x180084150`: `TempFolder`
- `0x180085146`: `BorderSide`
- `0x180083bb3`: `MsiNTProductType`
- `0x18008421f`: `Common Files (x86)`
- `0x180084209`: `CommonFilesDir (x86)`
- `0x180084e93`: `UserSID`
- `0x18008422e`: `CommonFilesDir`
- `0x1800838c3`: `VersionMsi`
- `0x180084240`: `Common Files`
- `0x180084b66`: `TemplateFolder`
- `0x180083bfb`: `MsiNTSuiteBackOffice`
- `0x180083c41`: `MsiNTSuiteDataCenter`
- `0x180083c7b`: `MsiNTSuiteEnterprise`
- `0x180083cb5`: `MsiNTSuiteSmallBusiness`
- `0x180083cef`: `MsiNTSuiteSmallBusinessRestricted`
- `0x180083d2d`: `MsiNTSuitePersonal`
- `0x180083d6b`: `MsiNTSuiteWebServer`
- `0x18008451b`: `SHELL32::SHGetKnownFolderPath returned error E_INVALIDARG. Falling back to ProgramFiles/ProgramFilesCommon.`
- `0x1800848eb`: `SHELL32::SHGetKnownFolderPath failed with error: %d`
- `0x180084af8`: `Common Templates`
- `0x180084db8`: `MsiTrueAdminUser`
- `0x180084f54`: `ComputerName`
- `0x180085193`: `MsiTabletPC`

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
  bool v61; // cl
  const unsigned __int16 *v62; // r14
  char v63; // r14
  __int64 v64; // r14
  int v65; // ecx
  HKEY v66; // r10
  int v67; // r14d
  const wchar_t *v68; // rdx
  int v69; // r9d
  __int64 v70; // r9
  int v71; // eax
  int v72; // r14d
  struct IMsiRecord *v73; // rax
  int v74; // eax
  LPCWSTR v75; // r9
  const WCHAR *v76; // r14
  const unsigned __int16 *v77; // rax
  struct IMsiRecord *v78; // rax
  struct IMsiString *v79; // r14
  LPVOID v80; // rbx
  unsigned int *v81; // r15
  int v82; // r12d
  __int64 (__fastcall *v83)(__int64 *, __int64, __int64, void **, LPBYTE); // r14
  __int64 v84; // r8
  __int64 v85; // rdx
  void *v86; // r14
  __int64 (__fastcall *v87)(__int64 *, __int64, const wchar_t *, void **, LPBYTE); // rbx
  __int64 v88; // rax
  void (__fastcall *v89)(__int64 *, void **); // r14
  MsiString *v90; // rax
  MsiString *v91; // rax
  MsiString *v92; // rax
  MsiString *v93; // rax
  __int64 v94; // r14
  MsiString *v95; // rax
  struct IMsiString *v96; // r12
  LANGID UserDefaultLangID; // ax
  unsigned int v98; // r14d
  bool v99; // cl
  __int64 v100; // r14
  MsiString *v101; // rax
  LANGID SystemDefaultLangID; // ax
  unsigned int v103; // r14d
  int SystemMetrics; // eax
  unsigned int v105; // r14d
  int v106; // eax
  unsigned int v107; // r14d
  int v108; // eax
  unsigned int v109; // r14d
  int v110; // eax
  unsigned int v111; // r14d
  int v112; // eax
  unsigned int v113; // r14d
  unsigned int v114; // r14d
  MsiString *v115; // rax
  HDC DC; // r15
  int DeviceCaps; // eax
  int v118; // eax
  HFONT v119; // r13
  HGDIOBJ v120; // r14
  const struct IMsiString *v121; // rbx
  const struct IMsiString **v122; // rax
  struct IMsiRecord *v123; // rax
  MsiString *v124; // rax
  MsiString *v125; // rax
  unsigned int v126; // ebx
  MsiString *v127; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  struct IMsiString *v130; // [rsp+68h] [rbp-98h] BYREF
  void *v131; // [rsp+70h] [rbp-90h] BYREF
  bool v132; // [rsp+78h] [rbp-88h]
  const struct IMsiString *v133; // [rsp+80h] [rbp-80h] BYREF
  int v134[2]; // [rsp+88h] [rbp-78h] BYREF
  void *v135; // [rsp+90h] [rbp-70h] BYREF
  int v136; // [rsp+98h] [rbp-68h] BYREF
  __int64 v137; // [rsp+A0h] [rbp-60h] BYREF
  void *v138; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v139; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v140; // [rsp+B8h] [rbp-48h] BYREF
  int v141; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  DWORD pcbBuffer; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v144; // [rsp+D8h] [rbp-28h] BYREF
  int v145; // [rsp+E0h] [rbp-20h]
  DWORD cbData; // [rsp+E4h] [rbp-1Ch] BYREF
  int v147; // [rsp+E8h] [rbp-18h]
  _QWORD v148[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v149; // [rsp+110h] [rbp+10h]
  const wchar_t *v150; // [rsp+118h] [rbp+18h]
  const wchar_t *v151; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v152; // [rsp+128h] [rbp+28h]
  const GUID *v153; // [rsp+130h] [rbp+30h]
  int v154; // [rsp+138h] [rbp+38h]
  _QWORD v155[4]; // [rsp+140h] [rbp+40h] BYREF
  int v156; // [rsp+160h] [rbp+60h]
  const wchar_t *v157; // [rsp+168h] [rbp+68h]
  const wchar_t *v158; // [rsp+170h] [rbp+70h]
  const unsigned __int16 *v159; // [rsp+178h] [rbp+78h]
  const GUID *v160; // [rsp+180h] [rbp+80h]
  int v161; // [rsp+188h] [rbp+88h]
  const wchar_t *v162; // [rsp+190h] [rbp+90h]
  const wchar_t *v163; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v164; // [rsp+1A0h] [rbp+A0h]
  const GUID *v165; // [rsp+1A8h] [rbp+A8h]
  int v166; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v167; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v168; // [rsp+1C0h] [rbp+C0h]
  const unsigned __int16 *v169; // [rsp+1C8h] [rbp+C8h]
  const GUID *v170; // [rsp+1D0h] [rbp+D0h]
  int v171; // [rsp+1D8h] [rbp+D8h]
  struct tagTEXTMETRICW SystemInfo; // [rsp+1E0h] [rbp+E0h] BYREF
  LOGFONTW lf; // [rsp+220h] [rbp+120h] BYREF
  LPWSTR lpBuffer; // [rsp+280h] [rbp+180h] BYREF
  UINT uSize; // [rsp+288h] [rbp+188h]
  LPCWSTR lpString; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v177; // [rsp+2A0h] [rbp+1A0h]
  int v178; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v179; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int64 v180; // [rsp+2D0h] [rbp+1D0h]
  _OSVERSIONINFOW VersionInformation; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v182; // [rsp+404h] [rbp+304h]
  unsigned __int16 v183; // [rsp+406h] [rbp+306h]
  __int16 v184; // [rsp+408h] [rbp+308h]
  unsigned __int8 v185; // [rsp+40Ah] [rbp+30Ah]
  WCHAR Name[48]; // [rsp+410h] [rbp+310h] BYREF

  LODWORD(v131) = a4;
  v145 = a3;
  v134[0] = 0;
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
  v137 = 0;
  v10 = 0;
  if ( a5 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a5 + 128LL))(a5, 0);
    CComPointer<IMsiDatabase>::operator=(&v137, v11);
    v10 = v137;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 128LL))(a2, 0);
  v139 = v12;
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
  v138 = &MsiString::s_NullString;
  v15 = (int)StringCchPrintfW(v14, (int)uSize, L"%d.%02d", 5, 0) < 0;
  v16 = MsiString::s_NullString;
  if ( v15 )
    goto LABEL_16;
  v17 = *(void (__fastcall **)(void *, LPWSTR, int *))(MsiString::s_NullString + 96LL);
  *(_QWORD *)v134 = &MsiString::s_NullString;
  v17(&MsiString::s_NullString, lpBuffer, v134);
  v18 = *(_QWORD *)v134;
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"VersionMsi",
    &pv);
  LODWORD(v18) = SetProperty(v13, pv, v18);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v134 + 16LL))(*(_QWORD *)v134);
  if ( !(_DWORD)v18 )
    goto LABEL_19;
  v177 = 261;
  lpString = (LPCWSTR)operator new(0x20Au);
  if ( !lpString )
  {
    v177 = 0;
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
    v136 = 0;
    if ( !(unsigned int)RtlGetCurrentServiceSessionId()
      || (v15 = (int)RtlpQueryContainersCompatMode(&v136) < 0, v20 = v136, v15) )
    {
      v20 = 0;
    }
    if ( !v20 )
    {
      v21 = MsiString::MsiString((MsiString *)&v130, L"VersionNT64");
      SetPropertyInt(v13, *(_QWORD *)v21, v19);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
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
  SetPropertyInt(v13, pv, v182);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ServicePackLevelMinor",
    &pv);
  SetPropertyInt(v13, pv, v183);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, LPVOID *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"MsiNTProductType",
    &pv);
  SetPropertyInt(v13, pv, v185);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  v23 = v184;
  if ( (v184 & 4) != 0 )
  {
    v24 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteBackOffice");
    SetPropertyInt(v13, *(_QWORD *)v24, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v23 = v184;
  }
  if ( v23 < 0 )
  {
    v25 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteDataCenter");
    SetPropertyInt(v13, *(_QWORD *)v25, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v23 = v184;
  }
  if ( (v23 & 2) != 0 )
  {
    v26 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteEnterprise");
    SetPropertyInt(v13, *(_QWORD *)v26, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v23 = v184;
  }
  if ( (v23 & 1) != 0 )
  {
    v27 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteSmallBusiness");
    SetPropertyInt(v13, *(_QWORD *)v27, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v23 = v184;
  }
  if ( (v23 & 0x20) != 0 )
  {
    v28 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteSmallBusinessRestricted");
    SetPropertyInt(v13, *(_QWORD *)v28, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  v29 = v184;
  if ( (v184 & 0x200) != 0 )
  {
    v30 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuitePersonal");
    SetPropertyInt(v13, *(_QWORD *)v30, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v29 = v184;
  }
  if ( (v29 & 0x400) != 0 )
  {
    v31 = MsiString::MsiString((MsiString *)&v130, L"MsiNTSuiteWebServer");
    SetPropertyInt(v13, *(_QWORD *)v31, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  if ( !MsiGetWindowsDirectory((unsigned __int16 *)lpString, v177) )
  {
LABEL_46:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    goto LABEL_17;
  }
  SetDirectoryProperty(v13, L"WindowsFolder", lpString, v177);
  (*(void (__fastcall **)(void *, LPCWSTR, void **))(*(_QWORD *)v138 + 96LL))(v138, lpString, &v138);
  v32 = *a1;
  v144 = 0;
  v140 = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR, __int64 *))(v32 + 128))(a1, lpString, &v144);
  if ( v144 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v144 + 168LL))(v144);
    v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 80LL))(v33);
    if ( (int)StringCchCopyW(lpBuffer, (int)uSize, v34) < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_50:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v140);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v144);
      goto LABEL_46;
    }
    SetDirectoryProperty(v13, L"WindowsVolume", lpBuffer, uSize);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  GetSystemDirectoryW(lpBuffer, uSize);
  if ( g_fWinNT64 )
  {
    SetDirectoryProperty(v13, L"System64Folder", lpBuffer, uSize);
    if ( (int)StringCchCopyW((unsigned __int16 *)lpString, (int)v177, lpBuffer) < 0 )
      goto LABEL_50;
    v35 = *a1;
    pv = 0;
    v36 = *(__int64 (__fastcall **)(__int64 *, LPCWSTR, __int64))(v35 + 120);
    v37 = CComPointer<IEnumMsiRecord>::operator=(&pv);
    v38 = v36(a1, lpString, v37);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v140, v38)
      || (v39 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 112LL))(pv),
          *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v140, v39))
      || (v40 = pv,
          v41 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)pv + 104LL),
          v42 = MsiString::MsiString((MsiString *)&v130, L"SysWOW64"),
          v7 = 1,
          v43 = v41(v40, *(_QWORD *)v42),
          v44 = 1,
          *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v140, v43)) )
    {
      v44 = 0;
    }
    if ( (v7 & 1) != 0 )
    {
      v7 &= ~1u;
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
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
    v47 = MsiString::MsiString((MsiString *)&v130, L"TerminalServer");
    SetPropertyInt(v13, *(_QWORD *)v47, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  if ( IsRemoteAdminTSInstalled() )
  {
    v48 = MsiString::MsiString((MsiString *)&v130, L"RemoteAdminTS");
    SetPropertyInt(v13, *(_QWORD *)v48, 1);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  MsiGetTempPath(uSize, lpBuffer);
  SetDirectoryProperty(v13, L"TempFolder", lpBuffer, uSize);
  if ( g_fShortFileNames )
  {
    v49 = *(_QWORD *)MsiString::MsiString((MsiString *)&pv, L"1");
    v50 = MsiString::MsiString((MsiString *)&v130, L"SHORTFILENAMES");
    SetProperty(v13, *(_QWORD *)v50, v49);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  }
  v148[3] = &FOLDERID_UserProgramFiles;
  v149 = 0;
  v155[0] = L"ProgramFilesDir (x86)";
  v148[0] = L"ProgramFilesDir";
  v155[1] = L"Program Files (x86)";
  v148[1] = L"Program Files";
  v157 = L"CommonFilesDir (x86)";
  v148[2] = L"ProgramFilesFolder";
  v158 = L"Common Files (x86)";
  v150 = L"CommonFilesDir";
  v164 = L"ProgramFiles64Folder";
  v151 = L"Common Files";
  v152 = L"CommonFilesFolder";
  v169 = L"CommonFiles64Folder";
  v153 = &FOLDERID_UserProgramFilesCommon;
  v154 = 0;
  v155[2] = L"ProgramFilesFolder";
  v155[3] = &FOLDERID_UserProgramFiles;
  v156 = 0;
  v159 = L"CommonFilesFolder";
  v160 = &FOLDERID_UserProgramFilesCommon;
  v161 = 0;
  v162 = L"ProgramFilesDir";
  v163 = L"Program Files";
  v165 = &FOLDERID_UserProgramFiles;
  v166 = 1;
  v167 = L"CommonFilesDir";
  v168 = L"Common Files";
  v170 = &FOLDERID_UserProgramFilesCommon;
  v171 = 1;
  if ( g_fWinNT64 )
  {
    v51 = v155;
    v52 = 4;
  }
  else
  {
    v51 = v148;
    v52 = 2;
  }
  v147 = v52;
  if ( hKey )
    hKey = 0;
  v53 = v133;
  *lpString = 0;
  v136 = *((_DWORD *)v51 + 8);
  for ( i = 0; ; i = v141 + 1 )
  {
    v141 = i;
    if ( i >= v52 )
      break;
    pv = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"ALLUSERS",
      &pv);
    Property = GetProperty(v13, (const struct IMsiString *)pv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    v134[0] = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)Property + 32LL))(Property);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)Property + 16LL))(Property);
    pv = &MsiString::s_NullString;
    (*(void (__fastcall **)(void *, const unsigned __int16 *, LPVOID *))(MsiString::s_NullString + 104LL))(
      &MsiString::s_NullString,
      L"MSIINSTALLPERUSER",
      &pv);
    v56 = v7 | 6;
    v57 = GetProperty(v13, (const struct IMsiString *)pv);
    v132 = (*(unsigned int (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 56LL))(v57)
        && ((v58 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v133, L"ALLUSERS"),
             v56 |= 0x18u,
             v53 = GetProperty(v13, *v58),
             !(*(unsigned int (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v53 + 56LL))(v53))
         || v134[0] == 2);
    if ( (v56 & 0x10) != 0 )
    {
      v56 &= ~0x10u;
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v53 + 16LL))(v53);
    }
    if ( (v56 & 8) != 0 )
    {
      v56 &= ~8u;
      (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    }
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v57 + 16LL))(v57);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( !v132 )
      goto LABEL_101;
    pv = 0;
    StartImpersonating();
    ++HIDWORD(qword_1803096FC);
    v130 = (struct IMsiString *)(5LL * v141);
    UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    v62 = (const unsigned __int16 *)(int)((__int64 (__fastcall *)(_QWORD, __int64, void *, LPVOID *))SHELL32::SHGetKnownFolderPath)(
                                           v51[v60 + 3],
                                           0x8000,
                                           UserToken,
                                           &pv);
    if ( HIDWORD(qword_1803096FC) )
      --HIDWORD(qword_1803096FC);
    StopImpersonating(v61);
    if ( (_DWORD)v62 )
    {
      if ( (_DWORD)v62 != -2147024809 && (_DWORD)v62 != -2147024894 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SHELL32::SHGetKnownFolderPath failed with error: %d",
            v62,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
LABEL_134:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v140);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v144);
LABEL_22:
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString);
LABEL_19:
        v16 = MsiString::s_NullString;
LABEL_16:
        (*(void (__fastcall **)(void *))(v16 + 16))(&MsiString::s_NullString);
LABEL_17:
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v138 + 16LL))(v138);
LABEL_14:
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
LABEL_11:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v139);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v137);
        return 0;
      }
      v63 = 0;
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
        goto LABEL_134;
      v63 = 1;
      SetDirectoryProperty(v13, v51[(_QWORD)v130 + 2], lpBuffer, uSize);
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v63 )
    {
LABEL_101:
      v64 = v141;
      wcscpy(Name, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion");
      pv = &MsiString::s_NullString;
      v65 = v51[5 * v141 + 4];
      v130 = (struct IMsiString *)(5LL * v141);
      if ( v136 != v65 )
      {
        v136 = v65;
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
      }
      *lpBuffer = 0;
      v66 = hKey;
      if ( !hKey )
      {
        MsiString::operator=(&pv, L"HKEY_LOCAL_MACHINE");
        v67 = v136;
        if ( g_fWinNT64 )
        {
          v68 = L"64";
          if ( v136 != 1 )
            v68 = L"32";
          MsiString::operator+=(&pv, v68);
        }
        MsiString::operator+=(&pv, L"\\");
        MsiString::operator+=(&pv, Name);
        if ( g_fWinNT64 )
        {
          v69 = 256;
          if ( v67 != 1 )
            v69 = 512;
          v70 = v69 | 0x20019u;
        }
        else
        {
          v70 = 131097;
        }
        v71 = ((__int64 (__fastcall *)(__int64, WCHAR *, _QWORD, __int64, HKEY *))RegOpenKeyAPI)(
                -2147483646,
                Name,
                0,
                v70,
                &hKey);
        v72 = v71;
        if ( v71 )
        {
          v73 = PostError(1402, (const struct IMsiString *)pv, v71);
          CComPointer<IMsiDatabase>::operator=(&v140, v73);
        }
        v66 = hKey;
        if ( !hKey )
        {
          if ( !v72 )
            goto LABEL_118;
LABEL_119:
          if ( !*lpString )
          {
            MsiGetWindowsDirectory((unsigned __int16 *)lpString, v177);
            v74 = lstrlenW(lpString);
            v75 = lpString;
            if ( lpString[v74 - 1] != 92 )
            {
              lpString[v74] = 92;
              if ( v74 >= (int)(v177 - 1) )
                v75[v74] = 0;
              else
                v75[v74 + 1] = 0;
            }
          }
          v79 = v130;
          lpData = (LPBYTE)v51[(_QWORD)v130 + 1];
          if ( (int)StringCchPrintfW(lpBuffer, (int)uSize, L"%s%s") < 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            goto LABEL_134;
          }
          goto LABEL_130;
        }
        v64 = v141;
      }
      cbData = 2 * uSize;
      v76 = (const WCHAR *)v51[5 * v64];
      v134[0] = RegQueryValueExW(v66, v76, 0, 0, (LPBYTE)lpBuffer, &cbData);
      if ( v134[0] )
      {
        v77 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 80LL))(pv);
        v78 = PostError(1405, v76, v77, v134[0]);
        CComPointer<IMsiDatabase>::operator=(&v140, v78);
        goto LABEL_119;
      }
LABEL_118:
      if ( !*lpBuffer )
        goto LABEL_119;
      v79 = v130;
LABEL_130:
      SetDirectoryProperty(v13, v51[(_QWORD)v79 + 2], lpBuffer, uSize);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    v7 = v56 & 0xFFFFFFF9;
    v52 = v147;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v80 = 0;
  v135 = &MsiString::s_NullString;
  v81 = 0;
  pv = 0;
  v82 = 0;
  while ( 2 )
  {
    switch ( v82 )
    {
      case 0:
        v81 = (unsigned int *)&rgShellFolders;
        goto LABEL_150;
      case 1:
        v81 = (unsigned int *)&rgAllUsersProfileShellFolders;
        if ( !v145 )
          v81 = (unsigned int *)&rgPersonalProfileShellFolders;
LABEL_149:
        if ( (*v81 & 0x80000000) == 0 )
          goto LABEL_150;
        break;
      case 2:
        if ( v10 )
        {
          if ( !v145 )
          {
            v81 = (unsigned int *)&rgAllUsersProfileShellFolders;
            goto LABEL_149;
          }
          v81 = (unsigned int *)&rgPersonalProfileShellFolders;
          do
          {
LABEL_150:
            v83 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, void **, LPBYTE))(*a1 + 344);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v135 + 16LL))(v135);
            v84 = *((_QWORD *)v81 + 2);
            v85 = *v81;
            v135 = &MsiString::s_NullString;
            LOBYTE(lpData) = 1;
            v86 = (void *)v83(a1, v85, v84, &v135, lpData);
            if ( v80 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
            v80 = v86;
            if ( !v86 && (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v135 + 56LL))(v135) )
            {
              (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v135 + 88LL))(v135, lpBuffer, uSize - 1);
              if ( v82 != 2 )
                SetDirectoryProperty(v13, *((_QWORD *)v81 + 1), lpBuffer, uSize);
              if ( v10 )
                CacheFolderProperty(v10, *v81, lpBuffer, uSize);
            }
            v81 += 8;
          }
          while ( (*v81 & 0x80000000) == 0 );
          pv = v86;
        }
        break;
      default:
        goto LABEL_149;
    }
    if ( ++v82 < 3 )
      continue;
    break;
  }
  if ( v145 )
  {
    v87 = *(__int64 (__fastcall **)(__int64 *, __int64, const wchar_t *, void **, LPBYTE))(*a1 + 344);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v135 + 16LL))(v135);
    v135 = &MsiString::s_NullString;
    LOBYTE(lpData) = 0;
    v88 = v87(a1, 45, L"Common Templates", &v135, lpData);
    CComPointer<IMsiDatabase>::operator=(&pv, v88);
    v80 = pv;
    if ( !pv )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v135 + 56LL))(v135) )
      {
        (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v135 + 88LL))(v135, lpBuffer, uSize - 1);
        SetDirectoryProperty(v13, L"TemplateFolder", lpBuffer, uSize);
      }
    }
  }
  v89 = *(void (__fastcall **)(__int64 *, void **))(*a1 + 384);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v135 + 16LL))(v135);
  v135 = &MsiString::s_NullString;
  v89(a1, &v135);
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v135 + 56LL))(v135) )
  {
    (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v135 + 88LL))(v135, lpBuffer, uSize - 1);
    SetDirectoryProperty(v13, L"FontsFolder", lpBuffer, uSize);
  }
  *(_QWORD *)v134 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"GPTSupport",
    v134);
  SetPropertyInt(v13, *(_QWORD *)v134, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v134 + 16LL))(*(_QWORD *)v134);
  *(_QWORD *)v134 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"OLEAdvtSupport",
    v134);
  SetPropertyInt(v13, *(_QWORD *)v134, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v134 + 16LL))(*(_QWORD *)v134);
  *(_QWORD *)v134 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, int *))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ShellAdvtSupport",
    v134);
  SetPropertyInt(v13, *(_QWORD *)v134, 1);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v134 + 16LL))(*(_QWORD *)v134);
  SetProcessorProperty(v13, (unsigned int)v131);
  memset_0(&v178, 0, 0x40u);
  v178 = 64;
  if ( (unsigned int)((__int64 (__fastcall *)(int *))KERNEL32::GlobalMemoryStatusEx)(&v178) )
  {
    v90 = MsiString::MsiString((MsiString *)&v133, L"PhysicalMemory");
    SetPropertyInt(v13, *(_QWORD *)v90, (unsigned __int64)(v179 + 650000) >> 20);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    v91 = MsiString::MsiString((MsiString *)&v133, L"VirtualMemory");
    SetPropertyInt(v13, *(_QWORD *)v91, v180 >> 20);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
  }
  if ( IsAdmin() )
  {
    v92 = MsiString::MsiString((MsiString *)&v133, L"AdminUser");
    SetPropertyInt(v13, *(_QWORD *)v92, 1);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    v93 = MsiString::MsiString((MsiString *)&v133, L"MsiTrueAdminUser");
    SetPropertyInt(v13, *(_QWORD *)v93, 1);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
  }
  pcbBuffer = uSize;
  StartImpersonating();
  pcbBuffer = uSize;
  if ( GetUserNameW(lpBuffer, &pcbBuffer) )
  {
    v94 = *(_QWORD *)MsiString::MsiString((MsiString *)&v130, lpBuffer);
    v95 = MsiString::MsiString((MsiString *)&v133, L"LogonUser");
    SetProperty(v13, *(_QWORD *)v95, v94);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v130 = (struct IMsiString *)&MsiString::s_NullString;
  GetCurrentUserStringSID(&v130);
  v131 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"UserSID",
    &v131);
  v96 = v130;
  SetProperty(v13, v131, v130);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  UserDefaultLangID = GetUserDefaultLangID();
  v131 = &MsiString::s_NullString;
  v98 = UserDefaultLangID;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"UserLanguageID",
    &v131);
  SetPropertyInt(v13, v131, v98);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  StopImpersonating(v99);
  pcbBuffer = uSize;
  if ( GetComputerNameW(lpBuffer, &pcbBuffer) )
  {
    v100 = *(_QWORD *)MsiString::MsiString((MsiString *)&v130, lpBuffer);
    v101 = MsiString::MsiString((MsiString *)&v133, L"ComputerName");
    SetProperty(v13, *(_QWORD *)v101, v100);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
  }
  SystemDefaultLangID = GetSystemDefaultLangID();
  v131 = &MsiString::s_NullString;
  v103 = SystemDefaultLangID;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"SystemLanguageID",
    &v131);
  SetPropertyInt(v13, v131, v103);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  SystemMetrics = GetSystemMetrics(0);
  v131 = &MsiString::s_NullString;
  v105 = SystemMetrics;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ScreenX",
    &v131);
  SetPropertyInt(v13, v131, v105);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  v106 = GetSystemMetrics(1);
  v131 = &MsiString::s_NullString;
  v107 = v106;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"ScreenY",
    &v131);
  SetPropertyInt(v13, v131, v107);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  v108 = GetSystemMetrics(4);
  v131 = &MsiString::s_NullString;
  v109 = v108;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"CaptionHeight",
    &v131);
  SetPropertyInt(v13, v131, v109);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  v110 = GetSystemMetrics(5);
  v131 = &MsiString::s_NullString;
  v111 = v110;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"BorderTop",
    &v131);
  SetPropertyInt(v13, v131, v111);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  v112 = GetSystemMetrics(6);
  v131 = &MsiString::s_NullString;
  v113 = v112;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(MsiString::s_NullString + 104LL))(
    &MsiString::s_NullString,
    L"BorderSide",
    &v131);
  SetPropertyInt(v13, v131, v113);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
  v114 = GetSystemMetrics(86);
  if ( v114 )
  {
    v115 = MsiString::MsiString((MsiString *)&v133, L"MsiTabletPC");
    SetPropertyInt(v13, *(_QWORD *)v115, v114);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
  }
  DC = GetDC(0);
  if ( DC )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    memset_0(&lf, 0, sizeof(lf));
    DeviceCaps = GetDeviceCaps(DC, 90);
    v118 = MulDiv(10, DeviceCaps, 72);
    lf.lfWeight = 400;
    lf.lfHeight = -v118;
    if ( (int)StringCchCopyW(lf.lfFaceName, 0x20u, L"MS Sans Serif") < 0 )
    {
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v96 + 16LL))(v96);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v135 + 16LL))(v135);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&pv);
      goto LABEL_134;
    }
    v119 = CreateFontIndirectW(&lf);
    v120 = SelectObject(DC, v119);
    GetTextFaceW(DC, 32, Name);
    GetTextMetricsW(DC, &SystemInfo);
    v121 = *(const struct IMsiString **)MsiString::MsiString((MsiString *)&v130, Name);
    v122 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v133, L"MS Sans Serif");
    v123 = PostError(2898, *v122, v121, lf.lfCharSet, SystemInfo.tmHeight, 1);
    CComPointer<IMsiDatabase>::operator=(&pv, v123);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    SelectObject(DC, v120);
    if ( v119 )
      DeleteObject(v119);
    v124 = MsiString::MsiString((MsiString *)&v133, L"TextHeight");
    SetPropertyInt(v13, *(_QWORD *)v124, (unsigned int)SystemInfo.tmHeight);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    v125 = MsiString::MsiString((MsiString *)&v130, L"TextInternalLeading");
    SetPropertyInt(v13, *(_QWORD *)v125, (unsigned int)SystemInfo.tmInternalLeading);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v130 + 16LL))(v130);
    v126 = GetDeviceCaps(DC, 12);
    v127 = MsiString::MsiString((MsiString *)&v133, L"ColorBits");
    SetPropertyInt(v13, *(_QWORD *)v127, v126);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v133 + 16LL))(v133);
    v80 = pv;
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
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v96 + 16LL))(v96);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v135 + 16LL))(v135);
  if ( v80 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
  if ( v140 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
  if ( v144 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v144 + 16LL))(v144);
  if ( (int)v177 > 1 )
    operator delete((void *)lpString);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v138 + 16LL))(v138);
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
0x180083700  mov     [rsp-8+arg_10], rbx
0x180083705  push    rbp
0x180083706  push    rsi
0x180083707  push    rdi
0x180083708  push    r12
0x18008370a  push    r13
0x18008370c  push    r14
0x18008370e  push    r15
0x180083710  lea     rbp, [rsp-380h]
0x180083718  sub     rsp, 480h
0x18008371f  mov     rax, cs:__security_cookie
0x180083726  xor     rax, rsp
0x180083729  mov     [rbp+3B0h+var_40], rax
0x180083730  mov     r10, [rbp+3B0h+arg_20]
0x180083737  xor     r12d, r12d
0x18008373a  mov     dword ptr [rsp+4B0h+var_440], r9d
0x18008373f  mov     r13, rcx
0x180083742  mov     [rbp+3B0h+var_3D0], r8d
0x180083746  mov     rbx, rdx
0x180083749  mov     [rbp+3B0h+var_428], r12d
0x18008374d  mov     r15d, r12d
0x180083750  mov     ecx, r9d
0x180083753  test    r9d, r9d
0x180083756  jz      short loc_180083778
0x180083758  sub     ecx, 1
0x18008375b  jz      short loc_180083773
0x18008375d  sub     ecx, 1
0x180083760  jz      short loc_18008376E
0x180083762  cmp     ecx, 1
0x180083765  jz      short loc_18008376E
0x180083767  xor     eax, eax
0x180083769  jmp     loc_1800855D4
0x18008376e  mov     r14b, 1
0x180083771  jmp     short loc_18008377F
0x180083773  mov     r14b, r12b
0x180083776  jmp     short loc_18008377F
0x180083778  mov     r14b, cs:?g_fWinNT64@@3_NA; bool g_fWinNT64
0x18008377f  mov     [rbp+3B0h+var_410], r12
0x180083783  mov     rsi, r12
0x180083786  test    r10, r10
0x180083789  jz      short loc_1800837AF
0x18008378b  mov     rax, [r10]
0x18008378e  xor     edx, edx
0x180083790  mov     rcx, r10
0x180083793  mov     rax, [rax+80h]
0x18008379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008379f  mov     rdx, rax
0x1800837a2  lea     rcx, [rbp+3B0h+var_410]
0x1800837a6  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800837ab  mov     rsi, [rbp+3B0h+var_410]
0x1800837af  mov     rax, [rbx]
0x1800837b2  xor     edx, edx
0x1800837b4  mov     rcx, rbx
0x1800837b7  mov     rax, [rax+80h]
0x1800837be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800837c3  mov     [rbp+3B0h+var_400], rax
0x1800837c7  mov     rdi, rax
0x1800837ca  test    rax, rax
0x1800837cd  jnz     short loc_1800837E3
0x1800837cf  lea     rcx, [rbp+3B0h+var_400]
0x1800837d3  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800837d8  lea     rcx, [rbp+3B0h+var_410]
0x1800837dc  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800837e1  jmp     short loc_180083767
0x1800837e3  mov     rax, [rax]
0x1800837e6  mov     edx, 1
0x1800837eb  mov     rcx, rdi
0x1800837ee  mov     rax, [rax+30h]
0x1800837f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800837f7  mov     ecx, 20Ah; unsigned __int64
0x1800837fc  mov     [rbp+3B0h+uSize], 105h
0x180083806  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008380b  mov     [rbp+3B0h+lpBuffer], rax
0x180083812  test    rax, rax
0x180083815  jnz     short loc_18008382C
0x180083817  mov     [rbp+3B0h+uSize], r12d
0x18008381e  lea     rcx, [rbp+3B0h+lpBuffer]
0x180083825  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x18008382a  jmp     short loc_1800837CF
0x18008382c  movsxd  rdx, [rbp+3B0h+uSize]; unsigned __int64
0x180083833  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18008383a  mov     r9d, 5
0x180083840  mov     [rbp+3B0h+var_408], rbx
0x180083844  lea     r8, aD02d; "%d.%02d"
0x18008384b  mov     [rsp+4B0h+lpData], r12
0x180083850  mov     rcx, rax; unsigned __int16 *
0x180083853  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083858  test    eax, eax
0x18008385a  mov     rcx, rbx
0x18008385d  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083864  jns     short loc_180083894
0x180083866  mov     rax, [rax+10h]
0x18008386a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008386f  mov     rcx, rbx
0x180083872  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083879  mov     rax, [rax+10h]
0x18008387d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083882  mov     rcx, [rbp+3B0h+var_408]
0x180083886  mov     rax, [rcx]
0x180083889  mov     rax, [rax+10h]
0x18008388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083892  jmp     short loc_18008381E
0x180083894  mov     rdx, [rbp+3B0h+lpBuffer]
0x18008389b  lea     r8, [rbp+3B0h+var_428]
0x18008389f  mov     rax, [rax+60h]
0x1800838a3  mov     qword ptr [rbp+3B0h+var_428], rbx
0x1800838a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838ac  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800838b3  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800838ba  mov     rbx, qword ptr [rbp+3B0h+var_428]
0x1800838be  lea     r8, [rsp+4B0h+pv]
0x1800838c3  lea     rdx, aVersionmsi; "VersionMsi"
0x1800838ca  mov     [rsp+4B0h+pv], rcx
0x1800838cf  mov     rax, [rax+68h]
0x1800838d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838d8  mov     rdx, [rsp+4B0h+pv]
0x1800838dd  mov     r8, rbx
0x1800838e0  mov     rcx, rdi
0x1800838e3  call    SetProperty
0x1800838e8  mov     rcx, [rsp+4B0h+pv]
0x1800838ed  mov     ebx, eax
0x1800838ef  mov     rax, [rcx]
0x1800838f2  mov     rax, [rax+10h]
0x1800838f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838fb  mov     rcx, qword ptr [rbp+3B0h+var_428]
0x1800838ff  mov     rax, [rcx]
0x180083902  mov     rax, [rax+10h]
0x180083906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008390b  test    ebx, ebx
0x18008390d  jnz     short loc_180083925
0x18008390f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083916  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18008391d  mov     rcx, rbx
0x180083920  jmp     loc_180083866
0x180083925  mov     ecx, 20Ah; unsigned __int64
0x18008392a  mov     [rbp+3B0h+var_210], 105h
0x180083934  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083939  mov     [rbp+3B0h+lpString], rax
0x180083940  test    rax, rax
0x180083943  jnz     short loc_18008395A
0x180083945  mov     [rbp+3B0h+var_210], r12d
0x18008394c  lea     rcx, [rbp+3B0h+lpString]
0x180083953  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x180083958  jmp     short loc_18008390F
0x18008395a  imul    ebx, cs:?g_iMajorVersion@@3HA, 64h ; 'd'; int g_iMajorVersion
0x180083961  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083968  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18008396f  lea     r8, [rsp+4B0h+pv]
0x180083974  lea     rdx, aVersionnt; "VersionNT"
0x18008397b  mov     [rsp+4B0h+pv], rcx
0x180083980  mov     rax, [rax+68h]
0x180083984  add     ebx, cs:?g_iMinorVersion@@3HA; int g_iMinorVersion
0x18008398a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008398f  mov     rdx, [rsp+4B0h+pv]
0x180083994  mov     r8d, ebx
0x180083997  mov     rcx, rdi
0x18008399a  call    SetPropertyInt
0x18008399f  mov     rcx, [rsp+4B0h+pv]
0x1800839a4  mov     rax, [rcx]
0x1800839a7  mov     rax, [rax+10h]
0x1800839ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839b0  xorps   xmm0, xmm0
0x1800839b3  lea     rcx, [rbp+3B0h+SystemInfo]; lpSystemInfo
0x1800839ba  movups  xmmword ptr [rbp+3B0h+SystemInfo], xmm0
0x1800839c1  movups  xmmword ptr [rbp+3B0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800839c8  movups  xmmword ptr [rbp+3B0h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800839cf  call    cs:__imp_GetNativeSystemInfo
0x1800839d5  mov     eax, 0Ch
0x1800839da  cmp     word ptr [rbp+3B0h+SystemInfo], ax
0x1800839e1  jnz     short loc_180083A31
0x1800839e3  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800839ea  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800839f1  lea     r8, [rsp+4B0h+pv]
0x1800839f6  mov     [rsp+4B0h+pv], r14
0x1800839fb  lea     rdx, aVersionnt64; "VersionNT64"
0x180083a02  mov     rcx, r14
0x180083a05  mov     rax, [rax+68h]
0x180083a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a0e  mov     rdx, [rsp+4B0h+pv]
0x180083a13  mov     r8d, ebx
0x180083a16  mov     rcx, rdi
0x180083a19  call    SetPropertyInt
0x180083a1e  mov     rcx, [rsp+4B0h+pv]
0x180083a23  mov     rax, [rcx]
0x180083a26  mov     rax, [rax+10h]
0x180083a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a2f  jmp     short loc_180083A92
0x180083a31  test    r14b, r14b
0x180083a34  jz      short loc_180083A8B
0x180083a36  mov     [rbp+3B0h+var_418], r12d
0x180083a3a  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180083a40  test    eax, eax
0x180083a42  jz      short loc_180083A54
0x180083a44  lea     rcx, [rbp+3B0h+var_418]
0x180083a48  call    RtlpQueryContainersCompatMode
0x180083a4d  test    eax, eax
0x180083a4f  mov     eax, [rbp+3B0h+var_418]
0x180083a52  jns     short loc_180083A57
0x180083a54  mov     eax, r12d
0x180083a57  test    eax, eax
0x180083a59  jnz     short loc_180083A8B
0x180083a5b  lea     rdx, aVersionnt64; "VersionNT64"
0x180083a62  lea     rcx, [rsp+4B0h+var_448]; this
0x180083a67  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180083a6c  mov     r8d, ebx
0x180083a6f  mov     rcx, rdi
0x180083a72  mov     rdx, [rax]
0x180083a75  call    SetPropertyInt
0x180083a7a  mov     rcx, [rsp+4B0h+var_448]
0x180083a7f  mov     rax, [rcx]
0x180083a82  mov     rax, [rax+10h]
0x180083a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a8b  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083a92  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083a99  lea     r8, [rsp+4B0h+pv]
0x180083a9e  mov     ebx, cs:?g_iWindowsBuild@@3HA; int g_iWindowsBuild
0x180083aa4  lea     rdx, aWindowsbuild; "WindowsBuild"
0x180083aab  mov     rcx, r14
0x180083aae  mov     [rsp+4B0h+pv], r14
0x180083ab3  mov     rax, [rax+68h]
0x180083ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083abc  mov     rdx, [rsp+4B0h+pv]
0x180083ac1  mov     r8d, ebx
0x180083ac4  mov     rcx, rdi
0x180083ac7  call    SetPropertyInt
0x180083acc  mov     rcx, [rsp+4B0h+pv]
0x180083ad1  mov     rax, [rcx]
0x180083ad4  mov     rax, [rax+10h]
0x180083ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083add  xor     edx, edx; Val
0x180083adf  mov     [rbp+3B0h+hKey], r12
0x180083ae3  mov     r8d, 118h; Size
0x180083ae9  mov     [rbp+3B0h+cbData], 4
0x180083af0  lea     rcx, [rbp+3B0h+VersionInformation.dwMajorVersion]; void *
0x180083af7  call    memset_0
0x180083afc  lea     rcx, [rbp+3B0h+VersionInformation]; lpVersionInformation
0x180083b03  mov     [rbp+3B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180083b0d  call    cs:__imp_GetVersionExW
0x180083b13  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083b1a  lea     r8, [rsp+4B0h+pv]
0x180083b1f  lea     rdx, aServicepacklev; "ServicePackLevel"
0x180083b26  mov     [rsp+4B0h+pv], r14
0x180083b2b  mov     rcx, r14
0x180083b2e  mov     rax, [rax+68h]
0x180083b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b37  movzx   r8d, [rbp+3B0h+var_AC]
0x180083b3f  mov     rcx, rdi
0x180083b42  mov     rdx, [rsp+4B0h+pv]
0x180083b47  call    SetPropertyInt
0x180083b4c  mov     rcx, [rsp+4B0h+pv]
0x180083b51  mov     rax, [rcx]
0x180083b54  mov     rax, [rax+10h]
0x180083b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b5d  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083b64  lea     r8, [rsp+4B0h+pv]
0x180083b69  lea     rdx, aServicepacklev_0; "ServicePackLevelMinor"
0x180083b70  mov     [rsp+4B0h+pv], r14
0x180083b75  mov     rcx, r14
0x180083b78  mov     rax, [rax+68h]
0x180083b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b81  movzx   r8d, [rbp+3B0h+var_AA]
0x180083b89  mov     rcx, rdi
0x180083b8c  mov     rdx, [rsp+4B0h+pv]
0x180083b91  call    SetPropertyInt
0x180083b96  mov     rcx, [rsp+4B0h+pv]
0x180083b9b  mov     rax, [rcx]
0x180083b9e  mov     rax, [rax+10h]
0x180083ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ba7  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180083bae  lea     r8, [rsp+4B0h+pv]
0x180083bb3  lea     rdx, aMsintproductty; "MsiNTProductType"
0x180083bba  mov     [rsp+4B0h+pv], r14
0x180083bbf  mov     rcx, r14
0x180083bc2  mov     rax, [rax+68h]
0x180083bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083bcb  movzx   r8d, [rbp+3B0h+var_A6]
0x180083bd3  mov     rcx, rdi
0x180083bd6  mov     rdx, [rsp+4B0h+pv]
0x180083bdb  call    SetPropertyInt
0x180083be0  mov     rcx, [rsp+4B0h+pv]
0x180083be5  mov     rax, [rcx]
0x180083be8  mov     rax, [rax+10h]
0x180083bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083bf1  mov     al, byte ptr [rbp+3B0h+var_A8]
0x180083bf7  test    al, 4
0x180083bf9  jz      short loc_180083C38
0x180083bfb  lea     rdx, aMsintsuiteback; "MsiNTSuiteBackOffice"
0x180083c02  lea     rcx, [rsp+4B0h+var_448]; this
0x180083c07  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180083c0c  mov     ebx, 1
0x180083c11  mov     rcx, rdi
0x180083c14  mov     r8d, ebx
0x180083c17  mov     rdx, [rax]
0x180083c1a  call    SetPropertyInt
0x180083c1f  mov     rcx, [rsp+4B0h+var_448]
0x180083c24  mov     rax, [rcx]
0x180083c27  mov     rax, [rax+10h]
0x180083c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c30  mov     al, byte ptr [rbp+3B0h+var_A8]
0x180083c36  jmp     short loc_180083C3D
  ... truncated ...
```
