# CDevEnvAppId::Run(ushort *,int)

- ea: `0x14000ccfc`
- end: `0x14000f0be`
- name: `?Run@CDevEnvAppId@@SAHPEAGH@Z`
- size: `9154`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `86`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f9f8`

## callees

- `0x140001020`
- `0x1400013a0`
- `0x140002190`
- `0x140002196`
- `0x140002c10`
- `0x140002dd0`
- `0x140002e30`
- `0x140002f00`
- `0x140003160`
- `0x140003ec0`
- `0x140003f60`
- `0x140004950`
- `0x140007740`
- `0x140007b08`
- `0x1400086e8`
- `0x140008970`
- `0x140009690`
- `0x14000972c`
- `0x140009b10`
- `0x140009ba4`
- `0x14000b1b4`
- `0x14000ccfc`
- `0x14000f0c0`
- `0x14000f144`
- `0x14000f26c`
- `0x140011b10`
- `0x140011b9c`
- `0x140011f38`
- `0x140012004`
- `0x140012070`
- `0x1400120e0`
- `0x140012440`
- `0x140012ad8`
- `0x140012bcc`
- `0x140012c20`
- `0x140012f10`
- `0x140013044`
- `0x140013100`
- `0x140013da0`
- `0x140018b58`
- `0x140019b18`
- `0x140019fc4`
- `0x14001b3e0`
- `0x14001b3f0`
- `0x14001ca30`
- `0x14001cec0`
- `0x14001e390`
- `0x14001e550`
- `0x140021048`
- `0x140021988`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000e657`
- `ADVAPI32!RegCloseKey` at `0x14000e8e2`
- `ADVAPI32!RegCloseKey` at `0x14000eae2`
- `ADVAPI32!RegCloseKey` at `0x14000e657`
- `ADVAPI32!RegCloseKey` at `0x14000e8e2`
- `ADVAPI32!RegCloseKey` at `0x14000eae2`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e58e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e58e`
- `ADVAPI32!RegSetValueExW` at `0x14000e8d4`
- `ADVAPI32!RegSetValueExW` at `0x14000e8d4`
- `ADVAPI32!RegQueryValueExW` at `0x14000e5cb`
- `ADVAPI32!RegQueryValueExW` at `0x14000e624`
- `ADVAPI32!RegQueryValueExW` at `0x14000e5cb`
- `ADVAPI32!RegQueryValueExW` at `0x14000e624`
- `KERNEL32!LoadLibraryW` at `0x14000d24d`
- `KERNEL32!LoadLibraryW` at `0x14000d24d`
- `KERNEL32!SetStdHandle` at `0x14000d0e3`
- `KERNEL32!SetStdHandle` at `0x14000d0e3`
- `KERNEL32!DuplicateHandle` at `0x14000d0d0`
- `KERNEL32!DuplicateHandle` at `0x14000d0d0`
- `KERNEL32!GetCurrentProcess` at `0x14000d0ab`
- `KERNEL32!GetCurrentProcess` at `0x14000d0ab`
- `KERNEL32!GetStdHandle` at `0x14000d096`
- `KERNEL32!GetStdHandle` at `0x14000d096`
- `KERNEL32!WerUnregisterRuntimeExceptionModule` at `0x14000eefd`
- `KERNEL32!WerUnregisterRuntimeExceptionModule` at `0x14000eefd`
- `KERNEL32!DebugBreak` at `0x14000d08b`
- `KERNEL32!DebugBreak` at `0x14000d08b`
- `KERNEL32!WerRegisterRuntimeExceptionModule` at `0x14000cfa1`
- `KERNEL32!WerRegisterRuntimeExceptionModule` at `0x14000cfa1`
- `KERNEL32!CloseHandle` at `0x14000d0f4`
- `KERNEL32!CloseHandle` at `0x14000d0f4`
- `KERNEL32!GetModuleFileNameW` at `0x14000ced3`
- `KERNEL32!GetModuleFileNameW` at `0x14000ced3`
- `KERNEL32!GetProcAddress` at `0x14000d262`
- `KERNEL32!GetProcAddress` at `0x14000eb60`
- `KERNEL32!GetProcAddress` at `0x14000eea7`
- `KERNEL32!GetProcAddress` at `0x14000d262`
- `KERNEL32!GetProcAddress` at `0x14000eb60`
- `KERNEL32!GetProcAddress` at `0x14000eea7`
- `KERNEL32!GetLastError` at `0x14000eb81`
- `KERNEL32!GetLastError` at `0x14000eeb2`
- `KERNEL32!GetLastError` at `0x14000eb81`
- `KERNEL32!GetLastError` at `0x14000eeb2`
- `VCRUNTIME140!wcsrchr` at `0x14000cf1f`
- `VCRUNTIME140!wcsrchr` at `0x14000cf1f`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x14000d6a2`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x14000d6a2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14000d38f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14000d38f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000cee2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000ed9d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000cee2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000ed9d`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x14000d13e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x14000d13e`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x14000e845`
- `api-ms-win-crt-stdio-l1-1-0!fclose` at `0x14000e845`
- `api-ms-win-crt-stdio-l1-1-0!fopen_s` at `0x14000e822`
- `api-ms-win-crt-stdio-l1-1-0!fopen_s` at `0x14000e822`
- `USER32!MessageBoxW` at `0x14000df48`
- `USER32!MessageBoxW` at `0x14000df48`
- `ole32!IIDFromString` at `0x14000e5e3`
- `ole32!IIDFromString` at `0x14000e63c`
- `ole32!IIDFromString` at `0x14000e5e3`
- `ole32!IIDFromString` at `0x14000e63c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ef78`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ef82`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ef78`
- `OLEAUT32!__imp_SysFreeString` at `0x14000ef82`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000d7f4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000d7f4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000d800`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000d800`
- `SHLWAPI!PathFileExistsW` at `0x14000d4b5`
- `SHLWAPI!PathFileExistsW` at `0x14000d4b5`

## string_xrefs

- `0x14000ce02`: `Software\Microsoft\VSCommon\17.0\SQM`
- `0x14000cf88`: `\VsWerHandler.dll`
- `0x14000e5c0`: `ThisVersionDTECLSID`
- `0x14000e619`: `ThisVersionSolutionCLSID`
- `0x14000d75a`: `Community`
- `0x14000d246`: `shell32.dll`
- `0x14000d4a1`: `LegacyExtensions.enabled`
- `0x14000cfda`: `HRESULT %d returned when registering WER handler path "%s".`
- `0x14000d3bf`: `Cannot create app id object with suffix :%s.`
- `0x14000dcc6`: `Failure calling IsCompatibleNDPVersionInstalled.`
- `0x14000e20f`: `GetConfigurationTimestamp`
- `0x14000e496`: `Ignoring RANU command-line argument (deprecated)`
- `0x14000e8ca`: `SetupCommandLine`
- `0x14000e919`: `Returning E_FAIL due to InitProfilePaths failing.`
- `0x14000eba5`: `Returning 3002 error due to util_CallVSValidateCommands failing.`
- `0x14000ec1e`: `Returning 0x%08x error due to util_CallVSComposeMEF failing.`
- `0x14000daec`: `ConfigurationChanged`
- `0x14000db0f`: `ConfigurationChanged`
- `0x14000d183`: `Failed to read installation config info.`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CDevEnvAppId::Run(unsigned __int16 *a1, int a2)
{
  unsigned int v4; // r14d
  struct ATL::IAtlStringMgr *Instance; // rax
  WCHAR *v6; // r15
  struct ATL::IAtlStringMgr *v7; // rax
  wchar_t *v8; // r12
  struct ATL::IAtlStringMgr *v9; // rax
  unsigned __int16 *v10; // r13
  struct ATL::IAtlStringMgr *v11; // rax
  __int64 v12; // rdi
  int inited; // esi
  struct ATL::IAtlStringMgr *v14; // rax
  const unsigned __int16 *v15; // rbx
  DWORD ModuleFileNameW; // ebx
  int v17; // eax
  wchar_t *v18; // rbx
  __int64 v19; // rbx
  unsigned int v20; // ebx
  struct ATL::IAtlStringMgr *v21; // rax
  const unsigned __int16 *v22; // rbx
  const unsigned __int16 *v23; // r9
  int v24; // eax
  int v25; // r8d
  HANDLE StdHandle; // rbx
  int v27; // edx
  HANDLE CurrentProcess; // rax
  BOOL v29; // eax
  HANDLE v30; // rcx
  int IsolationConfig; // eax
  const unsigned __int16 *v32; // r9
  __int64 v33; // rcx
  const unsigned __int16 *v34; // r8
  struct InstallationConfigInfo *v35; // rcx
  DetourManager *v36; // rcx
  int *v37; // rax
  __int64 *v38; // r8
  volatile signed __int32 *v39; // rbx
  int *v40; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v43; // r14d
  unsigned int v44; // r14d
  int v45; // edx
  int v46; // r8d
  CAppIdImpl *v47; // rcx
  const WCHAR *v48; // rdx
  __int64 v49; // r8
  const wchar_t *v50; // rdx
  struct ATL::IAtlStringMgr *v51; // rax
  const unsigned __int16 *v52; // rbx
  const unsigned __int16 **IsolationInstallationId; // rax
  _QWORD *v54; // rdx
  _QWORD *LocalAppDataStoragePath; // rax
  _QWORD *v56; // rdx
  _QWORD *v57; // rdx
  __int64 ExcludedDirectoriesList; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rdx
  unsigned __int16 ***LegacyCompatDirectory; // rbx
  _QWORD *v62; // rax
  int v63; // r14d
  _QWORD *v64; // rdx
  _QWORD *v65; // rdx
  struct ATL::IAtlStringMgr *v66; // rax
  const unsigned __int16 *v67; // rbx
  int v68; // eax
  _DWORD *v69; // rbx
  const wchar_t *v70; // r14
  int v71; // ebx
  BSTR v72; // rax
  BSTR v73; // rcx
  UINT v74; // eax
  HKEY v75; // rcx
  CDevEnvAppId *v76; // rcx
  int v77; // r14d
  struct ATL::IAtlStringMgr *v78; // rax
  struct ATL::IAtlStringMgr *v79; // rax
  HKEY v80; // rcx
  const unsigned __int16 *v81; // rdx
  int v82; // eax
  struct ATL::IAtlStringMgr *v83; // rax
  HKEY v84; // r14
  const unsigned __int16 *v85; // rdx
  const unsigned __int16 *v86; // rdx
  const unsigned __int16 *v87; // rdx
  const unsigned __int16 *v88; // rdx
  int v89; // eax
  CDevEnvAppId *v90; // rbx
  int Branding; // eax
  struct IVsDetourManager *v92; // rdx
  int v93; // eax
  const unsigned __int16 *v94; // rdx
  const unsigned __int16 *v95; // r9
  const unsigned __int16 *v96; // rcx
  int v97; // eax
  HINSTANCE v98; // r14
  struct ATL::IAtlStringMgr *v99; // rax
  __int64 v100; // rcx
  _QWORD *v101; // rdx
  struct ATL::IAtlStringMgr *v102; // rax
  struct ATL::IAtlStringMgr *v103; // rax
  __int64 v104; // rdi
  struct ATL::IAtlStringMgr *v105; // rax
  const WCHAR *v106; // rbx
  volatile signed __int32 *v107; // rdx
  _QWORD *v108; // rdx
  _QWORD *v109; // rdx
  struct ATL::IAtlStringMgr *v110; // rax
  const unsigned __int16 *v111; // r14
  __int64 v112; // rdi
  volatile signed __int32 *v113; // rsi
  LPCWSTR v114; // rbx
  CDevEnvAppId *v115; // rcx
  CDevEnvAppId *v116; // rcx
  const unsigned __int16 **SetupResult; // rax
  char v118; // r14
  bool v119; // cf
  int ConfigurationTimestamp; // r14d
  struct ATL::IAtlStringMgr *v121; // rax
  const unsigned __int16 **v122; // rax
  int v123; // r14d
  struct ATL::IAtlStringMgr *v124; // rax
  struct CmdLineFiles *v125; // rbx
  struct CmdLineFiles *v126; // rcx
  unsigned __int16 *v127; // rax
  __int64 v128; // rdx
  struct tagCmdLineRegistryParms *v129; // rbx
  struct tagCmdLineRegistryParms *v130; // rcx
  struct CmdLineFiles *v131; // rax
  HKEY v132; // rcx
  unsigned int ClrStartupFlagsFromSettings; // eax
  struct ATL::IAtlStringMgr *v134; // rax
  struct _GUID *v135; // rdx
  struct _GUID *v136; // r8
  unsigned int v137; // r9d
  __int64 v138; // rax
  __int64 v139; // rcx
  CDevEnvAppId *v140; // rbx
  CDevEnvAppId *v141; // rax
  int v142; // eax
  int v143; // eax
  int v144; // eax
  HKEY v145; // rbx
  __int64 v146; // rax
  CAppIdExtImpl *v147; // rcx
  bool v148; // dl
  const struct _GUID *v149; // r8
  unsigned int v150; // r9d
  int v151; // r14d
  struct ATL::IAtlStringMgr *v152; // rax
  int v153; // eax
  char *v154; // rcx
  __int64 v155; // rdx
  CDevEnvAppId *v156; // rax
  const unsigned __int16 *v157; // rcx
  int v158; // eax
  CAppIdExtImpl *v159; // rcx
  HKEY v160; // rcx
  CDevEnvAppId *v161; // rbx
  bool v162; // si
  CAppIdExtImpl *v163; // rcx
  bool v164; // al
  HMODULE MSENV; // rax
  HMODULE v166; // rbx
  FARPROC v167; // rax
  signed int v168; // ecx
  signed int LastError; // eax
  struct ATL::IAtlStringMgr *v170; // rax
  struct ATL::IAtlStringMgr *v171; // rax
  const wchar_t *v172; // rdx
  struct ATL::IAtlStringMgr *v173; // rax
  __int64 v174; // rax
  unsigned int v175; // r8d
  wchar_t *v176; // rbx
  int v177; // eax
  unsigned int v178; // edx
  HINSTANCE v179; // rsi
  struct tagCmdLineRegistryParms *v180; // rbx
  struct tagCmdLineRegistryParms *v181; // rcx
  HMODULE v182; // rbx
  FARPROC v183; // rax
  CLockClr *v184; // rbx
  wchar_t *v185; // rdx
  int *v186; // rdx
  int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessb; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessc; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessd; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccesse; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessf; // [rsp+20h] [rbp-E0h]
  DWORD dwOptions; // [rsp+30h] [rbp-D0h]
  int v196; // [rsp+38h] [rbp-C8h]
  unsigned __int16 **v197; // [rsp+40h] [rbp-C0h]
  unsigned int v198; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v199; // [rsp+50h] [rbp-B0h]
  DWORD Type[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v201; // [rsp+88h] [rbp-78h]
  HANDLE TargetHandle; // [rsp+90h] [rbp-70h] BYREF
  bool v203[4]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v204; // [rsp+9Ch] [rbp-64h]
  char v205; // [rsp+A0h] [rbp-60h]
  int v206; // [rsp+A4h] [rbp-5Ch]
  DWORD cbData[2]; // [rsp+A8h] [rbp-58h] BYREF
  int *v208; // [rsp+B0h] [rbp-50h] BYREF
  BSTR bstr; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpText; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR pwszOutOfProcessCallbackDll; // [rsp+C8h] [rbp-38h] BYREF
  int v212; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v213; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v214[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v215; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v216; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *v217; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t *String1[2]; // [rsp+100h] [rbp+0h] BYREF
  int v219[4]; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v220; // [rsp+120h] [rbp+20h]
  int v221; // [rsp+128h] [rbp+28h]
  char v222; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v223; // [rsp+178h] [rbp+78h]
  int v224; // [rsp+17Ch] [rbp+7Ch]
  struct _SYSTEMTIME hKey; // [rsp+180h] [rbp+80h] BYREF
  __int64 v226; // [rsp+190h] [rbp+90h]
  wchar_t Source[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  v206 = 0;
  v204 = -1;
  LODWORD(lpText) = -1;
  cbData[0] = 0;
  v4 = 0;
  v201 = 0;
  v212 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v6 = (WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  pwszOutOfProcessCallbackDll = v6;
  v205 = 0;
  v7 = ATL::CAtlStringMgr::GetInstance();
  if ( !v7 )
    ATL::AtlThrowImpl(-2147467259);
  v8 = (wchar_t *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  v217 = v8;
  v9 = ATL::CAtlStringMgr::GetInstance();
  if ( !v9 )
    ATL::AtlThrowImpl(-2147467259);
  v10 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v9 + 24LL))(v9) + 24);
  v213 = v10;
  bstr = 0;
  String1[1] = 0;
  v11 = ATL::CAtlStringMgr::GetInstance();
  if ( !v11 )
    ATL::AtlThrowImpl(-2147467259);
  v12 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v11 + 24LL))(v11) + 24;
  *(_QWORD *)v214 = v12;
  v216 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v208,
    L"VisualStudio.17.0");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    String1,
    L"$Client$");
  _InterlockedExchange64((volatile __int64 *)&hInstance, 0);
  inited = util_InitMainParam(
             (struct MAINPARAM *)&CDevEnvAppId::ms_MainParam,
             a1,
             a2,
             L"Software\\Microsoft\\VSCommon\\17.0\\SQM");
  if ( inited < 0 )
  {
    v14 = ATL::CAtlStringMgr::GetInstance();
    if ( v14 )
    {
      _mm_lfence();
      *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        Type,
        L"Failure calling %s.",
        L"util_InitMainParam");
      v15 = *(const unsigned __int16 **)Type;
      ActivityLog::LogEntryHr(
        (ActivityLog *)1,
        (int)L"VisualStudio",
        *(const unsigned __int16 **)Type,
        (const unsigned __int16 *)(unsigned int)inited,
        dwDesiredAccess);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      }
      goto LABEL_248;
    }
LABEL_493:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( ((1 - *((_DWORD *)v6 - 2)) | (*((_DWORD *)v6 - 3) - 260)) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&pwszOutOfProcessCallbackDll, 260);
    v6 = (WCHAR *)pwszOutOfProcessCallbackDll;
  }
  ModuleFileNameW = GetModuleFileNameW(0, v6, 0x104u);
  v17 = wcsnlen(v6, *((int *)v6 - 3));
  if ( v17 < 0 || v17 > *((_DWORD *)v6 - 3) )
    goto LABEL_483;
  *((_DWORD *)v6 - 4) = v17;
  v6[v17] = 0;
  if ( ModuleFileNameW )
  {
    v18 = wcsrchr(v6, 0x5Cu);
    if ( v18 )
    {
      v19 = v18 - v6;
      if ( (_DWORD)v19 != -1 )
      {
        if ( (int)v19 < 0 )
          goto LABEL_483;
        if ( ((1 - *((_DWORD *)v6 - 2)) | (*((_DWORD *)v6 - 3) - (int)v19)) < 0 )
        {
          _mm_lfence();
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&pwszOutOfProcessCallbackDll, (unsigned int)v19);
          v6 = (WCHAR *)pwszOutOfProcessCallbackDll;
        }
        if ( (int)v19 > *((_DWORD *)v6 - 3) )
          goto LABEL_483;
        *((_DWORD *)v6 - 4) = v19;
        v6[(int)v19] = 0;
        ATL::CSimpleStringT<unsigned short,0>::Append(&pwszOutOfProcessCallbackDll, L"\\VsWerHandler.dll", 17);
        v6 = (WCHAR *)pwszOutOfProcessCallbackDll;
        v20 = WerRegisterRuntimeExceptionModule(pwszOutOfProcessCallbackDll, 0);
        if ( v20 )
        {
          v21 = ATL::CAtlStringMgr::GetInstance();
          if ( !v21 )
            goto LABEL_493;
          *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v21 + 24LL))(v21) + 24;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            Type,
            L"HRESULT %d returned when registering WER handler path \"%s\".",
            v20,
            v6);
          v22 = *(const unsigned __int16 **)Type;
          ActivityLog::LogEntry((ActivityLog *)2, (int)L"VisualStudio", *(const unsigned __int16 **)Type, v23);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
          }
        }
        else
        {
          v205 = 1;
        }
      }
    }
  }
  v24 = util_ParseCmdLineParms(
          L"Software\\Microsoft\\VisualStudio\\17.0",
          qword_14009CD90,
          (struct tagCmdLineParms *)&CDevEnvAppId::ms_CmdLineParms,
          &Block,
          0,
          &CDevEnvAppId::ms_pszInvalidSwitch);
  Type[0] = v24;
  v25 = 0;
  if ( v24 >= 0 )
  {
    cbData[0] = util_CheckMainParam((struct MAINPARAM *)&CDevEnvAppId::ms_MainParam);
    if ( (cbData[0] & 0x80000000) == 0 )
      goto LABEL_30;
  }
  else if ( v24 == -2147024809 )
  {
    goto LABEL_30;
  }
  dword_14009CDD8 = 1;
  CDevEnvAppId::ms_fInvalidCmdLine = 1;
LABEL_30:
  if ( dword_14009CDDC != v25 )
    DebugBreak();
  StdHandle = GetStdHandle(0xFFFFFFF5);
  if ( (unsigned int)util_FConsoleHandle(StdHandle) )
  {
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, StdHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v29 = SetStdHandle(0xFFFFFFF5, TargetHandle);
      v30 = TargetHandle;
      if ( v29 )
        v30 = StdHandle;
      CloseHandle(v30);
    }
  }
  if ( !lpSubKey && !CAppIdExtImpl::ms_wszRegistrySuffix )
  {
    ReadRootSuffix(Source, v27);
    if ( Source[0] )
    {
      wcsncpy_s(&Destination, 0x104u, Source, 0x103u);
      CAppIdExtImpl::ms_wszRegistrySuffix = &Destination;
    }
  }
  IsolationConfig = ReadIsolationConfig((struct IsolationConfigInfo *)&CAppIdExtImpl::m_isolationConfigInfo);
  v33 = 3;
  if ( IsolationConfig >= 0 )
  {
    ActivityLog::LogEntry((ActivityLog *)3, (int)L"VisualStudio", L"Running in isolation mode.", v32);
    IsolationConfig = ReadInstallationConfig(v35);
    if ( IsolationConfig >= 0 )
      goto LABEL_46;
    v34 = L"Failed to read installation config info.";
    v33 = 2;
  }
  else
  {
    v34 = L"Running in traditional mode.";
  }
  _mm_lfence();
  ActivityLog::LogEntryHr(
    (ActivityLog *)v33,
    (int)L"VisualStudio",
    v34,
    (const unsigned __int16 *)(unsigned int)IsolationConfig,
    dwDesiredAccessa);
LABEL_46:
  if ( !CAppIdExtImpl::m_isolationConfigInfo )
    goto LABEL_54;
  v37 = v208;
  if ( ((1 - *(v208 - 2)) | *(v208 - 3)) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v208, 0);
    v37 = v208;
  }
  if ( *(v37 - 3) < 0 )
LABEL_483:
    ATL::AtlThrowImpl(-2147024809);
  *(v37 - 4) = 0;
  *(_WORD *)v208 = 0;
  CAppIdExtImpl::GetIsolationInstallationId(&TargetHandle);
  v38 = &qword_14009D550;
  if ( (unsigned __int64)qword_14009D568 > 7 )
    v38 = (__int64 *)qword_14009D550;
  v39 = (volatile signed __int32 *)TargetHandle;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v208,
    L"%s%s",
    v38,
    TargetHandle);
  if ( _InterlockedExchangeAdd(v39 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v39 - 3) + 8LL))(*((_QWORD *)v39 - 3));
  }
LABEL_54:
  v40 = v208;
  if ( byte_14009DBE0 )
  {
    ProcAddress = (FARPROC)qword_14009DBD8;
  }
  else
  {
    LibraryW = LoadLibraryW(L"shell32.dll");
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SetCurrentProcessExplicitAppUserModelID");
      qword_14009DBD8 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_14009DBD8;
    }
    byte_14009DBE0 = 1;
  }
  if ( ProcAddress )
    ((void (__fastcall *)(int *))ProcAddress)(v40);
  if ( CDevEnvAppId::ms_fResetUserData || (v43 = 1, CDevEnvAppId::ms_fUpdateConfiguration) )
    v43 = 257;
  if ( CDevEnvAppId::ms_fResetUserData )
    v43 |= 0x200u;
  v44 = v43 | 0x11800;
  if ( CDevEnvAppId::ms_fSafeModeRequested )
    v44 |= 0x20000u;
  *(_DWORD *)&hKey.wYear = 1;
  if ( (int)DetourManager::SetupDetours(v36) < 0 )
    goto LABEL_246;
  cbData[0] = 1204;
  LODWORD(TargetHandle) = 3000;
  inited = AtlCreateFreeThreadedInstanceInit4<CDevEnvAppId,int,unsigned short const (&)[13],_GUID const &,int>(
             (unsigned int)&TargetHandle,
             v45,
             v46,
             (unsigned int)cbData,
             dwDesiredAccessa,
             (__int64)&v216);
  if ( inited < 0 )
    goto LABEL_247;
  v216 = 0;
  if ( CAppIdExtImpl::m_isolationConfigInfo )
  {
    v44 |= 0x2000u;
    *(_DWORD *)&hKey.wYear = byte_14009D1DA != 0 ? 5 : 3;
    CAppIdImpl::AddDefaultIsolatedInstanceKeyFilters(v47);
  }
  v48 = lpSubKey;
  if ( lpSubKey )
  {
    v49 = -1;
    do
      ++v49;
    while ( lpSubKey[v49] );
  }
  else
  {
    v48 = L"Software\\Microsoft\\VisualStudio\\17.0";
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v213, v48);
  v50 = CAppIdExtImpl::ms_wszRegistrySuffix;
  if ( !CAppIdExtImpl::ms_wszRegistrySuffix )
    v50 = &WindowName;
  if ( !v50 )
    goto LABEL_493;
  if ( !_wcsicmp(String1[0], v50) )
  {
    v51 = ATL::CAtlStringMgr::GetInstance();
    if ( !v51 )
      goto LABEL_493;
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v51 + 24LL))(v51) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      Type,
      L"Cannot create app id object with suffix :%s.",
      CAppIdExtImpl::ms_wszRegistrySuffix);
    v52 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)1,
      dwDesiredAccessb);
    inited = 1;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v52 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v52 - 3) + 8LL))(*((_QWORD *)v52 - 3));
    }
    v10 = v213;
LABEL_247:
    v4 = v201;
    goto LABEL_248;
  }
  IsolationInstallationId = (const unsigned __int16 **)CAppIdExtImpl::GetIsolationInstallationId(&TargetHandle);
  v10 = v213;
  util_FormRootKeyPath(v213, *IsolationInstallationId, CAppIdExtImpl::ms_wszRegistrySuffix, &bstr);
  v54 = (char *)TargetHandle - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)TargetHandle - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 8LL))(*v54);
  }
  TargetHandle = 0;
  LocalAppDataStoragePath = (_QWORD *)CAppIdExtImpl::GetLocalAppDataStoragePath(cbData, bstr);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &TargetHandle,
    *LocalAppDataStoragePath);
  v56 = (_QWORD *)(*(_QWORD *)cbData - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)cbData - 24LL + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 8LL))(*v56);
  }
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
    &TargetHandle,
    L"LegacyExtensions.enabled");
  v203[0] = PathFileExistsW((LPCWSTR)TargetHandle);
  v57 = (char *)TargetHandle - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)TargetHandle - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v57 + 8LL))(*v57);
  }
  ExcludedDirectoriesList = CAppIdExtImpl::GetExcludedDirectoriesList(&TargetHandle, bstr);
  ATL::CSimpleStringT<unsigned short,0>::operator=(v214, ExcludedDirectoriesList);
  v60 = (char *)TargetHandle - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)TargetHandle - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v60 + 8LL))(*v60);
  }
  LegacyCompatDirectory = (unsigned __int16 ***)CAppIdExtImpl::GetLegacyCompatDirectory(v59, cbData);
  v62 = (_QWORD *)CAppIdExtImpl::GetIsolationInstallationId(&TargetHandle);
  v199 = (unsigned __int16 *)CDevEnvAppId::ms_pTheAppId;
  v12 = *(_QWORD *)v214;
  v198 = v214[0];
  v197 = *LegacyCompatDirectory;
  LOBYTE(v196) = v203[0];
  dwOptions = *(_DWORD *)&hKey.wYear;
  dwDesiredAccessc = 0;
  v63 = CDetouringPkgDefManagement::InitializeAppID(
          &CDevEnvAppId::ms_PkgDefManagement,
          CAppIdExtImpl::ms_wszRegistrySuffix,
          *v62,
          v44);
  v64 = (char *)TargetHandle - 24;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)TargetHandle - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v64 + 8LL))(*v64);
  }
  v65 = (_QWORD *)(*(_QWORD *)cbData - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)cbData - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v65 + 8LL))(*v65);
  }
  if ( v63 < 0 )
  {
    v66 = ATL::CAtlStringMgr::GetInstance();
    if ( !v66 )
      goto LABEL_493;
    _mm_lfence();
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v66 + 24LL))(v66) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      Type,
      L"Failure calling %s.",
      L"InitializeAppID");
    v67 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)(unsigned int)v63,
      0);
    inited = v63;
    goto LABEL_101;
  }
  Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetUserSettingsRoot(&CDevEnvAppId::ms_PkgDefManagement, &v217, 0);
  v8 = v217;
  wcscpy_s(&word_14009DC20, 0x400u, v217);
  lpSubKey = &word_14009DC20;
  v68 = CDevEnvAppId::ms_fAllowDuringSetup;
  if ( !CDevEnvAppId::ms_fAllowDuringSetup )
  {
    if ( !dword_14009CE10
      && !dword_14009CDF0
      && !CDevEnvAppId::ms_fUpdateConfiguration
      && !CDevEnvAppId::ms_fDeferUpdateConfiguration )
    {
      if ( (*(unsigned __int8 (__fastcall **)(CDevEnvAppId *))(*(_QWORD *)CDevEnvAppId::ms_pTheAppId + 104LL))(CDevEnvAppId::ms_pTheAppId) )
      {
        v4 = 3106;
LABEL_110:
        inited = -2147467259;
        v204 = 0;
        goto LABEL_248;
      }
      v68 = CDevEnvAppId::ms_fAllowDuringSetup;
    }
    if ( !v68
      && !dword_14009CE10
      && !dword_14009CDF0
      && !CDevEnvAppId::ms_fDeferUpdateConfiguration
      && (*(unsigned __int8 (__fastcall **)(CDevEnvAppId *))(*(_QWORD *)CDevEnvAppId::ms_pTheAppId + 112LL))(CDevEnvAppId::ms_pTheAppId) )
    {
      v4 = 3109;
      goto LABEL_110;
    }
  }
  TargetHandle = (char *)CDevEnvAppId::ms_pTheAppId + 1692;
  v69 = (_DWORD *)((char *)CDevEnvAppId::ms_pTheAppId + 1688);
  if ( CDevEnvAppId::ms_pTheAppId == (CDevEnvAppId *)-1688LL )
    goto LABEL_128;
  v70 = lpValue;
  if ( !wcscmp_0(lpValue, L"Community") )
  {
    *v69 = 1800;
LABEL_128:
    v71 = 0;
    goto LABEL_129;
  }
  if ( !wcscmp_0(v70, L"Professional") )
  {
    *v69 = 2000;
    goto LABEL_128;
  }
  if ( wcscmp_0(v70, L"Enterprise") )
  {
    if ( !wcscmp_0(v70, L"V3|UNKNOWN") )
      *v69 = 1400;
    goto LABEL_128;
  }
  *v69 = 3000;
  v71 = 0;
  if ( TargetHandle )
    *(_DWORD *)TargetHandle = 392;
LABEL_129:
  CAppIdExtImpl::SetProcessEnvironmentVariables();
  v72 = bstr;
  if ( bstr )
  {
    v74 = SysStringByteLen(bstr);
    v73 = SysAllocStringByteLen((LPCSTR)bstr, v74);
    v72 = bstr;
  }
  else
  {
    v73 = 0;
  }
  TargetHandle = v73;
  if ( v72 && !v73 )
    ATL::AtlThrowImpl(-2147024882);
  v75 = ::hKey;
  if ( *(_QWORD *)(qword_14009D1C0 + 232) )
    v75 = *(HKEY *)(qword_14009D1C0 + 232);
  CAppIdExtImpl::SetProcessDpiAwarenessMode(v75, &TargetHandle);
  v77 = util_OleInitialize(lpSubKey);
  if ( v77 < 0 )
  {
    v78 = ATL::CAtlStringMgr::GetInstance();
    if ( !v78 )
      goto LABEL_493;
    _mm_lfence();
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v78 + 24LL))(v78) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      Type,
      L"Failure calling %s.",
      L"util_OleInitialize");
    v67 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)(unsigned int)v77,
      0);
    inited = v77;
    goto LABEL_101;
  }
  v212 = 1;
  if ( CDevEnvAppId::ms_fClearCache )
  {
    v79 = ATL::CAtlStringMgr::GetInstance();
    if ( !v79 )
      goto LABEL_493;
    TargetHandle = (HANDLE)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v79 + 24LL))(v79) + 24);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&TargetHandle, &qword_14009D250);
    v80 = ::hKey;
    if ( *(_QWORD *)(qword_14009D1C0 + 232) )
      v80 = *(HKEY *)(qword_14009D1C0 + 232);
    v67 = (const unsigned __int16 *)TargetHandle;
    CAppIdImpl::WriteClearCacheTimestamp(v80, lpSubKey, (const unsigned __int16 *)TargetHandle);
    if ( !dword_14009CDF0 )
    {
      v204 = 0;
      goto LABEL_101;
    }
    v81 = v67 - 12;
    v82 = _InterlockedExchangeAdd((volatile signed __int32 *)v67 - 2, 0xFFFFFFFF);
    v71 = 0;
    if ( v82 <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v81 + 8LL))(*(_QWORD *)v81);
    }
  }
  if ( dword_14009CE00 || dword_14009CE10 )
  {
LABEL_172:
    if ( dword_14009CDF0 )
      goto LABEL_177;
    goto LABEL_173;
  }
  if ( dword_14009CDF0 )
    goto LABEL_177;
  if ( !dword_14009CDA0
    && !dword_14009CDB0
    && !dword_14009CDD8
    && !dword_14009CDA4
    && !dword_14009CDF8
    && !dword_14009CDAC
    && !dword_14009CDA8
    && !dword_14009CDC8
    && !dword_14009CDCC
    && !CDevEnvAppId::ms_fCommand
    && !CDevEnvAppId::ms_fNoSplash
    && !dword_14009CED4
    && !CDevEnvAppId::ms_fDiffSwitchOnCommandLine
    && !dword_14009CED0
    && dword_14009CD68
    && !CDevEnvAppId::ms_fResetUserData )
  {
    if ( CDevEnvAppId::ms_fUpdateConfiguration || CDevEnvAppId::ms_fDeferUpdateConfiguration )
      goto LABEL_177;
    if ( dword_14009CED8 || CDevEnvAppId::ms_fValidateCtm || dword_14009CEE8 )
      goto LABEL_197;
    CDevEnvAppId::DisplaySplashScreen(v76, (struct MAINPARAM *)&CDevEnvAppId::ms_MainParam);
    goto LABEL_172;
  }
LABEL_173:
  if ( !CDevEnvAppId::ms_fUpdateConfiguration
    && !CDevEnvAppId::ms_fDeferUpdateConfiguration
    && !dword_14009CED0
    && !CDevEnvAppId::ms_fResetUserData )
  {
    goto LABEL_197;
  }
LABEL_177:
  v83 = ATL::CAtlStringMgr::GetInstance();
  if ( !v83 )
    goto LABEL_493;
  TargetHandle = (HANDLE)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v83 + 24LL))(v83) + 24);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&TargetHandle, &qword_14009D250);
  v84 = ::hKey;
  if ( *(_QWORD *)(qword_14009D1C0 + 232) )
    v84 = *(HKEY *)(qword_14009D1C0 + 232);
  v67 = (const unsigned __int16 *)TargetHandle;
  if ( TargetHandle )
  {
    if ( (int)util_WriteConfigurationChangedFile((const unsigned __int16 *)TargetHandle) < 0 )
    {
      util_WriteTimeStampToRegistry(v84, &word_14009DC20, L"ConfigurationChanged", 0);
      util_WriteConfigurationChangedReasonToRegistry(v84, v86);
      goto LABEL_185;
    }
  }
  else
  {
    util_WriteTimeStampToRegistry(v84, &word_14009DC20, L"ConfigurationChanged", 1);
  }
  util_WriteConfigurationChangedReasonToRegistry(v84, v85);
  util_WriteConfigurationChangedIndicatorToRegistry(v84, v87);
LABEL_185:
  if ( dword_14009CED0 || CDevEnvAppId::ms_fDeferUpdateConfiguration )
  {
    v204 = 0;
    goto LABEL_101;
  }
  v88 = v67 - 12;
  v89 = _InterlockedExchangeAdd((volatile signed __int32 *)v67 - 2, 0xFFFFFFFF);
  v71 = 0;
  if ( v89 <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v88 + 8LL))(*(_QWORD *)v88);
  }
  if ( dword_14009CDF0 )
  {
    TargetHandle = 0;
    v90 = CDevEnvAppId::ms_pTheAppId;
    if ( ((*(__int64 (__fastcall **)(CDevEnvAppId *))(*(_QWORD *)CDevEnvAppId::ms_pTheAppId + 64LL))(CDevEnvAppId::ms_pTheAppId)
        & 0x10) != 0 )
    {
      Branding = CAppIdExtImpl::GetBrandingData<BrandingTheme<VSFILEASSOCIATIONTHEME>>(v90, &TargetHandle);
      v71 = 0;
      if ( Branding >= 0
        && (*(int (__fastcall **)(HANDLE, struct _SYSTEMTIME *))(*(_QWORD *)TargetHandle + 24LL))(TargetHandle, &hKey) >= 0 )
      {
        InitializeCapabilities(
          lpSubKey,
          **(const unsigned __int16 ***)&hKey.wYear,
          *(_DWORD *)(*(_QWORD *)&hKey.wYear + 8LL));
      }
    }
    else
    {
      v71 = 0;
    }
    if ( TargetHandle )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
  }
LABEL_197:
  v92 = (CDevEnvAppId *)((char *)CDevEnvAppId::ms_pTheAppId + 24);
  if ( !CDevEnvAppId::ms_pTheAppId )
    v92 = 0;
  v93 = CDetouringPkgDefManagement::FinishInitialize(
          (CDetouringPkgDefManagement *)&CDevEnvAppId::ms_PkgDefManagement,
          v92,
          (enum PkgDefMergeReason *)&v215);
  inited = v93;
  if ( v93 < 0 )
  {
    _mm_lfence();
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      L"Failure calling FinishInitialize.",
      (const unsigned __int16 *)(unsigned int)v93,
      0);
    v4 = (inited != -2147024891) + 3107;
    goto LABEL_248;
  }
  v96 = (const unsigned __int16 *)v215;
  if ( v215 )
    qword_14009CEF0 = GetExplanationForPkgDefMerge();
  v97 = CDevEnvAppId::ms_fAllowDuringSetup;
  if ( CDevEnvAppId::ms_fAllowDuringSetup )
    goto LABEL_282;
  if ( !dword_14009CE10
    && !dword_14009CDF0
    && !CDevEnvAppId::ms_fUpdateConfiguration
    && !CDevEnvAppId::ms_fDeferUpdateConfiguration )
  {
    inited = IsCompatibleNDPVersionInstalled(v96);
    cbData[0] = inited;
    if ( inited < 0 )
    {
      _mm_lfence();
      if ( CDevEnvAppId::ms_pTheAppId )
        CSplash::DestroySplashScreen((CDevEnvAppId *)((char *)CDevEnvAppId::ms_pTheAppId + 1528));
      ActivityLog::LogEntryHr(
        (ActivityLog *)1,
        (int)L"VisualStudio",
        L"Failure calling IsCompatibleNDPVersionInstalled.",
        (const unsigned __int16 *)(unsigned int)inited,
        0);
      (*(void (__fastcall **)(CDevEnvAppId *, _QWORD, _QWORD))(*(_QWORD *)CDevEnvAppId::ms_pTheAppId + 48LL))(
        CDevEnvAppId::ms_pTheAppId,
        0,
        0);
      v98 = hInstance;
      if ( !hInstance )
      {
        inited = -2147024809;
LABEL_235:
        v110 = ATL::CAtlStringMgr::GetInstance();
        if ( !v110 )
          goto LABEL_494;
        _mm_lfence();
        *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v110 + 24LL))(v110) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          Type,
          L"Failure calling %s.",
          L"ShowNDPVersionError");
        v67 = *(const unsigned __int16 **)Type;
        ActivityLog::LogEntryHr(
          (ActivityLog *)1,
          (int)L"VisualStudio",
          *(const unsigned __int16 **)Type,
          (const unsigned __int16 *)(unsigned int)inited,
          dwDesiredAccessd);
        goto LABEL_101;
      }
      v99 = ATL::CAtlStringMgr::GetInstance();
      if ( !v99 )
        goto LABEL_494;
      *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v99 + 24LL))(v99) + 24;
      inited = anonymous_namespace_::GetRequiredVersion(v100, Type);
      if ( inited < 0 )
      {
        v101 = (_QWORD *)(*(_QWORD *)Type - 24LL);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Type - 24LL + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v101 + 8LL))(*v101);
        }
        goto LABEL_235;
      }
      v102 = ATL::CAtlStringMgr::GetInstance();
      if ( !v102 )
        ATL::AtlThrowImpl(-2147467259);
      TargetHandle = (HANDLE)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v102 + 24LL))(v102)
                            + 24);
      v103 = ATL::CAtlStringMgr::GetInstance();
      if ( !v103 )
        ATL::AtlThrowImpl(-2147467259);
      v104 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v103 + 24LL))(v103) + 24;
      *(_QWORD *)&hKey.wYear = v104;
      v105 = ATL::CAtlStringMgr::GetInstance();
      if ( !v105 )
        ATL::AtlThrowImpl(-2147467259);
      v106 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v105 + 24LL))(v105) + 24);
      lpText = v106;
      ATL::CSimpleStringT<unsigned short,0>::Empty(&TargetHandle);
      if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                            &TargetHandle,
                            v98,
                            3000) )
      {
        inited = -2147023728;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v106 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v106 - 3) + 8LL))(*((_QWORD *)v106 - 3));
        }
        v107 = (volatile signed __int32 *)(v104 - 24);
LABEL_228:
        if ( _InterlockedExchangeAdd(v107 + 4, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v107 + 8LL))(*(_QWORD *)v107);
        }
        v108 = (char *)TargetHandle - 24;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)TargetHandle - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v108 + 8LL))(*v108);
        }
        v109 = (_QWORD *)(*(_QWORD *)Type - 24LL);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Type - 24LL + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v109 + 8LL))(*v109);
        }
        v12 = *(_QWORD *)v214;
        goto LABEL_235;
      }
      ATL::CSimpleStringT<unsigned short,0>::Empty(&hKey);
      if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                            &hKey,
                            v98,
                            28688) )
      {
        inited = -2147023728;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v106 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v106 - 3) + 8LL))(*((_QWORD *)v106 - 3));
        }
        v107 = (volatile signed __int32 *)(*(_QWORD *)&hKey.wYear - 24LL);
        goto LABEL_228;
      }
      v111 = *(const unsigned __int16 **)Type;
      v112 = *(_QWORD *)&hKey.wYear;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpText,
        *(_QWORD *)&hKey.wYear,
        *(_QWORD *)Type);
      v113 = (volatile signed __int32 *)TargetHandle;
      v114 = lpText;
      MessageBoxW(0, lpText, (LPCWSTR)TargetHandle, 0x10u);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v114 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v114 - 3) + 8LL))(*((_QWORD *)v114 - 3));
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v112 - 24 + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v112 - 24) + 8LL))(*(_QWORD *)(v112 - 24));
      }
      if ( _InterlockedExchangeAdd(v113 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v113 - 3) + 8LL))(*((_QWORD *)v113 - 3));
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v111 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v111 - 3) + 8LL))(*((_QWORD *)v111 - 3));
      }
      v204 = 0;
      v12 = *(_QWORD *)v214;
LABEL_246:
      inited = cbData[0];
      goto LABEL_247;
    }
    v97 = CDevEnvAppId::ms_fAllowDuringSetup;
  }
  if ( v97
    || dword_14009CE10
    || dword_14009CDF0
    || CDevEnvAppId::ms_fUpdateConfiguration
    || CDevEnvAppId::ms_fDeferUpdateConfiguration )
  {
LABEL_282:
    v118 = v206;
  }
  else
  {
    v116 = CDevEnvAppId::ms_pTheAppId;
    if ( CDevEnvAppId::ms_pTheAppId
      && *((_DWORD *)CDevEnvAppId::ms_pTheAppId + 422) == 1000
      && *((_DWORD *)CDevEnvAppId::ms_pTheAppId + 423) == 16 )
    {
      v118 = v206;
      goto LABEL_286;
    }
    SetupResult = (const unsigned __int16 **)CAppIdExtImpl::GetSetupResult(&hKey);
    v118 = 1;
    v206 = 1;
    v94 = *SetupResult;
    if ( !*SetupResult
      || (CAppIdExtImpl::m_installationConfigInfo & (unsigned __int8)-(CAppIdExtImpl::m_isolationConfigInfo != 0)) == 0 )
    {
      goto LABEL_281;
    }
    TargetHandle = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &TargetHandle,
      v94);
    v119 = *(_WORD *)TargetHandle < 0x31u;
    if ( *(_WORD *)TargetHandle != 49 || (v119 = 0, *((_WORD *)TargetHandle + 1)) )
      v71 = v119 ? -1 : 1;
    v94 = (const unsigned __int16 *)((char *)TargetHandle - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)TargetHandle - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v94 + 8LL))(*(_QWORD *)v94);
    }
    if ( !v71 )
      LOBYTE(v71) = 0;
    else
LABEL_281:
      LOBYTE(v71) = 1;
  }
  v116 = CDevEnvAppId::ms_pTheAppId;
LABEL_286:
  if ( (v118 & 1) != 0 )
  {
    v94 = (const unsigned __int16 *)(*(_QWORD *)&hKey.wYear - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&hKey.wYear - 24LL + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v94 + 8LL))(*(_QWORD *)v94);
    }
    v116 = CDevEnvAppId::ms_pTheAppId;
  }
  if ( (_BYTE)v71 )
  {
    if ( v116 )
    {
      CSplash::DestroySplashScreen((CDevEnvAppId *)((char *)v116 + 1528));
      v116 = CDevEnvAppId::ms_pTheAppId;
    }
    (*(void (__fastcall **)(CDevEnvAppId *, _QWORD, _QWORD))(*(_QWORD *)v116 + 48LL))(v116, 0, 0);
    ConfigurationTimestamp = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetConfigurationTimestamp(
                               (Microsoft::VisualStudio::PkgDef::CPkgDefManagement *)&CDevEnvAppId::ms_PkgDefManagement,
                               &hKey);
    if ( ConfigurationTimestamp < 0 )
    {
      v121 = ATL::CAtlStringMgr::GetInstance();
      if ( v121 )
      {
        _mm_lfence();
        *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v121 + 24LL))(v121) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          Type,
          L"Failure calling %s.",
          L"GetConfigurationTimestamp");
        v67 = *(const unsigned __int16 **)Type;
        ActivityLog::LogEntryHr(
          (ActivityLog *)1,
          (int)L"VisualStudio",
          *(const unsigned __int16 **)Type,
          (const unsigned __int16 *)(unsigned int)ConfigurationTimestamp,
          0);
        inited = ConfigurationTimestamp;
        goto LABEL_101;
      }
LABEL_492:
      ATL::AtlThrowImpl(-2147467259);
    }
    v122 = (const unsigned __int16 **)CAppIdExtImpl::GetSetupResult(&TargetHandle);
    v123 = ShowSetupError(
             CAppIdExtImpl::m_installationConfigInfo & (unsigned __int8)-(CAppIdExtImpl::m_isolationConfigInfo != 0),
             *v122,
             (const unsigned __int16 *)v203,
             &hKey,
             hInstance,
             v203);
    v94 = (const unsigned __int16 *)((char *)TargetHandle - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)TargetHandle - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v94 + 8LL))(*(_QWORD *)v94);
    }
    if ( v123 < 0 )
    {
      v124 = ATL::CAtlStringMgr::GetInstance();
      if ( !v124 )
        goto LABEL_492;
      _mm_lfence();
      *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v124 + 24LL))(v124) + 24;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        Type,
        L"Failure calling %s.",
        L"ShowSetupError");
      v67 = *(const unsigned __int16 **)Type;
      ActivityLog::LogEntryHr(
        (ActivityLog *)1,
        (int)L"VisualStudio",
        *(const unsigned __int16 **)Type,
        (const unsigned __int16 *)(unsigned int)v123,
        dwDesiredAccessc);
      inited = v123;
LABEL_101:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v67 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v67 - 3) + 8LL))(*((_QWORD *)v67 - 3));
      }
      goto LABEL_247;
    }
    if ( !v203[0] )
    {
LABEL_302:
      v204 = 0;
      goto LABEL_247;
    }
  }
  if ( Type[0] == -2147024809 )
  {
    v125 = Block;
    if ( Block )
    {
      v126 = Block;
      do
      {
        v125 = (struct CmdLineFiles *)*((_QWORD *)v125 + 5);
        free_0(v126);
        v126 = v125;
      }
      while ( v125 );
      Block = 0;
    }
    v127 = qword_14009CD90;
    if ( qword_14009CD90 )
    {
      v128 = -1;
      do
        ++v128;
      while ( lpData[v128] );
      wcscpy_s_0(qword_14009CD90, v128 + 1, lpData);
      v127 = qword_14009CD90;
    }
    CDevEnvAppId::ms_pszInvalidSwitch = 0;
    v129 = CDevEnvAppId::ms_pCmdLineRegistryParms;
    v130 = CDevEnvAppId::ms_pCmdLineRegistryParms;
    if ( CDevEnvAppId::ms_pCmdLineRegistryParms )
    {
      do
      {
        v129 = (struct tagCmdLineRegistryParms *)*((_QWORD *)v129 + 2);
        free_0(v130);
        v130 = v129;
      }
      while ( v129 );
      v127 = qword_14009CD90;
    }
    CDevEnvAppId::ms_pCmdLineRegistryParms = 0;
    if ( (int)util_ParseCmdLineParms(
                lpSubKey,
                v127,
                (struct tagCmdLineParms *)&CDevEnvAppId::ms_CmdLineParms,
                &Block,
                &CDevEnvAppId::ms_pCmdLineRegistryParms,
                &CDevEnvAppId::ms_pszInvalidSwitch) < 0 )
    {
      CDevEnvAppId::ms_fInvalidCmdLine = 1;
      dword_14009CDD8 = 1;
    }
    lpSubKey = &word_14009DC20;
    v131 = Block;
    if ( Block )
      goto LABEL_338;
    if ( dword_14009CDA0
      || dword_14009CDA4
      || dword_14009CDA8
      || dword_14009CDAC
      || dword_14009CDB0
      || dword_14009CED4
      || dword_14009CDB4
      || dword_14009CDC8
      || dword_14009CDCC )
    {
LABEL_327:
      CDevEnvAppId::ms_fInvalidCmdLine = 1;
      dword_14009CDD8 = 1;
    }
    else
    {
      while ( v131 )
      {
LABEL_338:
        if ( !*(_QWORD *)v131 )
          goto LABEL_327;
        v131 = (struct CmdLineFiles *)*((_QWORD *)v131 + 5);
      }
    }
  }
  if ( CDevEnvAppId::ms_fRANU && dword_14009CEBC )
    ActivityLog::LogEntry(
      (ActivityLog *)2,
      (int)L"VisualStudio",
      L"Ignoring RANU command-line argument (deprecated)",
      v95);
  if ( !CDevEnvAppId::ms_fNoVSW )
    VsWatsonSetUnhandledExceptionFilter(lpSubKey, v94);
  v132 = ::hKey;
  if ( *(_QWORD *)(qword_14009D1C0 + 232) )
    v132 = *(HKEY *)(qword_14009D1C0 + 232);
  ClrStartupFlagsFromSettings = GetClrStartupFlagsFromSettings(v132, v8);
  inited = VsHookCLRLoading(lpSubKey, ClrStartupFlagsFromSettings);
  if ( inited < 0 )
  {
    v134 = ATL::CAtlStringMgr::GetInstance();
    if ( !v134 )
      goto LABEL_494;
    _mm_lfence();
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v134 + 24LL))(v134) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      Type,
      L"Failure calling %s.",
      L"VsHookCLRLoading");
    v67 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)(unsigned int)inited,
      dwDesiredAccessc);
    goto LABEL_101;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, (PHKEY)&TargetHandle) )
  {
    iid = GUID_NULL;
    stru_14009CE58 = GUID_NULL;
  }
  else
  {
    cbData[0] = 520;
    if ( RegQueryValueExW((HKEY)TargetHandle, L"ThisVersionDTECLSID", 0, Type, (LPBYTE)Source, cbData) )
      iid = GUID_NULL;
    else
      IIDFromString(Source, &iid);
    cbData[0] = 520;
    if ( RegQueryValueExW((HKEY)TargetHandle, L"ThisVersionSolutionCLSID", 0, Type, (LPBYTE)Source, cbData) )
      stru_14009CE58 = GUID_NULL;
    else
      IIDFromString(Source, &stru_14009CE58);
    RegCloseKey((HKEY)TargetHandle);
  }
  if ( dword_14009CED4 )
  {
    v138 = *(_QWORD *)&iid.Data1;
    v139 = *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&iid.Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    {
      v135 = *(struct _GUID **)iid.Data4;
      v136 = *(struct _GUID **)GUID_NULL.Data4;
      if ( *(_QWORD *)iid.Data4 == *(_QWORD *)GUID_NULL.Data4 )
        goto LABEL_357;
    }
    inited = util_TryToEditFilesInExistingInstance(&iid, (HINSTANCE)v135, (unsigned int)v136, &Block);
    if ( (int)(inited + 0x80000000) < 0 || inited == -2147024894 )
      goto LABEL_247;
  }
  v135 = *(struct _GUID **)iid.Data4;
  v138 = *(_QWORD *)&iid.Data1;
  v136 = *(struct _GUID **)GUID_NULL.Data4;
  v139 = *(_QWORD *)&GUID_NULL.Data1;
LABEL_357:
  if ( CDevEnvAppId::ms_fDiffSwitchOnCommandLine && (v138 != v139 || v135 != v136) )
  {
    inited = util_TryToDiffFilesInExistingInstance(
               &iid,
               (HINSTANCE)v135,
               (unsigned int)v136,
               CDevEnvAppId::ms_wszDiffArguments);
    if ( inited >= 0 )
      goto LABEL_247;
  }
  *(_DWORD *)&hKey.wYear = 0;
  inited = util_CheckMigrationRequired(lpSubKey, v135, (unsigned int)v136, v137, (int *)&hKey);
  if ( inited < 0 || *(_DWORD *)&hKey.wYear )
  {
    v171 = ATL::CAtlStringMgr::GetInstance();
    if ( !v171 )
      goto LABEL_494;
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v171 + 24LL))(v171) + 24;
    if ( inited >= 0 )
      v172 = L"fMigrationRequired is true.";
    else
      v172 = L"Failure calling util_CheckMigrationRequired.";
    ATL::CSimpleStringT<unsigned short,0>::SetString(Type, v172);
    v67 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)(unsigned int)inited,
      dwDesiredAccesse);
    goto LABEL_101;
  }
  v140 = CDevEnvAppId::ms_pTheAppId;
  if ( (*(unsigned __int8 (__fastcall **)(void *))(CDevEnvAppId::ms_PkgDefManagement + 96LL))(&CDevEnvAppId::ms_PkgDefManagement) )
    *((_QWORD *)v140 + 184) = &CDevEnvAppId::ms_PkgDefManagement;
  v141 = CDevEnvAppId::ms_pTheAppId;
  *((_QWORD *)CDevEnvAppId::ms_pTheAppId + 49) = &CDevEnvAppId::ms_arrSafeModeApprovedExtensionTokens;
  *((_DWORD *)v141 + 100) = 5;
  if ( !CDevEnvAppId::ms_fUpdateConfiguration )
  {
    v142 = CDevEnvAppId::InitJITHelper((CDevEnvAppId *)&CDevEnvAppId::ms_arrSafeModeApprovedExtensionTokens);
    inited = v142;
    if ( v142 < 0 )
    {
      _mm_lfence();
      ActivityLog::LogEntryHr(
        (ActivityLog *)1,
        (int)L"VisualStudio",
        L"Failure calling InitJITHelper.",
        (const unsigned __int16 *)(unsigned int)v142,
        dwDesiredAccesse);
    }
  }
  if ( CDevEnvAppId::ms_fResetUserData )
  {
    v143 = 1;
    dword_14009CDF0 = 1;
  }
  else
  {
    v143 = dword_14009CDF0;
  }
  if ( dword_14009CDF4 )
    goto LABEL_302;
  if ( v143 || dword_14009CED0 )
  {
    *((_BYTE *)CDetourRules::GetInstance() + 10) = 1;
    *(_QWORD *)&hKey.wYear = 0;
    *(_DWORD *)&hKey.wHour = 0;
    v226 = 0;
    v144 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_LOCAL_MACHINE, lpSubKey, 0x20006u);
    v145 = *(HKEY *)&hKey.wYear;
    if ( !v144 && lpData )
    {
      v146 = -1;
      do
        ++v146;
      while ( lpData[v146] );
      RegSetValueExW(*(HKEY *)&hKey.wYear, L"SetupCommandLine", 0, 1u, (const BYTE *)lpData, 2 * v146 + 2);
    }
    if ( v145 )
      RegCloseKey(v145);
  }
  else if ( CDevEnvAppId::ms_fDumpVer )
  {
    *(_QWORD *)Type = 0;
    fopen_s((FILE **)Type, "devenv.ver", "w+");
    if ( *(_QWORD *)Type )
    {
      fprintf(*(FILE *const *)Type, "Software\\Microsoft\\VisualStudio\\17.0\n");
      fclose(*(FILE **)Type);
    }
    goto LABEL_247;
  }
  if ( Microsoft::VisualStudio::PkgDef::CPkgDefManagement::IsPortable((Microsoft::VisualStudio::PkgDef::CPkgDefManagement *)&CDevEnvAppId::ms_PkgDefManagement)
    || (v148 = 0, CAppIdExtImpl::m_isolationConfigInfo) )
  {
    v148 = 1;
  }
  if ( !CAppIdExtImpl::InitProfilePaths(v147, v148) )
  {
    inited = -2147467259;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      L"Returning E_FAIL due to InitProfilePaths failing.",
      (const unsigned __int16 *)0x80004005LL,
      dwDesiredAccesse);
    v4 = 3055;
    goto LABEL_248;
  }
  qword_14009CE40 = (__int64)CDevEnvAppId::ms_pTheAppId + 428;
  if ( CDevEnvAppId::ms_pTheAppId )
    qword_14009CE68 = (__int64)CDevEnvAppId::ms_pTheAppId + 1520;
  else
    qword_14009CE68 = 0;
  if ( CDevEnvAppId::ms_pTheAppId )
    qword_14009CE70 = (__int64)CDevEnvAppId::ms_pTheAppId + 8;
  else
    qword_14009CE70 = 0;
  v151 = CDevEnvAppId::SetCmdUICtxts(CDevEnvAppId::ms_pTheAppId);
  if ( v151 < 0 )
  {
    v152 = ATL::CAtlStringMgr::GetInstance();
    if ( !v152 )
      goto LABEL_494;
    _mm_lfence();
    *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v152 + 24LL))(v152) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      Type,
      L"Failure calling %s.",
      L"SetCmdUICtxts");
    v67 = *(const unsigned __int16 **)Type;
    ActivityLog::LogEntryHr(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      *(const unsigned __int16 **)Type,
      (const unsigned __int16 *)(unsigned int)v151,
      dwDesiredAccesse);
    inited = v151;
    goto LABEL_101;
  }
  v219[0] = 6640;
  v219[1] = 6672;
  v219[2] = 6673;
  v220 = L"RDRERRRRRRI2RRRRQEQPPKEHRRRERRRRRIRRRIRRP0E2HPZZZKC9KHQTM9P3KICHHKZCPHARPQE9C3K0E3Q3ARK9ERHCPMKZICK9ZQRHHREZETR"
          "EZQP8Q1ZDIKDREHR2C3K9RDP9MZQ9JQHCKEIMARRZC8RZE0E2EMMTZHC8";
  v221 = 32771;
  v153 = 6650;
  v154 = &v222;
  v155 = 19;
  do
  {
    *(_DWORD *)v154 = v153++;
    v154 += 4;
    --v155;
  }
  while ( v155 );
  v223 = 0;
  v224 = 6671;
  CAppIdExtImpl::InitCheckLoadPackage(
    (CAppIdExtImpl *)*((unsigned __int8 *)CDevEnvAppId::ms_pTheAppId + 1696),
    lpSubKey,
    v149,
    v150,
    (struct tagQueryLoadPackageErrMessages *)v219,
    *((unsigned __int8 *)CDevEnvAppId::ms_pTheAppId + 1696),
    dwOptions,
    v196,
    (const unsigned __int16 **)v197,
    v198,
    v199);
  v156 = CDevEnvAppId::ms_pTheAppId;
  v157 = (const unsigned __int16 *)&CDevEnvAppId::ms_SettingsRegistryRoots;
  *((_QWORD *)CDevEnvAppId::ms_pTheAppId + 52) = &CDevEnvAppId::ms_SettingsRegistryRoots;
  *((_DWORD *)v156 + 106) = 9;
  if ( CDevEnvAppId::ms_fResetSkipsRequested || dword_14009CDF0 || (v158 = CDevEnvAppId::ms_fUpdateConfiguration) != 0 )
  {
    CAppIdExtImpl::ResetSkipPackages((CAppIdExtImpl *)&CDevEnvAppId::ms_SettingsRegistryRoots);
    v158 = CDevEnvAppId::ms_fUpdateConfiguration;
  }
  if ( !CDevEnvAppId::ms_fResetUserData )
  {
    if ( CDevEnvAppId::ms_fValidateCtm )
    {
      MSENV = (HMODULE)anonymous_namespace_::LoadMSENV(&CDevEnvAppId::ms_MainParam);
      v166 = MSENV;
      if ( MSENV && (v167 = GetProcAddress(MSENV, "VStudioValidateCmds")) != 0 )
      {
        hModule = v166;
        v168 = ((__int64 (__fastcall *)(void *))v167)(&CDevEnvAppId::ms_MainParam);
      }
      else
      {
        LastError = GetLastError();
        v168 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v168 = LastError;
      }
      if ( v168 < 0 )
      {
        _mm_lfence();
        ActivityLog::LogEntryHr(
          (ActivityLog *)1,
          (int)L"VisualStudio",
          L"Returning 3002 error due to util_CallVSValidateCommands failing.",
          (const unsigned __int16 *)(unsigned int)inited,
          dwDesiredAccessf);
        v204 = 3002;
        v4 = 3054;
        goto LABEL_248;
      }
      goto LABEL_247;
    }
    if ( !v158 )
    {
      if ( !(unsigned int)util_CallVsMain((struct MAINPARAM *)&CDevEnvAppId::ms_MainParam, (int *)&lpText) )
      {
        inited = -2147467259;
        ActivityLog::LogEntryHr(
          (ActivityLog *)1,
          (int)L"VisualStudio",
          L"Returning E_FAIL due to util_CallVsMain failing.",
          (const unsigned __int16 *)0x80004005LL,
          dwDesiredAccessf);
        v4 = 3051;
        v204 = (unsigned int)lpText;
        goto LABEL_248;
      }
      v204 = (unsigned int)lpText;
      goto LABEL_247;
    }
    if ( (int)IsCompatibleNDPVersionInstalled(v157) >= 0 )
    {
      inited = util_CallVSComposeMEF((struct MAINPARAM *)&CDevEnvAppId::ms_MainParam);
      if ( inited < 0 )
      {
        v170 = ATL::CAtlStringMgr::GetInstance();
        if ( !v170 )
          goto LABEL_494;
        _mm_lfence();
        *(_QWORD *)Type = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v170 + 24LL))(v170) + 24;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          Type,
          L"Returning 0x%08x error due to util_CallVSComposeMEF failing.",
          (unsigned int)inited);
        v67 = *(const unsigned __int16 **)Type;
        ActivityLog::LogEntryHr(
          (ActivityLog *)1,
          (int)L"VisualStudio",
          *(const unsigned __int16 **)Type,
          (const unsigned __int16 *)(unsigned int)inited,
          dwDesiredAccessf);
        v204 = inited;
        goto LABEL_101;
      }
    }
    goto LABEL_302;
  }
  util_RemoveRecentDestinations();
  util_MarkKechainForClear();
  if ( CAppIdExtImpl::m_isolationConfigInfo )
  {
    v160 = ::hKey;
    if ( *(_QWORD *)(qword_14009D1C0 + 232) )
      v160 = *(HKEY *)(qword_14009D1C0 + 232);
    RegCloseKey(v160);
    CDetouringPkgDefManagement::Shutdown((CDetouringPkgDefManagement *)&CDevEnvAppId::ms_PkgDefManagement);
  }
  v161 = CDevEnvAppId::ms_pTheAppId;
  v162 = CAppIdExtImpl::RemoveDir(v159, (const unsigned __int16 *)CDevEnvAppId::ms_pTheAppId + 214);
  v164 = CAppIdExtImpl::RemoveDir(v163, (const unsigned __int16 *)v161 + 474);
  if ( !v162 || (inited = 0, !v164) )
    inited = -2147467259;
  v204 = 0;
  v4 = 3110;
LABEL_248:
  v115 = CDevEnvAppId::ms_pTheAppId;
  if ( CDevEnvAppId::ms_pTheAppId )
  {
    CSplash::DestroySplashScreen((CDevEnvAppId *)((char *)CDevEnvAppId::ms_pTheAppId + 1528));
    v115 = CDevEnvAppId::ms_pTheAppId;
  }
  if ( inited < 0 && !CDevEnvAppId::ms_fUpdateConfiguration && !CDevEnvAppId::ms_fDeferUpdateConfiguration )
  {
    if ( !lpSubKey )
      lpSubKey = L"Software\\Microsoft\\VisualStudio\\17.0";
    if ( v115 )
      (*(void (__fastcall **)(CDevEnvAppId *, _QWORD, _QWORD))(*(_QWORD *)v115 + 48LL))(v115, 0, 0);
    if ( !hInstance )
    {
      util_ShowMessage(qword_14009D158, 0x19E6u, 0x19E7u);
      goto LABEL_452;
    }
    if ( !v4 )
    {
      if ( inited == -2147024894 )
      {
        v4 = 3050;
      }
      else if ( inited == -2147024882 )
      {
        v4 = 3053;
      }
      else
      {
        v4 = 3051;
        if ( inited != -2147024809 )
          v4 = 3054;
      }
    }
    v173 = ATL::CAtlStringMgr::GetInstance();
    if ( v173 )
    {
      v174 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v173 + 24LL))(v173);
      v176 = (wchar_t *)(v174 + 24);
      *(_QWORD *)Type = v174 + 24;
      if ( v4 == 3050 || v4 != 3054 && v4 - 3107 > 1 )
      {
        _mm_lfence();
        util_ShowMessage(hInstance, 0xBB8u, v4);
      }
      else
      {
        if ( ((1 - *(_DWORD *)(v174 + 16)) | (*(_DWORD *)(v174 + 12) - 260)) < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(Type, 260);
          v176 = *(wchar_t **)Type;
        }
        ActivityLog::GetLogFilePath(v176, 0x104u, v175);
        v177 = wcsnlen(v176, *((int *)v176 - 3));
        if ( v177 < 0 || v177 > *((_DWORD *)v176 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        _mm_lfence();
        *((_DWORD *)v176 - 4) = v177;
        v176[v177] = 0;
        v179 = hInstance;
        if ( *((int *)v176 - 2) > 1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Fork(Type, *((unsigned int *)v176 - 4));
          v176 = *(wchar_t **)Type;
        }
        util_ShowFormatMessage(v179, v178, v4, v176);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v176 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v176 - 3) + 8LL))(*((_QWORD *)v176 - 3));
      }
      goto LABEL_452;
    }
LABEL_494:
    ATL::AtlThrowImpl(-2147467259);
  }
LABEL_452:
  v180 = CDevEnvAppId::ms_pCmdLineRegistryParms;
  while ( 1 )
  {
    v181 = v180;
    if ( !v180 )
      break;
    v180 = (struct tagCmdLineRegistryParms *)*((_QWORD *)v180 + 2);
    free_0(v181);
  }
  CDevEnvAppId::ms_pCmdLineRegistryParms = 0;
  v182 = hModule;
  util_FreeMainParam((struct MAINPARAM *)&CDevEnvAppId::ms_MainParam);
  if ( CDevEnvAppId::ms_pTheAppId )
    (*(void (__fastcall **)(char *))(*((_QWORD *)CDevEnvAppId::ms_pTheAppId + 1) + 16LL))((char *)CDevEnvAppId::ms_pTheAppId + 8);
  if ( v212 )
  {
    VsStopCLR();
    util_OleUninitialize();
  }
  if ( v182 )
  {
    v183 = GetProcAddress(v182, "VStudioTerm");
    if ( v183 )
      ((void (__fastcall *)(_QWORD))v183)(0);
    else
      GetLastError();
  }
  v184 = g_pLockClr;
  if ( g_pLockClr )
  {
    CLockClr::~CLockClr(g_pLockClr);
    operator delete(v184, (const struct std::nothrow_t *)0x28);
  }
  g_pLockClr = 0;
  CDetouringPkgDefManagement::Shutdown((CDetouringPkgDefManagement *)&CDevEnvAppId::ms_PkgDefManagement);
  if ( v205 )
    WerUnregisterRuntimeExceptionModule(v6, 0);
  v185 = String1[0] - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)String1[0] - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v185 + 8LL))(*(_QWORD *)v185);
  }
  v186 = v208 - 6;
  if ( _InterlockedExchangeAdd(v208 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v186 + 8LL))(*(_QWORD *)v186);
  }
  if ( v216 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 - 24) + 8LL))(*(_QWORD *)(v12 - 24));
  }
  SysFreeString(0);
  SysFreeString(bstr);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
  }
  return v204;
}

```

## disassembly

```asm
0x14000ccfc  mov     [rsp-8+arg_10], rbx
0x14000cd01  push    rbp
0x14000cd02  push    rsi
0x14000cd03  push    rdi
0x14000cd04  push    r12
0x14000cd06  push    r13
0x14000cd08  push    r14
0x14000cd0a  push    r15
0x14000cd0c  lea     rbp, [rsp-2C0h]
0x14000cd14  sub     rsp, 3C0h
0x14000cd1b  mov     rax, cs:__security_cookie
0x14000cd22  xor     rax, rsp
0x14000cd25  mov     [rbp+2F0h+var_40], rax
0x14000cd2c  mov     esi, edx
0x14000cd2e  mov     rbx, rcx
0x14000cd31  xor     edi, edi
0x14000cd33  mov     [rbp+2F0h+var_34C], edi
0x14000cd36  or      eax, 0FFFFFFFFh
0x14000cd39  mov     [rbp+2F0h+var_354], eax
0x14000cd3c  mov     dword ptr [rbp+2F0h+lpText], eax
0x14000cd3f  mov     [rbp+2F0h+cbData], edi
0x14000cd42  mov     r14d, edi
0x14000cd45  mov     [rbp+2F0h+var_368], edi
0x14000cd48  mov     [rbp+2F0h+var_320], edi
0x14000cd4b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000cd50  mov     rcx, rax
0x14000cd53  test    rax, rax
0x14000cd56  jz      loc_14000F02D
0x14000cd5c  mov     rax, [rax]
0x14000cd5f  call    qword ptr [rax+18h]
0x14000cd62  lea     r15, [rax+18h]
0x14000cd66  mov     [rbp+2F0h+pwszOutOfProcessCallbackDll], r15
0x14000cd6a  mov     [rbp+2F0h+var_350], dil
0x14000cd6e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000cd73  mov     rcx, rax
0x14000cd76  test    rax, rax
0x14000cd79  jz      loc_14000F03B
0x14000cd7f  mov     rax, [rax]
0x14000cd82  call    qword ptr [rax+18h]
0x14000cd85  lea     r12, [rax+18h]
0x14000cd89  mov     [rbp+2F0h+var_2F8], r12
0x14000cd8d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000cd92  mov     rcx, rax
0x14000cd95  test    rax, rax
0x14000cd98  jz      loc_14000F049
0x14000cd9e  mov     rax, [rax]
0x14000cda1  call    qword ptr [rax+18h]
0x14000cda4  lea     r13, [rax+18h]
0x14000cda8  mov     [rbp+2F0h+var_318], r13
0x14000cdac  mov     [rbp+2F0h+bstr], rdi
0x14000cdb0  mov     [rbp+2F0h+var_2E8], rdi
0x14000cdb4  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000cdb9  mov     rcx, rax
0x14000cdbc  test    rax, rax
0x14000cdbf  jz      loc_14000F057
0x14000cdc5  mov     rax, [rax]
0x14000cdc8  call    qword ptr [rax+18h]
0x14000cdcb  lea     rdi, [rax+18h]
0x14000cdcf  mov     qword ptr [rbp+2F0h+var_310], rdi
0x14000cdd3  xor     eax, eax
0x14000cdd5  mov     [rbp+2F0h+var_300], rax
0x14000cdd9  lea     rdx, aVisualstudio17; "VisualStudio.17.0"
0x14000cde0  lea     rcx, [rbp+2F0h+var_340]
0x14000cde4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000cde9  lea     rdx, aClient; "$Client$"
0x14000cdf0  lea     rcx, [rbp+2F0h+String1]
0x14000cdf4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000cdf9  xor     eax, eax
0x14000cdfb  xchg    rax, cs:hInstance
0x14000ce02  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\VSCommon\\17.0\\SQ"...
0x14000ce09  mov     r8d, esi; int
0x14000ce0c  mov     rdx, rbx; unsigned __int16 *
0x14000ce0f  lea     rcx, ?ms_MainParam@CDevEnvAppId@@1UMAINPARAM@@A; struct MAINPARAM *
0x14000ce16  call    ?util_InitMainParam@@YAJPEAUMAINPARAM@@PEAGH1@Z; util_InitMainParam(MAINPARAM *,ushort *,int,ushort *)
0x14000ce1b  mov     esi, eax
0x14000ce1d  test    eax, eax
0x14000ce1f  jns     short loc_14000CE9E
0x14000ce21  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000ce26  mov     rcx, rax
0x14000ce29  test    rax, rax
0x14000ce2c  jz      loc_14000F0A8
0x14000ce32  lfence
0x14000ce35  mov     rax, [rax]
0x14000ce38  call    qword ptr [rax+18h]
0x14000ce3b  add     rax, 18h
0x14000ce3f  mov     qword ptr [rbp+2F0h+Type], rax
0x14000ce43  lea     r8, aUtilInitmainpa; "util_InitMainParam"
0x14000ce4a  lea     rdx, aFailureCalling_3; "Failure calling %s."
0x14000ce51  lea     rcx, [rbp+2F0h+Type]
0x14000ce55  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000ce5a  mov     r9d, esi; unsigned __int16 *
0x14000ce5d  mov     rbx, qword ptr [rbp+2F0h+Type]
0x14000ce61  mov     r8, rbx; unsigned __int16 *
0x14000ce64  lea     rdx, aVisualstudio; "VisualStudio"
0x14000ce6b  mov     ecx, 1; this
0x14000ce70  call    ?LogEntryHr@ActivityLog@@YAJHPEBG0J@Z; ActivityLog::LogEntryHr(int,ushort const *,ushort const *,long)
0x14000ce75  nop
0x14000ce76  lea     rdx, [rbx-18h]
0x14000ce7a  or      eax, 0FFFFFFFFh
0x14000ce7d  lock xadd [rdx+10h], eax
0x14000ce82  xor     ebx, ebx
0x14000ce84  sub     eax, 1
0x14000ce87  jg      loc_14000DFD5
0x14000ce8d  lfence
0x14000ce90  mov     rcx, [rdx]
0x14000ce93  mov     rax, [rcx]
0x14000ce96  call    qword ptr [rax+8]
0x14000ce99  jmp     loc_14000DFD5
0x14000ce9e  mov     esi, 1
0x14000cea3  mov     ecx, esi
0x14000cea5  sub     ecx, [r15-8]
0x14000cea9  mov     eax, [r15-0Ch]
0x14000cead  sub     eax, 104h
0x14000ceb2  or      eax, ecx
0x14000ceb4  jge     short loc_14000CEC8
0x14000ceb6  mov     edx, 104h
0x14000cebb  lea     rcx, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cebf  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000cec4  mov     r15, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cec8  mov     r8d, 104h; nSize
0x14000cece  mov     rdx, r15; lpFilename
0x14000ced1  xor     ecx, ecx; hModule
0x14000ced3  call    cs:__imp_GetModuleFileNameW
0x14000ced9  mov     ebx, eax
0x14000cedb  movsxd  rdx, dword ptr [r15-0Ch]; MaxCount
0x14000cedf  mov     rcx, r15; Source
0x14000cee2  call    cs:__imp_wcsnlen
0x14000cee8  xor     r14d, r14d
0x14000ceeb  test    eax, eax
0x14000ceed  js      loc_14000F01E
0x14000cef3  cmp     eax, [r15-0Ch]
0x14000cef7  jg      loc_14000F01E
0x14000cefd  mov     [r15-10h], eax
0x14000cf01  cdqe
0x14000cf03  mov     [r15+rax*2], r14w
0x14000cf08  lea     r14, aVisualstudio; "VisualStudio"
0x14000cf0f  xor     eax, eax
0x14000cf11  test    ebx, ebx
0x14000cf13  jz      loc_14000D01E
0x14000cf19  lea     edx, [rax+5Ch]; Ch
0x14000cf1c  mov     rcx, r15; Str
0x14000cf1f  call    cs:__imp_wcsrchr
0x14000cf25  mov     rbx, rax
0x14000cf28  xor     eax, eax
0x14000cf2a  test    rbx, rbx
0x14000cf2d  jz      loc_14000D01E
0x14000cf33  sub     rbx, r15
0x14000cf36  sar     rbx, 1
0x14000cf39  cmp     ebx, 0FFFFFFFFh
0x14000cf3c  jz      loc_14000D01E
0x14000cf42  test    ebx, ebx
0x14000cf44  js      loc_14000F01E
0x14000cf4a  mov     ecx, esi
0x14000cf4c  sub     ecx, [r15-8]
0x14000cf50  mov     eax, [r15-0Ch]
0x14000cf54  sub     eax, ebx
0x14000cf56  or      eax, ecx
0x14000cf58  jge     short loc_14000CF6C
0x14000cf5a  lfence
0x14000cf5d  mov     edx, ebx
0x14000cf5f  lea     rcx, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cf63  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000cf68  mov     r15, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cf6c  cmp     ebx, [r15-0Ch]
0x14000cf70  jg      loc_14000F01E
0x14000cf76  mov     [r15-10h], ebx
0x14000cf7a  movsxd  rax, ebx
0x14000cf7d  xor     ecx, ecx
0x14000cf7f  mov     [r15+rax*2], cx
0x14000cf84  lea     r8d, [rcx+11h]
0x14000cf88  lea     rdx, aVswerhandlerDl; "\\VsWerHandler.dll"
0x14000cf8f  lea     rcx, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cf93  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000cf98  xor     edx, edx; pContext
0x14000cf9a  mov     r15, [rbp+2F0h+pwszOutOfProcessCallbackDll]
0x14000cf9e  mov     rcx, r15; pwszOutOfProcessCallbackDll
0x14000cfa1  call    cs:__imp_WerRegisterRuntimeExceptionModule
0x14000cfa7  mov     ebx, eax
0x14000cfa9  xor     eax, eax
0x14000cfab  test    ebx, ebx
0x14000cfad  jnz     short loc_14000CFB5
0x14000cfaf  mov     [rbp+2F0h+var_350], sil
0x14000cfb3  jmp     short loc_14000D01E
0x14000cfb5  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000cfba  mov     rcx, rax
0x14000cfbd  test    rax, rax
0x14000cfc0  jz      loc_14000F0A8
0x14000cfc6  mov     rax, [rax]
0x14000cfc9  call    qword ptr [rax+18h]
0x14000cfcc  add     rax, 18h
0x14000cfd0  mov     qword ptr [rbp+2F0h+Type], rax
0x14000cfd4  mov     r9, r15
0x14000cfd7  mov     r8d, ebx
0x14000cfda  lea     rdx, aHresultDReturn; "HRESULT %d returned when registering WE"...
0x14000cfe1  lea     rcx, [rbp+2F0h+Type]
0x14000cfe5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000cfea  mov     rbx, qword ptr [rbp+2F0h+Type]
0x14000cfee  mov     r8, rbx; unsigned __int16 *
0x14000cff1  mov     rdx, r14; int
0x14000cff4  mov     ecx, 2; this
0x14000cff9  call    ?LogEntry@ActivityLog@@YAJHPEBG0@Z; ActivityLog::LogEntry(int,ushort const *,ushort const *)
0x14000cffe  nop
0x14000cfff  lea     rdx, [rbx-18h]
0x14000d003  or      eax, 0FFFFFFFFh
0x14000d006  lock xadd [rdx+10h], eax
0x14000d00b  sub     eax, 1
0x14000d00e  jg      short loc_14000D01C
0x14000d010  lfence
0x14000d013  mov     rcx, [rdx]
0x14000d016  mov     rax, [rcx]
0x14000d019  call    qword ptr [rax+8]
0x14000d01c  xor     eax, eax
0x14000d01e  lea     rcx, ?ms_pszInvalidSwitch@CDevEnvAppId@@1PEAGEA; ushort * CDevEnvAppId::ms_pszInvalidSwitch
0x14000d025  mov     qword ptr [rsp+3F0h+bInheritHandle], rcx; unsigned __int16 **
0x14000d02a  mov     qword ptr [rsp+3F0h+dwDesiredAccess], rax; struct tagCmdLineRegistryParms **
0x14000d02f  lea     r9, Block; struct CmdLineFiles **
0x14000d036  lea     r8, ?ms_CmdLineParms@CDevEnvAppId@@1PAUtagCmdLineParms@@A; struct tagCmdLineParms *
0x14000d03d  mov     rdx, cs:qword_14009CD90; unsigned __int16 *
0x14000d044  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\VisualStudio\\17.0"
0x14000d04b  call    ?util_ParseCmdLineParms@@YAJPEBGPEAGPEAUtagCmdLineParms@@PEAPEAUCmdLineFiles@@PEAPEAUtagCmdLineRegistryParms@@PEAPEAG@Z; util_ParseCmdLineParms(ushort const *,ushort *,tagCmdLineParms *,CmdLineFiles * *,tagCmdLineRegistryParms * *,ushort * *)
0x14000d050  mov     [rbp+2F0h+Type], eax
0x14000d053  xor     r8d, r8d
0x14000d056  test    eax, eax
0x14000d058  jns     short loc_14000D063
0x14000d05a  cmp     eax, 80070057h
0x14000d05f  jz      short loc_14000D082
0x14000d061  jmp     short loc_14000D076
0x14000d063  lea     rcx, ?ms_MainParam@CDevEnvAppId@@1UMAINPARAM@@A; struct MAINPARAM *
0x14000d06a  call    ?util_CheckMainParam@@YAJPEAUMAINPARAM@@@Z; util_CheckMainParam(MAINPARAM *)
0x14000d06f  mov     [rbp+2F0h+cbData], eax
0x14000d072  test    eax, eax
0x14000d074  jns     short loc_14000D082
0x14000d076  mov     cs:dword_14009CDD8, esi
0x14000d07c  mov     cs:?ms_fInvalidCmdLine@CDevEnvAppId@@1HA, esi; int CDevEnvAppId::ms_fInvalidCmdLine
0x14000d082  cmp     cs:dword_14009CDDC, r8d
0x14000d089  jz      short loc_14000D091
0x14000d08b  call    cs:__imp_DebugBreak
0x14000d091  mov     ecx, 0FFFFFFF5h; nStdHandle
0x14000d096  call    cs:__imp_GetStdHandle
0x14000d09c  mov     rbx, rax
0x14000d09f  mov     rcx, rax; void *
0x14000d0a2  call    ?util_FConsoleHandle@@YAHPEAX@Z; util_FConsoleHandle(void *)
0x14000d0a7  test    eax, eax
0x14000d0a9  jz      short loc_14000D0FA
0x14000d0ab  call    cs:__imp_GetCurrentProcess
0x14000d0b1  mov     [rsp+3F0h+dwOptions], 2; dwOptions
0x14000d0b9  xor     ecx, ecx
0x14000d0bb  mov     [rsp+3F0h+bInheritHandle], ecx; bInheritHandle
0x14000d0bf  mov     [rsp+3F0h+dwDesiredAccess], ecx; int
0x14000d0c3  lea     r9, [rbp+2F0h+TargetHandle]; lpTargetHandle
0x14000d0c7  mov     r8, rax; hTargetProcessHandle
0x14000d0ca  mov     rdx, rbx; hSourceHandle
0x14000d0cd  mov     rcx, rax; hSourceProcessHandle
0x14000d0d0  call    cs:__imp_DuplicateHandle
0x14000d0d6  test    eax, eax
0x14000d0d8  jz      short loc_14000D0FA
0x14000d0da  mov     rdx, [rbp+2F0h+TargetHandle]; hHandle
0x14000d0de  mov     ecx, 0FFFFFFF5h; nStdHandle
0x14000d0e3  call    cs:__imp_SetStdHandle
0x14000d0e9  test    eax, eax
0x14000d0eb  mov     rcx, [rbp+2F0h+TargetHandle]
0x14000d0ef  jz      short loc_14000D0F4
0x14000d0f1  mov     rcx, rbx; hObject
0x14000d0f4  call    cs:__imp_CloseHandle
0x14000d0fa  xor     ebx, ebx
0x14000d0fc  cmp     cs:lpSubKey, rbx
0x14000d103  jnz     short loc_14000D14D
0x14000d105  cmp     cs:?ms_wszRegistrySuffix@CAppIdExtImpl@@1PEAGEA, rbx; ushort * CAppIdExtImpl::ms_wszRegistrySuffix
0x14000d10c  jnz     short loc_14000D14D
0x14000d10e  lea     rcx, [rbp+2F0h+Source]; Buffer
0x14000d115  call    ?ReadRootSuffix@@YAXPEAGH@Z; ReadRootSuffix(ushort *,int)
0x14000d11a  cmp     [rbp+2F0h+Source], bx
0x14000d121  jz      short loc_14000D14D
0x14000d123  mov     r9d, 103h; MaxCount
0x14000d129  lea     r8, [rbp+2F0h+Source]; Source
0x14000d130  lea     edx, [r9+1]; SizeInWords
0x14000d134  lea     rbx, Destination
0x14000d13b  mov     rcx, rbx; Destination
0x14000d13e  call    cs:__imp_wcsncpy_s
0x14000d144  mov     cs:?ms_wszRegistrySuffix@CAppIdExtImpl@@1PEAGEA, rbx; ushort * CAppIdExtImpl::ms_wszRegistrySuffix
0x14000d14b  xor     ebx, ebx
0x14000d14d  lea     rcx, ?m_isolationConfigInfo@CAppIdExtImpl@@1UIsolationConfigInfo@@A; struct IsolationConfigInfo *
0x14000d154  call    ?ReadIsolationConfig@@YAJAEAUIsolationConfigInfo@@@Z; ReadIsolationConfig(IsolationConfigInfo &)
0x14000d159  mov     rdx, r14; int
0x14000d15c  mov     ecx, 3; this
0x14000d161  test    eax, eax
0x14000d163  jns     short loc_14000D16E
0x14000d165  lea     r8, aRunningInTradi; "Running in traditional mode."
0x14000d16c  jmp     short loc_14000D192
0x14000d16e  lea     r8, aRunningInIsola; "Running in isolation mode."
0x14000d175  call    ?LogEntry@ActivityLog@@YAJHPEBG0@Z; ActivityLog::LogEntry(int,ushort const *,ushort const *)
0x14000d17a  call    ?ReadInstallationConfig@@YAJAEAUInstallationConfigInfo@@@Z; ReadInstallationConfig(InstallationConfigInfo &)
0x14000d17f  test    eax, eax
0x14000d181  jns     short loc_14000D19D
0x14000d183  lea     r8, aFailedToReadIn_0; "Failed to read installation config info"...
0x14000d18a  mov     rdx, r14; int
0x14000d18d  mov     ecx, 2; this
0x14000d192  lfence
0x14000d195  mov     r9d, eax; unsigned __int16 *
0x14000d198  call    ?LogEntryHr@ActivityLog@@YAJHPEBG0J@Z; ActivityLog::LogEntryHr(int,ushort const *,ushort const *,long)
  ... truncated ...
```
