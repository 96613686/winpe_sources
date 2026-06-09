# DesktopShellHostExtensions::PreInitialize(IShellHostCreationBehavior *)

- ea: `0x180017f00`
- end: `0x180018314`
- name: `?PreInitialize@DesktopShellHostExtensions@@UEAAJPEAUIShellHostCreationBehavior@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(DesktopShellHostExtensions *__hidden this, struct IShellHostCreationBehavior *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009c00`
- `0x18000a558`
- `0x18000f59c`
- `0x1800108cc`
- `0x180017f00`
- `0x18001831c`
- `0x180018348`
- `0x180018624`
- `0x18001870c`
- `0x18001a070`
- `0x18001a18c`
- `0x18002661c`
- `0x18002a3d0`
- `0x18002af50`
- `0x180035c94`
- `0x1800394e0`
- `0x180039bd0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001803d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001803d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018160`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018160`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018051`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800181d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800181d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001819e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001819e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017fcb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017fcb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017f9b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180017f9b`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-0!GetShellWindow` at `0x180017f47`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-0!GetShellWindow` at `0x180017f47`

## string_xrefs

- `0x180017fab`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x180017fde`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800180ee`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800182ab`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800182e7`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800182ff`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x180018100`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DesktopShellHostExtensions::PreInitialize(
        DesktopShellHostExtensions *this,
        struct IShellHostCreationBehavior *a2,
        __int64 a3,
        const char *a4)
{
  struct IShellHostCreationBehavior *v4; // r14
  DesktopShellHostExtensions *v5; // rdi
  HWND ShellWindow; // rsi
  HANDLE v7; // rax
  const char *v8; // r9
  void *v9; // rcx
  unsigned __int64 v10; // rsi
  DesktopShellHostExtensions *v11; // rcx
  void *v12; // rdx
  unsigned int v13; // eax
  int v14; // eax
  GUID *v15; // rsi
  HKEY *v16; // rax
  int v17; // eax
  __int64 *v18; // rsi
  unsigned __int8 (*v19)(void); // rax
  int v20; // eax
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  std::_Ref_count_base *v24; // rcx
  const char *v25; // r9
  int lpUserTime; // [rsp+20h] [rbp-238h]
  DWORD dwProcessId; // [rsp+30h] [rbp-228h] BYREF
  struct _FILETIME CreationTime; // [rsp+38h] [rbp-220h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+40h] [rbp-218h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-208h] BYREF
  struct IShellHostCreationBehavior *v32; // [rsp+58h] [rbp-200h]
  struct _FILETIME UserTime; // [rsp+60h] [rbp-1F8h] BYREF
  struct _FILETIME KernelTime; // [rsp+68h] [rbp-1F0h] BYREF
  struct _FILETIME ExitTime; // [rsp+70h] [rbp-1E8h] BYREF
  DesktopShellHostExtensions *v36; // [rsp+78h] [rbp-1E0h]
  _QWORD v37[42]; // [rsp+80h] [rbp-1D8h] BYREF
  WCHAR SubKey[7]; // [rsp+1D0h] [rbp-88h] BYREF
  _BYTE v39[82]; // [rsp+1DEh] [rbp-7Ah] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  try
  {
    v4 = a2;
    v5 = this;
    v36 = this;
    v32 = a2;
    if ( *((_BYTE *)this + 18) )
    {
      if ( !*((_BYTE *)this + 17) )
      {
        ShellWindow = GetShellWindow();
        if ( ShellWindow )
        {
          wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
          v37[0] = &DesktopShellHostExtensionsTelemetry::TerminateShell::`vftable';
          DesktopShellHostExtensionsTelemetry::TerminateShell::StartActivity((DesktopShellHostExtensionsTelemetry::TerminateShell *)v37);
          dwProcessId = 0;
          if ( !GetWindowThreadProcessId(ShellWindow, &dwProcessId) )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xDF,
              (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
              (const char *)0x80004005LL,
              lpUserTime);
          v7 = OpenProcess(0x101001u, 0, dwProcessId);
          if ( !v7 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xE0,
              (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
              v8);
          wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
            v30,
            v7);
          if ( v30[0] )
            v9 = *(void **)v30[0];
          else
            v9 = 0;
          v10 = 0;
          CreationTime = 0;
          ExitTime = 0;
          KernelTime = 0;
          UserTime = 0;
          if ( GetProcessTimes(v9, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
          {
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            v11 = (DesktopShellHostExtensions *)(*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CreationTime);
            v10 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CreationTime) / 0x2710uLL;
          }
          if ( v30[0] )
            v12 = *(void **)v30[0];
          else
            v12 = 0;
          v13 = DesktopShellHostExtensions::TerminateShellProcessAndBlock(v11, v12);
          DesktopShellHostExtensionsTelemetry::TerminateShell::Stop(
            (DesktopShellHostExtensionsTelemetry::TerminateShell *)v37,
            v10,
            v13);
          std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v30);
          DesktopShellHostExtensionsTelemetry::TerminateShell::~TerminateShell((DesktopShellHostExtensionsTelemetry::TerminateShell *)v37);
        }
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE9,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      a4);
    v5 = v36;
    v4 = v32;
  }
  v14 = (*(__int64 (__fastcall **)(struct IShellHostCreationBehavior *, __int64, GUID *))(*(_QWORD *)v4 + 24LL))(
          v4,
          5,
          &DesktopShellHostExtensions::s_secondaryComponents);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      (const char *)(unsigned int)v14,
      lpUserTime);
  wcscpy(SubKey, L"CLSID\\");
  memset_0(v39, 0, 0x4Eu);
  v15 = &DesktopShellHostExtensions::s_optionalComponents;
  do
  {
    if ( !StringFromGUID2(v15, &SubKey[6], 40) )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
        (const char *)0x80004005LL,
        lpUserTime);
    CreationTime = 0;
    v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&CreationTime);
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, v16) )
    {
      v17 = (*(__int64 (__fastcall **)(struct IShellHostCreationBehavior *, __int64, GUID *))(*(_QWORD *)v4 + 24LL))(
              v4,
              1,
              v15);
      if ( v17 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x118,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
          (const char *)(unsigned int)v17,
          lpUserTime);
    }
    if ( CreationTime )
      RegCloseKey(*(HKEY *)&CreationTime);
    ++v15;
  }
  while ( v15 != (GUID *)&g_header_init_WilInitialize_CppWinRT );
  v18 = qword_1800AC290;
  do
  {
    v19 = (unsigned __int8 (*)(void))v18[2];
    if ( !v19 || v19() )
    {
      v20 = (*(__int64 (__fastcall **)(struct IShellHostCreationBehavior *, __int64, __int64 *))(*(_QWORD *)v4 + 24LL))(
              v4,
              1,
              v18);
      if ( v20 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
          (const char *)(unsigned int)v20,
          lpUserTime);
    }
    v18 += 3;
  }
  while ( v18 != (__int64 *)&wil::details::g_processLocalData );
  if ( !*((_BYTE *)v5 + 16) )
  {
    try
    {
      v21 = (__int64 *)std::make_shared<ShellFeatureRolloutCoordinator,>(v30);
      v22 = *v21;
      v23 = v21[1];
      *v21 = 0;
      v21[1] = 0;
      *((_QWORD *)v5 + 3) = v22;
      v24 = (std::_Ref_count_base *)*((_QWORD *)v5 + 4);
      *((_QWORD *)v5 + 4) = v23;
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
      if ( v30[1] )
        std::_Ref_count_base::_Decref(v30[1]);
      *(_OWORD *)v30 = 0;
      ShellFeatureRolloutCoordinator::Initialize(*((_QWORD *)v5 + 3), v30);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x12D,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
        v25);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017f00  mov     [rsp+arg_10], rsi
0x180017f05  push    rdi
0x180017f06  push    r14
0x180017f08  push    r15
0x180017f0a  sub     rsp, 240h
0x180017f11  mov     rax, cs:__security_cookie
0x180017f18  xor     rax, rsp
0x180017f1b  mov     [rsp+258h+var_28], rax
0x180017f23  mov     r14, rdx
0x180017f26  mov     rdi, rcx
0x180017f29  mov     [rsp+258h+var_1E0], rcx
0x180017f2e  mov     [rsp+258h+var_200], rdx
0x180017f33  cmp     byte ptr [rcx+12h], 0
0x180017f37  jz      loc_1800180B8
0x180017f3d  cmp     byte ptr [rcx+11h], 0
0x180017f41  jnz     loc_1800180B8
0x180017f47  call    cs:__imp_GetShellWindow
0x180017f4d  mov     rsi, rax
0x180017f50  test    rax, rax
0x180017f53  jz      loc_1800180B8
0x180017f59  lea     rcx, [rsp+258h+var_1D8]; struct wil::details::IFailureCallback *
0x180017f61  call    ??0?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017f66  lea     rax, ??_7TerminateShell@DesktopShellHostExtensionsTelemetry@@6B@; const DesktopShellHostExtensionsTelemetry::TerminateShell::`vftable'
0x180017f6d  mov     [rsp+258h+var_1D8], rax
0x180017f75  lea     rcx, [rsp+258h+var_1D8]; this
0x180017f7d  call    ?StartActivity@TerminateShell@DesktopShellHostExtensionsTelemetry@@QEAAXXZ; DesktopShellHostExtensionsTelemetry::TerminateShell::StartActivity(void)
0x180017f82  nop
0x180017f83  mov     [rsp+258h+dwProcessId], 0
0x180017f8b  mov     r15, [rsp+258h]
0x180017f93  lea     rdx, [rsp+258h+dwProcessId]; lpdwProcessId
0x180017f98  mov     rcx, rsi; hWnd
0x180017f9b  call    cs:__imp_GetWindowThreadProcessId
0x180017fa1  test    eax, eax
0x180017fa3  jnz     short loc_180017FBF
0x180017fa5  mov     r9d, 80004005h; char *
0x180017fab  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180017fb2  mov     edx, 0DFh; void *
0x180017fb7  mov     rcx, r15; this
0x180017fba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017fbf  mov     r8d, [rsp+258h+dwProcessId]; dwProcessId
0x180017fc4  xor     edx, edx; bInheritHandle
0x180017fc6  mov     ecx, 101001h; dwDesiredAccess
0x180017fcb  call    cs:__imp_OpenProcess
0x180017fd1  mov     rcx, [rsp+258h]; this
0x180017fd9  test    rax, rax
0x180017fdc  jnz     short loc_180017FEF
0x180017fde  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180017fe5  mov     edx, 0E0h; void *
0x180017fea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180017fef  mov     rdx, rax
0x180017ff2  lea     rcx, [rsp+258h+var_218]
0x180017ff7  call    ??0?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@PEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *)
0x180017ffc  nop
0x180017ffd  mov     rax, [rsp+258h+var_218]
0x180018002  test    rax, rax
0x180018005  jz      short loc_18001800C
0x180018007  mov     rcx, [rax]
0x18001800a  jmp     short loc_18001800E
0x18001800c  xor     ecx, ecx; hProcess
0x18001800e  xor     esi, esi
0x180018010  mov     qword ptr [rsp+258h+CreationTime.dwLowDateTime], rsi
0x180018015  mov     qword ptr [rsp+258h+ExitTime.dwLowDateTime], rsi
0x18001801a  mov     qword ptr [rsp+258h+KernelTime.dwLowDateTime], rsi
0x18001801f  mov     qword ptr [rsp+258h+UserTime.dwLowDateTime], rsi
0x180018024  lea     rax, [rsp+258h+UserTime]
0x180018029  mov     qword ptr [rsp+258h+lpUserTime], rax; lpUserTime
0x18001802e  lea     r9, [rsp+258h+KernelTime]; lpKernelTime
0x180018033  lea     r8, [rsp+258h+ExitTime]; lpExitTime
0x180018038  lea     rdx, [rsp+258h+CreationTime]; lpCreationTime
0x18001803d  call    cs:__imp_GetProcessTimes
0x180018043  test    eax, eax
0x180018045  jz      short loc_180018075
0x180018047  mov     qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18001804c  lea     rcx, [rsp+258h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018051  call    cs:__imp_GetSystemTimeAsFileTime
0x180018057  mov     rcx, qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime]
0x18001805c  sub     rcx, qword ptr [rsp+258h+CreationTime.dwLowDateTime]; this
0x180018061  mov     rax, 346DC5D63886594Bh
0x18001806b  mul     rcx
0x18001806e  mov     rsi, rdx
0x180018071  shr     rsi, 0Bh
0x180018075  mov     rax, [rsp+258h+var_218]
0x18001807a  test    rax, rax
0x18001807d  jz      short loc_180018084
0x18001807f  mov     rdx, [rax]
0x180018082  jmp     short loc_180018086
0x180018084  xor     edx, edx; void *
0x180018086  call    ?TerminateShellProcessAndBlock@DesktopShellHostExtensions@@AEAAKPEAX@Z; DesktopShellHostExtensions::TerminateShellProcessAndBlock(void *)
0x18001808b  mov     r8d, eax; unsigned int
0x18001808e  mov     rdx, rsi; unsigned __int64
0x180018091  lea     rcx, [rsp+258h+var_1D8]; this
0x180018099  call    ?Stop@TerminateShell@DesktopShellHostExtensionsTelemetry@@QEAAX_KK@Z; DesktopShellHostExtensionsTelemetry::TerminateShell::Stop(unsigned __int64,ulong)
0x18001809e  nop
0x18001809f  lea     rcx, [rsp+258h+var_218]
0x1800180a4  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800180a9  nop
0x1800180aa  lea     rcx, [rsp+258h+var_1D8]; this
0x1800180b2  call    ??1TerminateShell@DesktopShellHostExtensionsTelemetry@@QEAA@XZ; DesktopShellHostExtensionsTelemetry::TerminateShell::~TerminateShell(void)
0x1800180b7  nop
0x1800180b8  jmp     short loc_1800180C4
0x1800180ba  mov     rdi, [rsp+258h+var_1E0]
0x1800180bf  mov     r14, [rsp+258h+var_200]
0x1800180c4  mov     rax, [r14]
0x1800180c7  lea     r8, ?s_secondaryComponents@DesktopShellHostExtensions@@0QBU_GUID@@B; _GUID const near * const DesktopShellHostExtensions::s_secondaryComponents
0x1800180ce  mov     edx, 5
0x1800180d3  mov     rcx, r14
0x1800180d6  mov     rax, [rax+18h]
0x1800180da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180df  mov     rcx, [rsp+258h]; this
0x1800180e7  test    eax, eax
0x1800180e9  jns     short loc_180018100
0x1800180eb  mov     r9d, eax; char *
0x1800180ee  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x1800180f5  mov     edx, 0ECh; void *
0x1800180fa  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180018100  movsd   xmm0, qword ptr cs:aClsid; "CLSID\\"
0x180018108  movsd   qword ptr [rsp+258h+SubKey], xmm0
0x180018111  mov     eax, dword ptr cs:aClsid+8; "D\\"
0x180018117  mov     [rsp+258h+var_80], eax
0x18001811e  movzx   eax, word ptr cs:aClsid+0Ch; ""
0x180018125  mov     [rsp+258h+sz], ax
0x18001812d  xor     edx, edx; Val
0x18001812f  lea     r8d, [rdx+4Eh]; Size
0x180018133  lea     rcx, [rsp+258h+var_7A]; void *
0x18001813b  call    memset_0
0x180018140  lea     rsi, ?s_optionalComponents@DesktopShellHostExtensions@@0QBU_GUID@@B; _GUID const near * const DesktopShellHostExtensions::s_optionalComponents
0x180018147  mov     r15, [rsp+258h]
0x18001814f  mov     r8d, 28h ; '('; cchMax
0x180018155  lea     rdx, [rsp+258h+sz]; lpsz
0x18001815d  mov     rcx, rsi; rguid
0x180018160  call    cs:__imp_StringFromGUID2
0x180018166  test    eax, eax
0x180018168  jz      loc_1800182F9
0x18001816e  mov     qword ptr [rsp+258h+CreationTime.dwLowDateTime], 0
0x180018177  lea     rcx, [rsp+258h+CreationTime]
0x18001817c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180018181  mov     qword ptr [rsp+258h+lpUserTime], rax; int
0x180018186  mov     r9d, 20019h; samDesired
0x18001818c  xor     r8d, r8d; ulOptions
0x18001818f  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180018197  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001819e  call    cs:__imp_RegOpenKeyExW
0x1800181a4  test    eax, eax
0x1800181a6  jnz     short loc_1800181CF
0x1800181a8  mov     rax, [r14]
0x1800181ab  mov     r8, rsi
0x1800181ae  mov     edx, 1
0x1800181b3  mov     rcx, r14
0x1800181b6  mov     rax, [rax+18h]
0x1800181ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181bf  mov     rcx, [rsp+258h]; this
0x1800181c7  test    eax, eax
0x1800181c9  js      loc_1800182A8
0x1800181cf  mov     rcx, qword ptr [rsp+258h+CreationTime.dwLowDateTime]; hKey
0x1800181d4  test    rcx, rcx
0x1800181d7  jz      short loc_1800181DF
0x1800181d9  call    cs:__imp_RegCloseKey
0x1800181df  add     rsi, 10h
0x1800181e3  lea     rax, g_header_init_WilInitialize_CppWinRT
0x1800181ea  cmp     rsi, rax
0x1800181ed  jnz     loc_180018147
0x1800181f3  lea     rsi, qword_1800AC290
0x1800181fa  mov     rax, [rsi+10h]
0x1800181fe  test    rax, rax
0x180018201  jz      short loc_18001820C
0x180018203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018208  test    al, al
0x18001820a  jz      short loc_180018233
0x18001820c  mov     rax, [r14]
0x18001820f  mov     r8, rsi
0x180018212  mov     edx, 1
0x180018217  mov     rcx, r14
0x18001821a  mov     rax, [rax+18h]
0x18001821e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018223  mov     rcx, [rsp+258h]; this
0x18001822b  test    eax, eax
0x18001822d  js      loc_1800182E4
0x180018233  add     rsi, 18h
0x180018237  lea     rax, ?g_processLocalData@details@wil@@3V?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@2@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> wil::details::g_processLocalData
0x18001823e  cmp     rsi, rax
0x180018241  jnz     short loc_1800181FA
0x180018243  cmp     byte ptr [rdi+10h], 0
0x180018247  jnz     short loc_1800182BD
0x180018249  lea     rcx, [rsp+258h+var_218]
0x18001824e  call    ??$make_shared@VShellFeatureRolloutCoordinator@@$$V@std@@YA?AV?$shared_ptr@VShellFeatureRolloutCoordinator@@@0@XZ; std::make_shared<ShellFeatureRolloutCoordinator,>(void)
0x180018253  mov     rcx, [rax]
0x180018256  mov     rdx, [rax+8]
0x18001825a  mov     qword ptr [rax], 0
0x180018261  mov     qword ptr [rax+8], 0
0x180018269  mov     [rdi+18h], rcx
0x18001826d  mov     rcx, [rdi+20h]; this
0x180018271  mov     [rdi+20h], rdx
0x180018275  test    rcx, rcx
0x180018278  jz      short loc_18001827F
0x18001827a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001827f  mov     rcx, [rsp+258h+var_218+8]; this
0x180018284  test    rcx, rcx
0x180018287  jz      short loc_18001828E
0x180018289  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001828e  xorps   xmm0, xmm0
0x180018291  movdqu  xmmword ptr [rsp+258h+var_218], xmm0
0x180018297  lea     rdx, [rsp+258h+var_218]
0x18001829c  mov     rcx, [rdi+18h]
0x1800182a0  call    ?Initialize@ShellFeatureRolloutCoordinator@@QEAAXV?$shared_ptr@VRolloutCoordinatorData@@@std@@@Z; ShellFeatureRolloutCoordinator::Initialize(std::shared_ptr<RolloutCoordinatorData>)
0x1800182a5  nop
0x1800182a6  jmp     short loc_1800182BD
0x1800182a8  mov     r9d, eax; char *
0x1800182ab  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x1800182b2  mov     edx, 118h; void *
0x1800182b7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800182bd  xor     eax, eax
0x1800182bf  mov     rcx, [rsp+258h+var_28]
0x1800182c7  xor     rcx, rsp; StackCookie
0x1800182ca  call    __security_check_cookie
0x1800182cf  mov     rsi, [rsp+258h+arg_10]
0x1800182d7  add     rsp, 240h
0x1800182de  pop     r15
0x1800182e0  pop     r14
0x1800182e2  pop     rdi
0x1800182e3  retn
0x1800182e4  mov     r9d, eax; char *
0x1800182e7  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x1800182ee  mov     edx, 120h; void *
0x1800182f3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800182f9  mov     r9d, 80004005h; char *
0x1800182ff  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180018306  mov     edx, 114h; void *
0x18001830b  mov     rcx, r15; this
0x18001830e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
