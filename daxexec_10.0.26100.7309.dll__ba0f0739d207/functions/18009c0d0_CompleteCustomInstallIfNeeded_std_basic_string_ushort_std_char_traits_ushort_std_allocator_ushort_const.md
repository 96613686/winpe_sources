# CompleteCustomInstallIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009c0d0`
- end: `0x18009cb6e`
- name: `?CompleteCustomInstallIfNeeded@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2718`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ff30`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180010a84`
- `0x180011300`
- `0x1800116b0`
- `0x180011820`
- `0x180013148`
- `0x180013188`
- `0x180014ed8`
- `0x180015ec8`
- `0x180017374`
- `0x18001eb48`
- `0x18002031c`
- `0x18002b240`
- `0x1800341b4`
- `0x1800721b0`
- `0x180095718`
- `0x18009bdf8`
- `0x18009c0d0`
- `0x18009cb90`
- `0x18009cd10`
- `0x18009d110`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c964`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c558`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009c542`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009c542`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009c529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009c529`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009c8d0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009c8d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c9dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c9dd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009c6c2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009c6c2`
- `USERENV!CreateEnvironmentBlock` at `0x18009c6f6`
- `USERENV!CreateEnvironmentBlock` at `0x18009c6f6`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18009c64e`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18009c64e`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009c11e`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009c98b`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009c11e`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009c98b`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009c740`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009c740`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009c929`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009c929`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009c780`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009c780`

## string_xrefs

- `0x18009c16c`: `PreActivationCustomInstallCompletion`
- `0x18009c3ea`: `/install`
- `0x18009c360`: `custominstallexec.exe`
- `0x18009ca7f`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009ca91`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009caa2`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cab7`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cac9`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cada`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009caec`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cafe`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cb15`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cb2d`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cb44`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009cb5b`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CompleteCustomInstallIfNeeded(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rdi
  unsigned __int16 *v2; // rdx
  __int64 result; // rax
  const char *v4; // r9
  const unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  void *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  void **v13; // rbx
  HANDLE CurrentThread; // rax
  BOOL v15; // ebx
  const char *v16; // r9
  char *v17; // rax
  const char *v18; // r9
  HINSTANCE v19; // rbx
  HANDLE v20; // rcx
  const WCHAR *v21; // rax
  const WCHAR *v22; // rax
  const char *v23; // r9
  void **phNewToken; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  void **v28; // rax
  const char *v29; // r9
  void *lpEnvironment; // rbx
  __int64 v31; // rax
  WCHAR *v32; // r8
  const WCHAR *v33; // rdx
  const char *v34; // r9
  int EffectivePackageStatusForUser; // eax
  struct _PROCESS_INFORMATION *v36; // rdx
  int TokenType; // [rsp+20h] [rbp-3E8h]
  unsigned int v38; // [rsp+60h] [rbp-3A8h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-3A0h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+70h] [rbp-398h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp-390h] BYREF
  HANDLE hExistingToken; // [rsp+80h] [rbp-388h] BYREF
  LPVOID Environment; // [rsp+88h] [rbp-380h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-378h] BYREF
  char v45; // [rsp+A8h] [rbp-360h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+B0h] [rbp-358h] BYREF
  HWND *p_hwnd; // [rsp+120h] [rbp-2E8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+130h] [rbp-2D8h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+1A0h] [rbp-268h] BYREF
  __int64 v50[2]; // [rsp+1B0h] [rbp-258h]
  LPWSTR lpCommandLine[2]; // [rsp+1C0h] [rbp-248h] BYREF
  __int128 v52; // [rsp+1D0h] [rbp-238h]
  __int128 v53; // [rsp+1E0h] [rbp-228h] BYREF
  __int128 v54; // [rsp+1F0h] [rbp-218h]
  __int128 v55; // [rsp+200h] [rbp-208h] BYREF
  __int128 v56; // [rsp+210h] [rbp-1F8h]
  _OWORD Src[2]; // [rsp+220h] [rbp-1E8h] BYREF
  _OWORD v58[2]; // [rsp+240h] [rbp-1C8h] BYREF
  void **v59; // [rsp+260h] [rbp-1A8h] BYREF
  int v60; // [rsp+268h] [rbp-1A0h] BYREF
  char v61; // [rsp+26Ch] [rbp-19Ch]
  int v62; // [rsp+290h] [rbp-178h] BYREF
  const char *v63; // [rsp+298h] [rbp-170h]
  __int64 v64; // [rsp+2A0h] [rbp-168h]
  char v65; // [rsp+2A8h] [rbp-160h]
  int v66; // [rsp+2B0h] [rbp-158h]
  _BYTE v67[152]; // [rsp+2B8h] [rbp-150h] BYREF
  __int128 v68; // [rsp+350h] [rbp-B8h]
  int v69; // [rsp+360h] [rbp-A8h]
  __int64 v70; // [rsp+368h] [rbp-A0h]
  int *v71; // [rsp+370h] [rbp-98h]
  __int64 v72; // [rsp+378h] [rbp-90h]
  __int64 v73; // [rsp+380h] [rbp-88h]
  void ***v74; // [rsp+388h] [rbp-80h]
  __int64 v75; // [rsp+390h] [rbp-78h]
  int v76; // [rsp+398h] [rbp-70h]
  int *v77; // [rsp+3A0h] [rbp-68h]
  _BYTE v78[32]; // [rsp+3B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v1 = a1;
  v38 = 0;
  v2 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    v2 = *(unsigned __int16 **)a1;
  result = GetEffectivePackageStatusForUser(0, v2, &v38);
  try
  {
    if ( (int)result >= 0 && (v38 & 0x1800000) != 0 )
    {
      v5 = v1;
      if ( *((_QWORD *)v1 + 3) > 7u )
        v5 = *(const unsigned __int16 **)v1;
      v60 = 0;
      v61 = 0;
      v65 = 0;
      v62 = 0;
      v63 = "PreActivationCustomInstallCompletion";
      v64 = 0;
      v66 = 0;
      v68 = 0;
      memset_0(v67, 0, sizeof(v67));
      v69 = 1;
      v70 = 0;
      v71 = &v60;
      v72 = 0;
      v73 = 0;
      v74 = &v59;
      v75 = 0;
      v76 = 0;
      v77 = &v62;
      v59 = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
      DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(
        (DesktopAppXProvider::PreActivationCustomInstallCompletion *)&v59,
        v5,
        v38);
      v6 = v1;
      if ( *((_QWORD *)v1 + 3) > 7u )
        v6 = *(const unsigned __int16 **)v1;
      if ( IsPackagePreOrderAndNotAvailable(v6) )
      {
        DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable((DesktopAppXProvider::PreActivationCustomInstallCompletion *)&v59);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v59);
        v59 = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
        result = wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(&v59);
      }
      else
      {
        v58[0] = 0;
        v58[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v58[0]) = 0;
        pExecInfo.hwnd = (HWND)&wistd::__function::__func<_lambda_68ab120a28af3a893520bfd208deb9bd_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
        p_hwnd = &pExecInfo.hwnd;
        v7 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(v58, &pExecInfo);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)v7,
            TokenType);
        v8 = (void *)std::wstring::wstring(v78, v58);
        v9 = std::wstring::append(v8);
        *(_OWORD *)lpCommandLine = 0;
        v52 = 0;
        *(_OWORD *)lpCommandLine = *(_OWORD *)v9;
        v52 = *(_OWORD *)(v9 + 16);
        *(_QWORD *)(v9 + 16) = 0;
        *(_QWORD *)(v9 + 24) = 7;
        *(_WORD *)v9 = 0;
        v10 = std::wstring::append(lpCommandLine);
        *(_OWORD *)lpApplicationName = 0;
        v50[0] = 0;
        v50[1] = 0;
        *(_OWORD *)lpApplicationName = *(_OWORD *)v10;
        *(_OWORD *)v50 = *(_OWORD *)(v10 + 16);
        *(_QWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 7;
        *(_WORD *)v10 = 0;
        std::wstring::~wstring(lpCommandLine);
        std::wstring::~wstring(v78);
        memset(Src, 0, sizeof(Src));
        std::wstring::_Construct<1,unsigned short const *>(Src, L"/install", 8);
        v11 = std::wstring::append(Src);
        v55 = 0;
        v56 = 0;
        v55 = *(_OWORD *)v11;
        v56 = *(_OWORD *)(v11 + 16);
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 7;
        *(_WORD *)v11 = 0;
        v12 = std::wstring::append(&v55);
        v53 = 0;
        v54 = 0u;
        v53 = *(_OWORD *)v12;
        v54 = *(_OWORD *)(v12 + 16);
        *(_QWORD *)(v12 + 16) = 0;
        *(_QWORD *)(v12 + 24) = 7;
        *(_WORD *)v12 = 0;
        std::wstring::~wstring(&v55);
        std::wstring::~wstring(Src);
        memset_0(&StartupInfo, 0, 0x70u);
        StartupInfo.cb = 112;
        StartupInfo.dwFlags = 1;
        StartupInfo.wShowWindow = 5;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        hExistingToken = 0;
        v13 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hExistingToken);
        CurrentThread = GetCurrentThread();
        v15 = OpenThreadToken(CurrentThread, 2u, 1, v13);
        if ( v15 || GetLastError() != 1008 )
        {
          if ( !v15 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v16);
          hToken = 0;
          phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hToken);
          if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, phNewToken) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xAA,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v25);
          Environment = 0;
          if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v26);
          pLevelHandle = 0;
          *(_QWORD *)&v55 = &pLevelHandle;
          BYTE8(v55) = 1;
          if ( !SaferCreateLevel(1u, 0x20000u, 1u, &pLevelHandle, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xB5,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v27);
          hObject = 0;
          v28 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
          if ( !SaferComputeTokenFromLevel(pLevelHandle, hToken, v28, 0, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v29);
          lpEnvironment = Environment;
          if ( 0x7FFFFFFFFFFFFFFELL == v50[0] )
            std::_Xlen_string();
          std::wstring::wstring(Src, v50[0], L" ", 1);
          v31 = std::wstring::append(Src);
          *(_OWORD *)lpCommandLine = 0;
          v52 = 0;
          *(_OWORD *)lpCommandLine = *(_OWORD *)v31;
          v52 = *(_OWORD *)(v31 + 16);
          *(_QWORD *)(v31 + 16) = 0;
          *(_QWORD *)(v31 + 24) = 7;
          *(_WORD *)v31 = 0;
          v32 = (WCHAR *)lpCommandLine;
          if ( *((_QWORD *)&v52 + 1) > 7u )
            v32 = lpCommandLine[0];
          v33 = (const WCHAR *)lpApplicationName;
          if ( v50[1] > 7uLL )
            v33 = lpApplicationName[0];
          if ( !CreateProcessAsUserW(
                  hObject,
                  v33,
                  v32,
                  0,
                  0,
                  0,
                  0x80400u,
                  lpEnvironment,
                  0,
                  &StartupInfo,
                  &ProcessInformation) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v34);
          std::wstring::~wstring(lpCommandLine);
          std::wstring::~wstring(Src);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          SaferCloseLevel(pLevelHandle);
          if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hToken);
        }
        else
        {
          v17 = (char *)Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(&hObject);
          v19 = 0;
          if ( &v45 != v17 )
          {
            v19 = *(HINSTANCE *)v17;
            *(_QWORD *)v17 = 0;
          }
          Environment = v19;
          v20 = hObject;
          if ( hObject )
          {
            hObject = 0;
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( !v19 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x98,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v18);
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          *(_QWORD *)&pExecInfo.cbSize = __PAIR64__(pExecInfo.fMask, 112) | 0x880004000000000LL;
          pExecInfo.nShow = 5;
          v21 = (const WCHAR *)lpApplicationName;
          if ( v50[1] > 7uLL )
            v21 = lpApplicationName[0];
          pExecInfo.lpFile = v21;
          v22 = (const WCHAR *)&v53;
          if ( *((_QWORD *)&v54 + 1) > 7u )
            v22 = (const WCHAR *)v53;
          pExecInfo.lpParameters = v22;
          pExecInfo.hInstApp = v19;
          if ( !ShellExecuteExW(&pExecInfo) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v23);
          ProcessInformation.hProcess = pExecInfo.hProcess;
          (*(void (__fastcall **)(HINSTANCE))(*(_QWORD *)v19 + 16LL))(v19);
        }
        if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)0x80004005LL,
            TokenType);
        if ( *((_QWORD *)v1 + 3) > 7u )
          v1 = *(unsigned __int16 **)v1;
        EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v1, &v38);
        if ( EffectivePackageStatusForUser < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)EffectivePackageStatusForUser,
            TokenType);
        if ( (v38 & 0x1800000) != 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)0x80004005LL,
            TokenType);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v59);
        if ( (char *)hExistingToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hExistingToken);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v36);
        std::wstring::~wstring(&v53);
        std::wstring::~wstring(lpApplicationName);
        std::wstring::~wstring(v58);
        v59 = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v59);
        result = wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(&v59);
      }
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xC7,
             (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
             v4);
  }
  return result;
}

```

## disassembly

```asm
0x18009c0d0  mov     [rsp+arg_8], rbx
0x18009c0d5  mov     [rsp+arg_10], rsi
0x18009c0da  push    rdi
0x18009c0db  push    r12
0x18009c0dd  push    r13
0x18009c0df  push    r14
0x18009c0e1  push    r15
0x18009c0e3  sub     rsp, 3E0h
0x18009c0ea  mov     rax, cs:__security_cookie
0x18009c0f1  xor     rax, rsp
0x18009c0f4  mov     [rsp+408h+var_38], rax
0x18009c0fc  mov     rdi, rcx
0x18009c0ff  xor     r14d, r14d
0x18009c102  mov     [rsp+408h+var_3A8], r14d
0x18009c107  mov     rdx, rcx
0x18009c10a  lea     r15d, [r14+7]
0x18009c10e  cmp     [rcx+18h], r15
0x18009c112  jbe     short loc_18009C117
0x18009c114  mov     rdx, [rcx]
0x18009c117  lea     r8, [rsp+408h+var_3A8]
0x18009c11c  xor     ecx, ecx
0x18009c11e  call    cs:__imp_GetEffectivePackageStatusForUser
0x18009c125  nop     dword ptr [rax+rax+00h]
0x18009c12a  test    eax, eax
0x18009c12c  js      loc_18009CA4C
0x18009c132  test    [rsp+408h+var_3A8], 1800000h
0x18009c13a  jz      loc_18009CA4C
0x18009c140  mov     rbx, rdi
0x18009c143  cmp     [rdi+18h], r15
0x18009c147  jbe     short loc_18009C14C
0x18009c149  mov     rbx, [rdi]
0x18009c14c  mov     [rsp+408h+var_1A0], r14d
0x18009c154  mov     [rsp+408h+var_19C], r14b
0x18009c15c  mov     [rsp+408h+var_160], r14b
0x18009c164  mov     [rsp+408h+var_178], r14d
0x18009c16c  lea     rax, aPreactivationc; "PreActivationCustomInstallCompletion"
0x18009c173  mov     [rsp+408h+var_170], rax
0x18009c17b  mov     [rsp+408h+var_168], r14
0x18009c183  mov     [rsp+408h+var_158], r14d
0x18009c18b  xorps   xmm0, xmm0
0x18009c18e  movdqa  [rsp+408h+var_B8], xmm0
0x18009c197  xor     edx, edx; Val
0x18009c199  mov     r8d, 98h; Size
0x18009c19f  lea     rcx, [rsp+408h+var_150]; void *
0x18009c1a7  call    memset_0
0x18009c1ac  mov     esi, 1
0x18009c1b1  mov     [rsp+408h+var_A8], esi
0x18009c1b8  xor     eax, eax
0x18009c1ba  mov     [rsp+408h+var_A0], rax
0x18009c1c2  lea     rax, [rsp+408h+var_1A0]
0x18009c1ca  mov     [rsp+408h+var_98], rax
0x18009c1d2  mov     [rsp+408h+var_90], r14
0x18009c1da  mov     [rsp+408h+var_88], r14
0x18009c1e2  lea     rax, [rsp+408h+var_1A8]
0x18009c1ea  mov     [rsp+408h+var_80], rax
0x18009c1f2  mov     [rsp+408h+var_78], r14
0x18009c1fa  mov     [rsp+408h+var_70], r14d
0x18009c202  lea     rax, [rsp+408h+var_178]
0x18009c20a  mov     [rsp+408h+var_68], rax
0x18009c212  lea     r12, ??_7PreActivationCustomInstallCompletion@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable'
0x18009c219  mov     [rsp+408h+var_1A8], r12
0x18009c221  mov     r8d, [rsp+408h+var_3A8]; unsigned int
0x18009c226  mov     rdx, rbx; unsigned __int16 *
0x18009c229  lea     rcx, [rsp+408h+var_1A8]; this
0x18009c231  call    ?StartActivity@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXPEBGI@Z; DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(ushort const *,uint)
0x18009c236  nop
0x18009c237  mov     rcx, rdi
0x18009c23a  cmp     [rdi+18h], r15
0x18009c23e  jbe     short loc_18009C243
0x18009c240  mov     rcx, [rdi]; unsigned __int16 *
0x18009c243  call    ?IsPackagePreOrderAndNotAvailable@@YA_NPEBG@Z; IsPackagePreOrderAndNotAvailable(ushort const *)
0x18009c248  test    al, al
0x18009c24a  jz      short loc_18009C28F
0x18009c24c  lea     rcx, [rsp+408h+var_1A8]; this
0x18009c254  call    ?PreDownloadLicenseNotYetAvailable@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable(void)
0x18009c259  lea     rcx, [rsp+408h+var_1A8]
0x18009c261  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009c266  nop
0x18009c267  mov     [rsp+408h+var_1A8], r12
0x18009c26f  lea     rcx, [rsp+408h+var_1A8]
0x18009c277  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18009c27c  lea     rcx, [rsp+408h+var_1A8]
0x18009c284  call    ??1?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
0x18009c289  nop
0x18009c28a  jmp     loc_18009CA4E
0x18009c28f  xorps   xmm0, xmm0
0x18009c292  movups  [rsp+408h+var_1C8], xmm0
0x18009c29a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009c2a2  movdqu  [rsp+408h+var_1B8], xmm1
0x18009c2ab  mov     word ptr [rsp+408h+var_1C8], r14w
0x18009c2b4  lea     rax, ??_7?$__func@V_lambda_68ab120a28af3a893520bfd208deb9bd_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_68ab120a28af3a893520bfd208deb9bd_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18009c2bb  mov     [rsp+408h+pExecInfo.hwnd], rax
0x18009c2c3  lea     rax, [rsp+408h+pExecInfo.hwnd]
0x18009c2cb  mov     [rsp+408h+var_2E8], rax
0x18009c2d3  lea     rdx, [rsp+408h+pExecInfo]
0x18009c2db  lea     rcx, [rsp+408h+var_1C8]
0x18009c2e3  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BAA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(std::wstring &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>)
0x18009c2e8  mov     rcx, [rsp+408h]; this
0x18009c2f0  test    eax, eax
0x18009c2f2  js      loc_18009CA7C
0x18009c2f8  lea     rdx, [rsp+408h+var_1C8]
0x18009c300  lea     rcx, [rsp+408h+var_58]
0x18009c308  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009c30d  nop
0x18009c30e  mov     r8, rsi
0x18009c311  lea     rdx, asc_1800D5864; "\\"
0x18009c318  mov     rcx, rax; Src
0x18009c31b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18009c320  xorps   xmm0, xmm0
0x18009c323  movups  xmmword ptr [rsp+408h+lpCommandLine], xmm0
0x18009c32b  xorps   xmm1, xmm1
0x18009c32e  movdqu  [rsp+408h+var_238], xmm1
0x18009c337  movups  xmm0, xmmword ptr [rax]
0x18009c33a  movups  xmmword ptr [rsp+408h+lpCommandLine], xmm0
0x18009c342  movups  xmm1, xmmword ptr [rax+10h]
0x18009c346  movups  [rsp+408h+var_238], xmm1
0x18009c34e  mov     [rax+10h], r14
0x18009c352  mov     [rax+18h], r15
0x18009c356  mov     [rax], r14w
0x18009c35a  mov     r8d, 15h
0x18009c360  lea     rdx, aCustominstalle; "custominstallexec.exe"
0x18009c367  lea     rcx, [rsp+408h+lpCommandLine]; Src
0x18009c36f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18009c374  xorps   xmm0, xmm0
0x18009c377  movups  xmmword ptr [rsp+408h+lpApplicationName], xmm0
0x18009c37f  mov     [rsp+408h+var_258], r14
0x18009c387  mov     [rsp+408h+var_258+8], r14
0x18009c38f  movups  xmm0, xmmword ptr [rax]
0x18009c392  movups  xmmword ptr [rsp+408h+lpApplicationName], xmm0
0x18009c39a  movups  xmm1, xmmword ptr [rax+10h]
0x18009c39e  movups  xmmword ptr [rsp+408h+var_258], xmm1
0x18009c3a6  mov     [rax+10h], r14
0x18009c3aa  mov     [rax+18h], r15
0x18009c3ae  mov     [rax], r14w
0x18009c3b2  lea     rcx, [rsp+408h+lpCommandLine]; void *
0x18009c3ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c3bf  nop
0x18009c3c0  lea     rcx, [rsp+408h+var_58]; void *
0x18009c3c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c3cd  xorps   xmm0, xmm0
0x18009c3d0  movups  [rsp+408h+Src], xmm0
0x18009c3d8  xorps   xmm1, xmm1
0x18009c3db  movdqu  [rsp+408h+var_1D8], xmm1
0x18009c3e4  mov     r8d, 8
0x18009c3ea  lea     rdx, aInstall; "/install"
0x18009c3f1  lea     rcx, [rsp+408h+Src]
0x18009c3f9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009c3fe  nop
0x18009c3ff  mov     r8, rsi
0x18009c402  lea     r12, asc_1800D6984; " "
0x18009c409  mov     rdx, r12
0x18009c40c  lea     rcx, [rsp+408h+Src]; Src
0x18009c414  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18009c419  xorps   xmm0, xmm0
0x18009c41c  movups  [rsp+408h+var_208], xmm0
0x18009c424  xorps   xmm1, xmm1
0x18009c427  movdqu  [rsp+408h+var_1F8], xmm1
0x18009c430  movups  xmm0, xmmword ptr [rax]
0x18009c433  movups  [rsp+408h+var_208], xmm0
0x18009c43b  movups  xmm1, xmmword ptr [rax+10h]
0x18009c43f  movups  [rsp+408h+var_1F8], xmm1
0x18009c447  mov     [rax+10h], r14
0x18009c44b  mov     [rax+18h], r15
0x18009c44f  mov     [rax], r14w
0x18009c453  mov     rdx, rdi
0x18009c456  cmp     [rdi+18h], r15
0x18009c45a  jbe     short loc_18009C45F
0x18009c45c  mov     rdx, [rdi]
0x18009c45f  mov     r8, [rdi+10h]
0x18009c463  lea     rcx, [rsp+408h+var_208]; Src
0x18009c46b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18009c470  xorps   xmm0, xmm0
0x18009c473  movups  [rsp+408h+var_228], xmm0
0x18009c47b  mov     qword ptr [rsp+408h+var_218], r14
0x18009c483  mov     qword ptr [rsp+408h+var_218+8], r14
0x18009c48b  movups  xmm0, xmmword ptr [rax]
0x18009c48e  movups  [rsp+408h+var_228], xmm0
0x18009c496  movups  xmm1, xmmword ptr [rax+10h]
0x18009c49a  movups  [rsp+408h+var_218], xmm1
0x18009c4a2  mov     [rax+10h], r14
0x18009c4a6  mov     [rax+18h], r15
0x18009c4aa  mov     [rax], r14w
0x18009c4ae  lea     rcx, [rsp+408h+var_208]; void *
0x18009c4b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c4bb  nop
0x18009c4bc  lea     rcx, [rsp+408h+Src]; void *
0x18009c4c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009c4c9  mov     r13d, 70h ; 'p'
0x18009c4cf  mov     r8d, r13d; Size
0x18009c4d2  xor     edx, edx; Val
0x18009c4d4  lea     rcx, [rsp+408h+StartupInfo]; void *
0x18009c4dc  call    memset_0
0x18009c4e1  mov     [rsp+408h+StartupInfo.cb], r13d
0x18009c4e9  mov     [rsp+408h+StartupInfo.dwFlags], esi
0x18009c4f0  lea     eax, [r13-6Bh]
0x18009c4f4  mov     [rsp+408h+StartupInfo.wShowWindow], ax
0x18009c4fc  xorps   xmm0, xmm0
0x18009c4ff  xor     eax, eax
0x18009c501  movups  xmmword ptr [rsp+408h+ProcessInformation.hProcess], xmm0
0x18009c509  mov     qword ptr [rsp+408h+ProcessInformation.dwProcessId], rax
0x18009c511  mov     [rsp+408h+hExistingToken], r14
0x18009c519  lea     rcx, [rsp+408h+hExistingToken]
0x18009c521  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009c526  mov     rbx, rax
0x18009c529  call    cs:__imp_GetCurrentThread
0x18009c530  nop     dword ptr [rax+rax+00h]
0x18009c535  mov     r9, rbx; TokenHandle
0x18009c538  mov     r8d, esi; OpenAsSelf
0x18009c53b  lea     edx, [r13-6Eh]; DesiredAccess
0x18009c53f  mov     rcx, rax; ThreadHandle
0x18009c542  call    cs:__imp_OpenThreadToken
0x18009c549  nop     dword ptr [rax+rax+00h]
0x18009c54e  mov     ebx, eax
0x18009c550  test    eax, eax
0x18009c552  jnz     loc_18009C687
0x18009c558  call    cs:__imp_GetLastError
0x18009c55f  nop     dword ptr [rax+rax+00h]
0x18009c564  cmp     eax, 3F0h
0x18009c569  jnz     loc_18009C687
0x18009c56f  lea     rcx, [rsp+408h+hObject]
0x18009c574  call    ??$Make@VSwitchToDesktopImpl@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSwitchToDesktopImpl@@@12@XZ; Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(void)
0x18009c579  mov     rbx, r14
0x18009c57c  lea     rcx, [rsp+408h+var_360]
0x18009c584  cmp     rcx, rax
0x18009c587  jz      short loc_18009C58F
0x18009c589  mov     rbx, [rax]
0x18009c58c  mov     [rax], r14
0x18009c58f  mov     [rsp+408h+Environment], rbx
0x18009c597  mov     rcx, [rsp+408h+hObject]
0x18009c59c  test    rcx, rcx
0x18009c59f  jz      short loc_18009C5B3
0x18009c5a1  mov     [rsp+408h+hObject], r14
0x18009c5a6  mov     rax, [rcx]
0x18009c5a9  mov     rax, [rax+10h]
0x18009c5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c5b2  nop
0x18009c5b3  mov     rcx, [rsp+408h]; this
0x18009c5bb  test    rbx, rbx
0x18009c5be  jz      loc_18009CA91
0x18009c5c4  mov     r8, r13; Size
0x18009c5c7  xor     edx, edx; Val
0x18009c5c9  lea     rcx, [rsp+408h+pExecInfo]; void *
0x18009c5d1  call    memset_0
0x18009c5d6  mov     [rsp+408h+pExecInfo.cbSize], r13d
0x18009c5de  mov     [rsp+408h+pExecInfo.nShow], 5
0x18009c5e9  or      [rsp+408h+pExecInfo.fMask], 8800040h
0x18009c5f4  lea     rax, [rsp+408h+lpApplicationName]
0x18009c5fc  cmp     [rsp+408h+var_258+8], r15
0x18009c604  cmova   rax, [rsp+408h+lpApplicationName]
0x18009c60d  mov     [rsp+408h+pExecInfo.lpFile], rax
0x18009c615  lea     rax, [rsp+408h+var_228]
0x18009c61d  cmp     qword ptr [rsp+408h+var_218+8], r15
0x18009c625  cmova   rax, qword ptr [rsp+408h+var_228]
0x18009c62e  mov     [rsp+408h+pExecInfo.lpParameters], rax
0x18009c636  mov     [rsp+408h+pExecInfo.hInstApp], rbx
0x18009c63e  mov     rsi, [rsp+408h]
0x18009c646  lea     rcx, [rsp+408h+pExecInfo]; pExecInfo
0x18009c64e  call    cs:__imp_ShellExecuteExW
0x18009c655  nop     dword ptr [rax+rax+00h]
0x18009c65a  test    eax, eax
0x18009c65c  jz      loc_18009CAA2
0x18009c662  mov     rax, [rsp+408h+pExecInfo.hProcess]
0x18009c66a  mov     [rsp+408h+ProcessInformation.hProcess], rax
0x18009c672  mov     rax, [rbx]
0x18009c675  mov     rcx, rbx
0x18009c678  mov     rax, [rax+10h]
0x18009c67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c681  nop
0x18009c682  jmp     loc_18009C951
0x18009c687  mov     rcx, [rsp+408h]; this
0x18009c68f  test    ebx, ebx
0x18009c691  jz      loc_18009CAB7
0x18009c697  mov     [rsp+408h+hToken], r14
0x18009c69c  lea     rcx, [rsp+408h+hToken]
0x18009c6a1  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009c6a6  mov     [rsp+408h+phNewToken], rax; phNewToken
0x18009c6ab  mov     [rsp+408h+TokenType], esi; TokenType
0x18009c6af  xor     r9d, r9d; ImpersonationLevel
0x18009c6b2  xor     r8d, r8d; lpTokenAttributes
0x18009c6b5  mov     edx, 2000000h; dwDesiredAccess
0x18009c6ba  mov     rcx, [rsp+408h+hExistingToken]; hExistingToken
0x18009c6c2  call    cs:__imp_DuplicateTokenEx
0x18009c6c9  nop     dword ptr [rax+rax+00h]
0x18009c6ce  mov     rcx, [rsp+408h]; this
0x18009c6d6  test    eax, eax
0x18009c6d8  jz      loc_18009CAC9
0x18009c6de  mov     [rsp+408h+Environment], r14
0x18009c6e6  xor     r8d, r8d; bInherit
0x18009c6e9  mov     rdx, [rsp+408h+hToken]; hToken
0x18009c6ee  lea     rcx, [rsp+408h+Environment]; lpEnvironment
0x18009c6f6  call    cs:__imp_CreateEnvironmentBlock
0x18009c6fd  nop     dword ptr [rax+rax+00h]
0x18009c702  mov     rcx, [rsp+408h]; this
0x18009c70a  test    eax, eax
0x18009c70c  jz      loc_18009CADA
0x18009c712  mov     [rsp+408h+pLevelHandle], r14
0x18009c717  lea     rax, [rsp+408h+pLevelHandle]
0x18009c71c  mov     qword ptr [rsp+408h+var_208], rax
0x18009c724  mov     byte ptr [rsp+408h+var_208+8], sil
0x18009c72c  mov     qword ptr [rsp+408h+TokenType], r14; lpReserved
  ... truncated ...
```
