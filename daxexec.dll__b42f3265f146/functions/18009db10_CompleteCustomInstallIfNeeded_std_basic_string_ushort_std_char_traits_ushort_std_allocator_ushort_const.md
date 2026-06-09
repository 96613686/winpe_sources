# CompleteCustomInstallIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009db10`
- end: `0x18009e47d`
- name: `?CompleteCustomInstallIfNeeded@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2413`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180041d10`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x1800125f4`
- `0x180012ddc`
- `0x180012f3c`
- `0x180012fb8`
- `0x180013320`
- `0x180013510`
- `0x180014ebc`
- `0x180016434`
- `0x180016b18`
- `0x180017aa4`
- `0x180018fc0`
- `0x18001f6a0`
- `0x1800210fc`
- `0x18002bab4`
- `0x180035e2c`
- `0x180073c80`
- `0x180097078`
- `0x18009d82c`
- `0x18009db10`
- `0x18009e4a0`
- `0x18009e638`
- `0x18009ea50`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e273`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009debe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009debe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009de90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009de90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009dea8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009dea8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009e1df`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009e1df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2ec`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009e028`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009e028`
- `USERENV!CreateEnvironmentBlock` at `0x18009e05c`
- `USERENV!CreateEnvironmentBlock` at `0x18009e05c`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18009dfb4`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18009dfb4`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009db60`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009e29a`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009db60`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18009e29a`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009e0a6`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009e0a6`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009e238`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009e238`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009e0e6`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009e0e6`

## string_xrefs

- `0x18009db90`: `PreActivationCustomInstallCompletion`
- `0x18009e38e`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3a0`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3b1`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3c6`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3d8`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3e9`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e3fb`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e40d`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e424`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e43c`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e453`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e46a`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009dd96`: `/install`
- `0x18009dd12`: `custominstallexec.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CompleteCustomInstallIfNeeded(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rdi
  unsigned __int16 *v2; // rdx
  __int64 result; // rax
  const char *v4; // r9
  const unsigned __int16 *v5; // rbx
  const unsigned __int16 *v6; // rcx
  int v7; // ebx
  void *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  void **v12; // rbx
  HANDLE CurrentThread; // rax
  BOOL v14; // ebx
  const char *v15; // r9
  char *v16; // rax
  const char *v17; // r9
  HINSTANCE v18; // rbx
  HANDLE v19; // rcx
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  const char *v22; // r9
  void **phNewToken; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  void **v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  const char *v30; // r9
  void *lpEnvironment; // rbx
  LPCWSTR *v32; // r9
  __int64 v33; // rax
  const WCHAR *v34; // rdx
  const char *v35; // r9
  int EffectivePackageStatusForUser; // eax
  struct _PROCESS_INFORMATION *v37; // rdx
  int TokenType; // [rsp+20h] [rbp-3E8h]
  unsigned int v39; // [rsp+60h] [rbp-3A8h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-3A0h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+70h] [rbp-398h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp-390h] BYREF
  HANDLE hExistingToken; // [rsp+80h] [rbp-388h] BYREF
  LPVOID Environment; // [rsp+88h] [rbp-380h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-378h] BYREF
  char v46; // [rsp+A8h] [rbp-360h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-358h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+120h] [rbp-2E8h] BYREF
  __int128 v49; // [rsp+130h] [rbp-2D8h]
  __int128 Src; // [rsp+140h] [rbp-2C8h] BYREF
  __int128 v51; // [rsp+150h] [rbp-2B8h]
  _OWORD v52[2]; // [rsp+160h] [rbp-2A8h] BYREF
  __int128 v53; // [rsp+180h] [rbp-288h] BYREF
  __int128 v54; // [rsp+190h] [rbp-278h]
  _QWORD v55[4]; // [rsp+1A0h] [rbp-268h] BYREF
  _OWORD v56[2]; // [rsp+1C0h] [rbp-248h] BYREF
  _BYTE v57[32]; // [rsp+1E0h] [rbp-228h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+200h] [rbp-208h] BYREF
  HWND *p_hwnd; // [rsp+270h] [rbp-198h]
  _QWORD v60[42]; // [rsp+280h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v1 = a1;
  v39 = 0;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v2 = a1;
  else
    v2 = *(unsigned __int16 **)a1;
  result = GetEffectivePackageStatusForUser(0, v2, &v39);
  try
  {
    if ( (int)result >= 0 && (v39 & 0x1800000) != 0 )
    {
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v5 = v1;
      else
        v5 = *(const unsigned __int16 **)v1;
      wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v60,
        "PreActivationCustomInstallCompletion");
      v60[0] = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
      DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(
        (DesktopAppXProvider::PreActivationCustomInstallCompletion *)v60,
        v5,
        v39);
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v6 = v1;
      else
        v6 = *(const unsigned __int16 **)v1;
      if ( IsPackagePreOrderAndNotAvailable(v6) )
      {
        DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable((DesktopAppXProvider::PreActivationCustomInstallCompletion *)v60);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v60);
        v60[0] = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v60);
        result = wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(v60);
      }
      else
      {
        v56[0] = 0;
        v56[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v56[0]) = 0;
        pExecInfo.hwnd = (HWND)&wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
        p_hwnd = &pExecInfo.hwnd;
        v7 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(v56, &pExecInfo);
        if ( p_hwnd )
          (*((void (__fastcall **)(HWND *))*p_hwnd + 3))(p_hwnd);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)v7,
            TokenType);
        v8 = (void *)std::wstring::wstring(v57, v56);
        v9 = std::wstring::_Append<unsigned short>(v8);
        Src = 0;
        v51 = 0;
        Src = *(_OWORD *)v9;
        v51 = *(_OWORD *)(v9 + 16);
        *(_QWORD *)(v9 + 16) = 0;
        *(_QWORD *)(v9 + 24) = 7;
        *(_WORD *)v9 = 0;
        v10 = std::wstring::_Append<unsigned short>(&Src);
        *(_OWORD *)lpApplicationName = 0;
        v49 = 0;
        *(_OWORD *)lpApplicationName = *(_OWORD *)v10;
        v49 = *(_OWORD *)(v10 + 16);
        *(_QWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 7;
        *(_WORD *)v10 = 0;
        std::wstring::~wstring(&Src);
        std::wstring::~wstring(v57);
        memset(v52, 0, sizeof(v52));
        std::wstring::_Construct<1,unsigned short const *>(v52, L"/install", 8);
        v11 = std::wstring::_Append<unsigned short>(v52);
        v53 = 0;
        v54 = 0;
        v53 = *(_OWORD *)v11;
        v54 = *(_OWORD *)(v11 + 16);
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 7;
        *(_WORD *)v11 = 0;
        std::operator+<unsigned short>(v55, &v53, v1);
        std::wstring::~wstring(&v53);
        std::wstring::~wstring(v52);
        memset_0(&StartupInfo, 0, 0x70u);
        StartupInfo.cb = 112;
        StartupInfo.dwFlags = 1;
        StartupInfo.wShowWindow = 5;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        hExistingToken = 0;
        v12 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hExistingToken);
        CurrentThread = GetCurrentThread();
        v14 = OpenThreadToken(CurrentThread, 2u, 1, v12);
        if ( v14 || GetLastError() != 1008 )
        {
          if ( !v14 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v15);
          hToken = 0;
          phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hToken);
          if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, phNewToken) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xAA,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v24);
          Environment = 0;
          if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v25);
          pLevelHandle = 0;
          *(_QWORD *)&Src = &pLevelHandle;
          BYTE8(Src) = 1;
          if ( !SaferCreateLevel(1u, 0x20000u, 1u, &pLevelHandle, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xB5,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v26);
          hObject = 0;
          v27 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
          if ( !SaferComputeTokenFromLevel(pLevelHandle, hToken, v27, 0, 0) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v30);
          if ( 0x7FFFFFFFFFFFFFFELL == (_QWORD)v49 )
            std::_Xlen_string();
          lpEnvironment = Environment;
          v32 = lpApplicationName;
          if ( *((_QWORD *)&v49 + 1) > 7u )
            v32 = (LPCWSTR *)lpApplicationName[0];
          std::wstring::wstring(v52, v28, v29, v32, v49, L" ", 1);
          v33 = std::operator+<unsigned short>(v57, v52, v55);
          if ( *(_QWORD *)(v33 + 24) > 7u )
            v33 = *(_QWORD *)v33;
          v34 = (const WCHAR *)lpApplicationName;
          if ( *((_QWORD *)&v49 + 1) > 7u )
            v34 = lpApplicationName[0];
          if ( !CreateProcessAsUserW(
                  hObject,
                  v34,
                  (LPWSTR)v33,
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
              v35);
          std::wstring::~wstring(v57);
          std::wstring::~wstring(v52);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          SaferCloseLevel(pLevelHandle);
          if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hToken);
        }
        else
        {
          v16 = (char *)Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(&hObject);
          v18 = 0;
          if ( &v46 != v16 )
          {
            v18 = *(HINSTANCE *)v16;
            *(_QWORD *)v16 = 0;
          }
          Environment = v18;
          v19 = hObject;
          if ( hObject )
          {
            hObject = 0;
            (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v19 + 16LL))(v19);
          }
          if ( !v18 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x98,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v17);
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          pExecInfo.cbSize = 112;
          pExecInfo.nShow = 5;
          pExecInfo.fMask = 142606400;
          v20 = (const WCHAR *)lpApplicationName;
          if ( *((_QWORD *)&v49 + 1) > 7u )
            v20 = lpApplicationName[0];
          pExecInfo.lpFile = v20;
          v21 = (const WCHAR *)v55;
          if ( v55[3] > 7u )
            v21 = (const WCHAR *)v55[0];
          pExecInfo.lpParameters = v21;
          pExecInfo.hInstApp = v18;
          if ( !ShellExecuteExW(&pExecInfo) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v22);
          ProcessInformation.hProcess = pExecInfo.hProcess;
          (*(void (__fastcall **)(HINSTANCE))(*(_QWORD *)v18 + 16LL))(v18);
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
        EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v1, &v39);
        if ( EffectivePackageStatusForUser < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)EffectivePackageStatusForUser,
            TokenType);
        if ( (v39 & 0x1800000) != 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)0x80004005LL,
            TokenType);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v60);
        if ( (char *)hExistingToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hExistingToken);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v37);
        std::wstring::~wstring(v55);
        std::wstring::~wstring(lpApplicationName);
        std::wstring::~wstring(v56);
        v60[0] = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v60);
        result = wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(v60);
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
0x18009db10  mov     [rsp+arg_8], rbx
0x18009db15  mov     [rsp+arg_10], rsi
0x18009db1a  push    rdi
0x18009db1b  push    r12
0x18009db1d  push    r13
0x18009db1f  push    r14
0x18009db21  push    r15
0x18009db23  sub     rsp, 3E0h
0x18009db2a  mov     rax, cs:__security_cookie
0x18009db31  xor     rax, rsp
0x18009db34  mov     [rsp+408h+var_38], rax
0x18009db3c  mov     rdi, rcx
0x18009db3f  xor     r14d, r14d
0x18009db42  mov     [rsp+408h+var_3A8], r14d
0x18009db47  lea     r15d, [r14+7]
0x18009db4b  cmp     [rcx+18h], r15
0x18009db4f  jbe     short loc_18009DB56
0x18009db51  mov     rdx, [rcx]
0x18009db54  jmp     short loc_18009DB59
0x18009db56  mov     rdx, rdi
0x18009db59  lea     r8, [rsp+408h+var_3A8]
0x18009db5e  xor     ecx, ecx
0x18009db60  call    cs:__imp_GetEffectivePackageStatusForUser
0x18009db67  nop     dword ptr [rax+rax+00h]
0x18009db6c  test    eax, eax
0x18009db6e  js      loc_18009E35B
0x18009db74  test    [rsp+408h+var_3A8], 1800000h
0x18009db7c  jz      loc_18009E35B
0x18009db82  cmp     [rdi+18h], r15
0x18009db86  jbe     short loc_18009DB8D
0x18009db88  mov     rbx, [rdi]
0x18009db8b  jmp     short loc_18009DB90
0x18009db8d  mov     rbx, rdi
0x18009db90  lea     rdx, aPreactivationc; "PreActivationCustomInstallCompletion"
0x18009db97  lea     rcx, [rsp+408h+var_188]
0x18009db9f  call    ??0?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009dba4  lea     rsi, ??_7PreActivationCustomInstallCompletion@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable'
0x18009dbab  mov     [rsp+408h+var_188], rsi
0x18009dbb3  mov     r8d, [rsp+408h+var_3A8]; unsigned int
0x18009dbb8  mov     rdx, rbx; unsigned __int16 *
0x18009dbbb  lea     rcx, [rsp+408h+var_188]; this
0x18009dbc3  call    ?StartActivity@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXPEBGI@Z; DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(ushort const *,uint)
0x18009dbc8  nop
0x18009dbc9  cmp     [rdi+18h], r15
0x18009dbcd  jbe     short loc_18009DBD4
0x18009dbcf  mov     rcx, [rdi]
0x18009dbd2  jmp     short loc_18009DBD7
0x18009dbd4  mov     rcx, rdi; unsigned __int16 *
0x18009dbd7  call    ?IsPackagePreOrderAndNotAvailable@@YA_NPEBG@Z; IsPackagePreOrderAndNotAvailable(ushort const *)
0x18009dbdc  test    al, al
0x18009dbde  jz      short loc_18009DC23
0x18009dbe0  lea     rcx, [rsp+408h+var_188]; this
0x18009dbe8  call    ?PreDownloadLicenseNotYetAvailable@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable(void)
0x18009dbed  lea     rcx, [rsp+408h+var_188]
0x18009dbf5  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009dbfa  nop
0x18009dbfb  mov     [rsp+408h+var_188], rsi
0x18009dc03  lea     rcx, [rsp+408h+var_188]
0x18009dc0b  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18009dc10  lea     rcx, [rsp+408h+var_188]
0x18009dc18  call    ??1?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
0x18009dc1d  nop
0x18009dc1e  jmp     loc_18009E35D
0x18009dc23  xorps   xmm0, xmm0
0x18009dc26  movups  [rsp+408h+var_248], xmm0
0x18009dc2e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18009dc36  movdqu  [rsp+408h+var_238], xmm1
0x18009dc3f  mov     word ptr [rsp+408h+var_248], r14w
0x18009dc48  lea     rax, ??_7?$__func@V_lambda_b184ef8228511dea446194ec32405fe9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18009dc4f  mov     [rsp+408h+pExecInfo.hwnd], rax
0x18009dc57  lea     rax, [rsp+408h+pExecInfo.hwnd]
0x18009dc5f  mov     [rsp+408h+var_198], rax
0x18009dc67  lea     rdx, [rsp+408h+pExecInfo]
0x18009dc6f  lea     rcx, [rsp+408h+var_248]
0x18009dc77  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BAA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(std::wstring &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18009dc7c  mov     ebx, eax
0x18009dc7e  mov     rcx, [rsp+408h+var_198]
0x18009dc86  test    rcx, rcx
0x18009dc89  jz      short loc_18009DC97
0x18009dc8b  mov     rdx, [rcx]
0x18009dc8e  mov     rax, [rdx+18h]
0x18009dc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dc97  mov     rcx, [rsp+408h]; this
0x18009dc9f  test    ebx, ebx
0x18009dca1  js      loc_18009E38B
0x18009dca7  lea     rdx, [rsp+408h+var_248]
0x18009dcaf  lea     rcx, [rsp+408h+var_228]
0x18009dcb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009dcbc  nop
0x18009dcbd  mov     esi, 1
0x18009dcc2  mov     r8d, esi
0x18009dcc5  lea     rdx, S; "\\"
0x18009dccc  mov     rcx, rax; Src
0x18009dccf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18009dcd4  xorps   xmm0, xmm0
0x18009dcd7  movups  [rsp+408h+Src], xmm0
0x18009dcdf  xorps   xmm1, xmm1
0x18009dce2  movdqu  [rsp+408h+var_2B8], xmm1
0x18009dceb  movups  xmm0, xmmword ptr [rax]
0x18009dcee  movups  [rsp+408h+Src], xmm0
0x18009dcf6  movups  xmm1, xmmword ptr [rax+10h]
0x18009dcfa  movups  [rsp+408h+var_2B8], xmm1
0x18009dd02  mov     [rax+10h], r14
0x18009dd06  mov     [rax+18h], r15
0x18009dd0a  mov     [rax], r14w
0x18009dd0e  lea     r8d, [rsi+14h]
0x18009dd12  lea     rdx, aCustominstalle; "custominstallexec.exe"
0x18009dd19  lea     rcx, [rsp+408h+Src]; Src
0x18009dd21  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18009dd26  xorps   xmm0, xmm0
0x18009dd29  movups  xmmword ptr [rsp+408h+lpApplicationName], xmm0
0x18009dd31  xorps   xmm1, xmm1
0x18009dd34  movdqu  [rsp+408h+var_2D8], xmm1
0x18009dd3d  movups  xmm0, xmmword ptr [rax]
0x18009dd40  movups  xmmword ptr [rsp+408h+lpApplicationName], xmm0
0x18009dd48  movups  xmm1, xmmword ptr [rax+10h]
0x18009dd4c  movups  [rsp+408h+var_2D8], xmm1
0x18009dd54  mov     [rax+10h], r14
0x18009dd58  mov     [rax+18h], r15
0x18009dd5c  mov     [rax], r14w
0x18009dd60  lea     rcx, [rsp+408h+Src]; void *
0x18009dd68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009dd6d  nop
0x18009dd6e  lea     rcx, [rsp+408h+var_228]; void *
0x18009dd76  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009dd7b  xorps   xmm0, xmm0
0x18009dd7e  movups  [rsp+408h+var_2A8], xmm0
0x18009dd86  xorps   xmm1, xmm1
0x18009dd89  movdqu  [rsp+408h+var_298], xmm1
0x18009dd92  lea     r8d, [rsi+7]
0x18009dd96  lea     rdx, aInstall; "/install"
0x18009dd9d  lea     rcx, [rsp+408h+var_2A8]
0x18009dda5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18009ddaa  nop
0x18009ddab  mov     r8d, esi
0x18009ddae  lea     r12, asc_1800D7C84; " "
0x18009ddb5  mov     rdx, r12
0x18009ddb8  lea     rcx, [rsp+408h+var_2A8]; Src
0x18009ddc0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18009ddc5  xorps   xmm0, xmm0
0x18009ddc8  movups  [rsp+408h+var_288], xmm0
0x18009ddd0  xorps   xmm1, xmm1
0x18009ddd3  movdqu  [rsp+408h+var_278], xmm1
0x18009dddc  movups  xmm0, xmmword ptr [rax]
0x18009dddf  movups  [rsp+408h+var_288], xmm0
0x18009dde7  movups  xmm1, xmmword ptr [rax+10h]
0x18009ddeb  movups  [rsp+408h+var_278], xmm1
0x18009ddf3  mov     [rax+10h], r14
0x18009ddf7  mov     [rax+18h], r15
0x18009ddfb  mov     [rax], r14w
0x18009ddff  mov     r8, rdi
0x18009de02  lea     rdx, [rsp+408h+var_288]
0x18009de0a  lea     rcx, [rsp+408h+var_268]
0x18009de12  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18009de17  nop
0x18009de18  lea     rcx, [rsp+408h+var_288]; void *
0x18009de20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009de25  nop
0x18009de26  lea     rcx, [rsp+408h+var_2A8]; void *
0x18009de2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009de33  lea     r13d, [rsi+6Fh]
0x18009de37  mov     r8d, r13d; Size
0x18009de3a  xor     edx, edx; Val
0x18009de3c  lea     rcx, [rsp+408h+StartupInfo]; void *
0x18009de44  call    memset_0
0x18009de49  mov     [rsp+408h+StartupInfo.cb], r13d
0x18009de51  mov     [rsp+408h+StartupInfo.dwFlags], esi
0x18009de58  lea     eax, [rsi+4]
0x18009de5b  mov     [rsp+408h+StartupInfo.wShowWindow], ax
0x18009de63  xorps   xmm0, xmm0
0x18009de66  xor     eax, eax
0x18009de68  movups  xmmword ptr [rsp+408h+ProcessInformation.hProcess], xmm0
0x18009de70  mov     qword ptr [rsp+408h+ProcessInformation.dwProcessId], rax
0x18009de78  mov     [rsp+408h+hExistingToken], r14
0x18009de80  lea     rcx, [rsp+408h+hExistingToken]
0x18009de88  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009de8d  mov     rbx, rax
0x18009de90  call    cs:__imp_GetCurrentThread
0x18009de97  nop     dword ptr [rax+rax+00h]
0x18009de9c  mov     r9, rbx; TokenHandle
0x18009de9f  mov     r8d, esi; OpenAsSelf
0x18009dea2  lea     edx, [rsi+1]; DesiredAccess
0x18009dea5  mov     rcx, rax; ThreadHandle
0x18009dea8  call    cs:__imp_OpenThreadToken
0x18009deaf  nop     dword ptr [rax+rax+00h]
0x18009deb4  mov     ebx, eax
0x18009deb6  test    eax, eax
0x18009deb8  jnz     loc_18009DFED
0x18009debe  call    cs:__imp_GetLastError
0x18009dec5  nop     dword ptr [rax+rax+00h]
0x18009deca  cmp     eax, 3F0h
0x18009decf  jnz     loc_18009DFED
0x18009ded5  lea     rcx, [rsp+408h+hObject]
0x18009deda  call    ??$Make@VSwitchToDesktopImpl@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSwitchToDesktopImpl@@@12@XZ; Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(void)
0x18009dedf  mov     rbx, r14
0x18009dee2  lea     rcx, [rsp+408h+var_360]
0x18009deea  cmp     rcx, rax
0x18009deed  jz      short loc_18009DEF5
0x18009deef  mov     rbx, [rax]
0x18009def2  mov     [rax], r14
0x18009def5  mov     [rsp+408h+Environment], rbx
0x18009defd  mov     rcx, [rsp+408h+hObject]
0x18009df02  test    rcx, rcx
0x18009df05  jz      short loc_18009DF19
0x18009df07  mov     [rsp+408h+hObject], r14
0x18009df0c  mov     rax, [rcx]
0x18009df0f  mov     rax, [rax+10h]
0x18009df13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009df18  nop
0x18009df19  mov     rcx, [rsp+408h]; this
0x18009df21  test    rbx, rbx
0x18009df24  jz      loc_18009E3A0
0x18009df2a  mov     r8, r13; Size
0x18009df2d  xor     edx, edx; Val
0x18009df2f  lea     rcx, [rsp+408h+pExecInfo]; void *
0x18009df37  call    memset_0
0x18009df3c  mov     [rsp+408h+pExecInfo.cbSize], r13d
0x18009df44  mov     [rsp+408h+pExecInfo.nShow], 5
0x18009df4f  mov     [rsp+408h+pExecInfo.fMask], 8800040h
0x18009df5a  lea     rax, [rsp+408h+lpApplicationName]
0x18009df62  cmp     qword ptr [rsp+408h+var_2D8+8], r15
0x18009df6a  cmova   rax, [rsp+408h+lpApplicationName]
0x18009df73  mov     [rsp+408h+pExecInfo.lpFile], rax
0x18009df7b  lea     rax, [rsp+408h+var_268]
0x18009df83  cmp     [rsp+408h+var_250], r15
0x18009df8b  cmova   rax, [rsp+408h+var_268]
0x18009df94  mov     [rsp+408h+pExecInfo.lpParameters], rax
0x18009df9c  mov     [rsp+408h+pExecInfo.hInstApp], rbx
0x18009dfa4  mov     rsi, [rsp+408h]
0x18009dfac  lea     rcx, [rsp+408h+pExecInfo]; pExecInfo
0x18009dfb4  call    cs:__imp_ShellExecuteExW
0x18009dfbb  nop     dword ptr [rax+rax+00h]
0x18009dfc0  test    eax, eax
0x18009dfc2  jz      loc_18009E3B1
0x18009dfc8  mov     rax, [rsp+408h+pExecInfo.hProcess]
0x18009dfd0  mov     [rsp+408h+ProcessInformation.hProcess], rax
0x18009dfd8  mov     rax, [rbx]
0x18009dfdb  mov     rcx, rbx
0x18009dfde  mov     rax, [rax+10h]
0x18009dfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dfe7  nop
0x18009dfe8  jmp     loc_18009E260
0x18009dfed  mov     rcx, [rsp+408h]; this
0x18009dff5  test    ebx, ebx
0x18009dff7  jz      loc_18009E3C6
0x18009dffd  mov     [rsp+408h+hToken], r14
0x18009e002  lea     rcx, [rsp+408h+hToken]
0x18009e007  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009e00c  mov     [rsp+408h+phNewToken], rax; phNewToken
0x18009e011  mov     [rsp+408h+TokenType], esi; TokenType
0x18009e015  xor     r9d, r9d; ImpersonationLevel
0x18009e018  xor     r8d, r8d; lpTokenAttributes
0x18009e01b  mov     edx, 2000000h; dwDesiredAccess
0x18009e020  mov     rcx, [rsp+408h+hExistingToken]; hExistingToken
0x18009e028  call    cs:__imp_DuplicateTokenEx
0x18009e02f  nop     dword ptr [rax+rax+00h]
0x18009e034  mov     rcx, [rsp+408h]; this
0x18009e03c  test    eax, eax
0x18009e03e  jz      loc_18009E3D8
0x18009e044  mov     [rsp+408h+Environment], r14
0x18009e04c  xor     r8d, r8d; bInherit
0x18009e04f  mov     rdx, [rsp+408h+hToken]; hToken
0x18009e054  lea     rcx, [rsp+408h+Environment]; lpEnvironment
0x18009e05c  call    cs:__imp_CreateEnvironmentBlock
0x18009e063  nop     dword ptr [rax+rax+00h]
0x18009e068  mov     rcx, [rsp+408h]; this
0x18009e070  test    eax, eax
0x18009e072  jz      loc_18009E3E9
0x18009e078  mov     [rsp+408h+pLevelHandle], r14
0x18009e07d  lea     rax, [rsp+408h+pLevelHandle]
0x18009e082  mov     qword ptr [rsp+408h+Src], rax
0x18009e08a  mov     byte ptr [rsp+408h+Src+8], sil
0x18009e092  mov     qword ptr [rsp+408h+TokenType], r14; lpReserved
0x18009e097  lea     r9, [rsp+408h+pLevelHandle]; pLevelHandle
0x18009e09c  mov     r8d, esi; OpenFlags
0x18009e09f  mov     edx, 20000h; dwLevelId
0x18009e0a4  mov     ecx, esi; dwScopeId
0x18009e0a6  call    cs:__imp_SaferCreateLevel
0x18009e0ad  nop     dword ptr [rax+rax+00h]
0x18009e0b2  mov     rcx, [rsp+408h]; this
0x18009e0ba  test    eax, eax
0x18009e0bc  jz      loc_18009E3FB
0x18009e0c2  mov     [rsp+408h+hObject], r14
0x18009e0c7  lea     rcx, [rsp+408h+hObject]
0x18009e0cc  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009e0d1  mov     qword ptr [rsp+408h+TokenType], r14; lpReserved
0x18009e0d6  xor     r9d, r9d; dwFlags
0x18009e0d9  mov     r8, rax; OutAccessToken
0x18009e0dc  mov     rdx, [rsp+408h+hToken]; InAccessToken
0x18009e0e1  mov     rcx, [rsp+408h+pLevelHandle]; LevelHandle
0x18009e0e6  call    cs:__imp_SaferComputeTokenFromLevel
0x18009e0ed  nop     dword ptr [rax+rax+00h]
0x18009e0f2  mov     rcx, [rsp+408h]; this
0x18009e0fa  test    eax, eax
0x18009e0fc  jz      loc_18009E40D
0x18009e102  mov     rcx, qword ptr [rsp+408h+var_2D8]
0x18009e10a  mov     rax, 7FFFFFFFFFFFFFFEh
0x18009e114  sub     rax, rcx
0x18009e117  cmp     rax, rsi
0x18009e11a  jb      loc_18009E41E
  ... truncated ...
```
