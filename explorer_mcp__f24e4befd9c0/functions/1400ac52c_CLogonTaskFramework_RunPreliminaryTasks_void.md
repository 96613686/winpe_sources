# CLogonTaskFramework::RunPreliminaryTasks(void)

- ea: `0x1400ac52c`
- end: `0x1400acae6`
- name: `?RunPreliminaryTasks@CLogonTaskFramework@@QEAAJXZ`
- size: `1466`
- prototype: `__int64 __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400a4f90`

## callees

- `0x140012594`
- `0x14001b2c8`
- `0x140023118`
- `0x1400283bc`
- `0x140044f90`
- `0x14004856c`
- `0x140082868`
- `0x1400867f4`
- `0x14009ca94`
- `0x1400abbe0`
- `0x1400ac52c`
- `0x1400acaec`
- `0x1400acbf8`
- `0x1400b45b4`
- `0x1400b90bc`
- `0x1400babd0`
- `0x14010e160`
- `0x14010e520`
- `0x14010ed90`
- `0x140119d5c`
- `0x14013af98`
- `0x140142cec`
- `0x140155c50`
- `0x1401a27a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400ac59e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400ac59e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ac5f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ac694`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ac5f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400ac694`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400ac8e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400ac8e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400ac61e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400ac6b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400ac61e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400ac6b4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ac647`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ac6dd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ac647`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ac6dd`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1400aca6f`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1400aca6f`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400aca88`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400aca99`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400aca88`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400aca99`

## string_xrefs

- `0x1400ac661`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac6fb`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac844`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac8b0`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac93d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac9e0`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400ac890`: `FirstLogonOnAadcCompliantInstallation`
- `0x1400ac687`: `FirstLogonTimeOnCurrentInstallation`
- `0x1400ac6d0`: `FirstLogonTimeOnCurrentInstallation`
- `0x1400aca0b`: `AppReadinessGlobalTimeoutMs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogonTaskFramework::RunPreliminaryTasks(CLogonTaskFramework *this)
{
  unsigned int v2; // eax
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // r15
  _DWORD *v8; // r12
  _lambda_83de4cbc0c4501b1c4607aaeb53a90cb_ *v9; // rax
  __int64 result; // rax
  _QWORD *v11; // rbx
  HKEY v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char v16; // r15
  DWORD dwBuildNumber; // ebx
  int v18; // eax
  int DWORD; // eax
  wil::details::in1diag3 *v20; // rcx
  char v21; // bl
  __int64 v22; // rdx
  int v23; // ebx
  char v24; // al
  HANDLE *v25; // rbx
  HANDLE v26; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  struct CLogonTaskFramework *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h] BYREF
  _REASON_CONTEXT Context; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Process[3]; // [rsp+88h] [rbp-78h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  _InterlockedExchange((volatile __int32 *)this + 136, 100);
  *(_QWORD *)&Context.Version = this;
  LOBYTE(Context.Reason.Detailed.LocalizedReasonModule) = 1;
  Process[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    Process,
    0);
  if ( (int)GetSiHostProcessHandle(0x1000u, Process) >= 0 )
    *((_DWORD *)this + 140) = GetProcessId(Process[0]);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Process);
  if ( (*((_DWORD *)this + 54) & 0x800) != 0 )
  {
    FireOOBEMonitorEvent(102);
    LOBYTE(v29) = 1;
    v30 = 0;
    SHRegGetDWORD(
      HKEY_CURRENT_USER,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE",
      L"ExplorerStartCount",
      &v30);
    v5 = v30;
    v31 = v30;
    v32 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    Process[0] = v6;
    v8 = 0;
    if ( v6 )
    {
      Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>(v6);
      *(_QWORD *)v7 = &off_1401E05C0;
      v7[4] = v5;
      Process[0] = 0;
      v8 = v7;
    }
    Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____(Process);
    *(_QWORD *)&v32 = v8;
    v9 = _lambda_83de4cbc0c4501b1c4607aaeb53a90cb_::_lambda_83de4cbc0c4501b1c4607aaeb53a90cb_(
           (_lambda_83de4cbc0c4501b1c4607aaeb53a90cb_ *)Process,
           &v29);
    UserOOBERetryHandler::SetMaxRetriesReachedHandler__lambda_c13a568d67465b69e694c83ccd5e808a___(&v31, v9);
    UserOOBERetryHandler::Retry((UserOOBERetryHandler *)&v31);
    if ( !(_BYTE)v29 )
    {
      UserOOBERetryHandler::~UserOOBERetryHandler((UserOOBERetryHandler *)&v31);
      result = 2147500036LL;
      goto LABEL_48;
    }
    UserOOBERetryHandler::~UserOOBERetryHandler((UserOOBERetryHandler *)&v31);
  }
  else
  {
    if ( RegGetValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
           L"FirstLogonTime",
           8u,
           0,
           0,
           0) == 2 )
    {
      *(_OWORD *)Process = 0;
      GetSystemTime((LPSYSTEMTIME)Process);
      v2 = RegSetKeyValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
             L"FirstLogonTime",
             3u,
             Process,
             0x10u);
      if ( v2 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x309E,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)v2,
          pdwTypea);
    }
    if ( RegGetValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
           L"FirstLogonTimeOnCurrentInstallation",
           8u,
           0,
           0,
           0) == 2 )
    {
      *(_OWORD *)Process = 0;
      GetSystemTime((LPSYSTEMTIME)Process);
      v4 = RegSetKeyValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
             L"FirstLogonTimeOnCurrentInstallation",
             3u,
             Process,
             0x10u);
      v3 = (HKEY)retaddr;
      if ( v4 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x30A5,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)v4,
          pdwType);
    }
  }
  v11 = (_QWORD *)((char *)this + 264);
  if ( (int)SHRegGetQWORD(
              v3,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              L"LogonCount",
              (unsigned __int64 *)this + 33) < 0 )
    *v11 = 0;
  v13 = SHRegSetQWORD(v12, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer", L"LogonCount", ++*v11);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x30AE,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v13,
      pdwType);
  if ( (*((_BYTE *)this + 216) & 2) != 0 )
  {
    SHRegSetBOOL(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer", L"UserSignedIn", 1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_50179255>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_50179255>::GetImpl'::`2'::impl);
  }
  v14 = *((_DWORD *)this + 54);
  if ( (v14 & 2) != 0 && (v14 & 4) == 0 )
  {
    v15 = SHRegSetBOOL(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
            L"FirstLogonOnAadcCompliantInstallation",
            1);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x30C0,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v15,
        pdwType);
  }
  v16 = 0;
  VersionInformation.dwOSVersionInfoSize = 276;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  if ( GetVersionExW(&VersionInformation) )
  {
    dwBuildNumber = VersionInformation.dwBuildNumber;
    LODWORD(Process[0]) = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
                L"LastLogonBuildNumber",
                (unsigned int *)Process) < 0
      || dwBuildNumber != LODWORD(Process[0]) )
    {
      v16 = 1;
      v18 = SHRegSetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
              L"LastLogonBuildNumber",
              VersionInformation.dwBuildNumber);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x72E,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v18,
          pdwType);
    }
  }
  HIDWORD(v29) = 0;
  DWORD = SHRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
            L"UBR",
            (unsigned int *)&v29 + 1);
  v20 = retaddr;
  if ( DWORD < 0 )
  {
    v21 = 0;
    v22 = 12501;
LABEL_37:
    wil::details::in1diag3::_Log_Hr(
      v20,
      (void *)v22,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)DWORD,
      pdwType);
    goto LABEL_38;
  }
  v23 = HIDWORD(v29);
  LODWORD(Process[0]) = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
              L"LastLogonBuildRevision",
              (unsigned int *)Process) >= 0
    && v23 == LODWORD(Process[0]) )
  {
    v21 = 0;
    goto LABEL_38;
  }
  v21 = 1;
  DWORD = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\LogonStats",
            L"LastLogonBuildRevision",
            HIDWORD(v29));
  v20 = retaddr;
  if ( DWORD < 0 )
  {
    v22 = 1857;
    goto LABEL_37;
  }
LABEL_38:
  if ( v16 || (v24 = 0, v21) )
    v24 = 1;
  *((_BYTE *)this + 272) = v24;
  if ( (int)SHRegGetDWORD(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              L"AppReadinessGlobalTimeoutMs",
              (unsigned int *)this + 62) < 0 )
    *((_DWORD *)this + 62) = 420000;
  v25 = (HANDLE *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  Process[0] = v25;
  if ( v25 )
  {
    *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
    Context.Version = 0;
    Context.Flags = 1;
    Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)L"UserSignIn";
    v26 = PowerCreateRequest(&Context);
    *v25 = v26;
    if ( v26 )
    {
      PowerSetRequest(v26, PowerRequestDisplayRequired);
      PowerSetRequest(*v25, PowerRequestSystemRequired);
    }
  }
  else
  {
    v25 = 0;
  }
  *((_QWORD *)this + 28) = v25;
  CLogonTaskFramework::_LaunchFSIAIfNecessary(this);
  result = 0;
LABEL_48:
  _InterlockedExchange((volatile __int32 *)this + 136, 1);
  return result;
}

```

## disassembly

```asm
0x1400ac52c  push    rbp
0x1400ac52e  push    rbx
0x1400ac52f  push    rsi
0x1400ac530  push    rdi
0x1400ac531  push    r12
0x1400ac533  push    r13
0x1400ac535  push    r14
0x1400ac537  push    r15
0x1400ac539  lea     rbp, [rsp-0D8h]
0x1400ac541  sub     rsp, 1D8h
0x1400ac548  mov     rax, cs:__security_cookie
0x1400ac54f  xor     rax, rsp
0x1400ac552  mov     [rbp+110h+var_50], rax
0x1400ac559  mov     rdi, rcx
0x1400ac55c  mov     eax, 64h ; 'd'
0x1400ac561  xchg    eax, [rcx+220h]
0x1400ac567  mov     qword ptr [rsp+210h+Context.Version], rcx
0x1400ac56c  mov     esi, 1
0x1400ac571  mov     byte ptr [rsp+210h+Context.Reason], sil
0x1400ac576  xor     r13d, r13d
0x1400ac579  mov     [rbp+110h+Process], r13
0x1400ac57d  xor     edx, edx
0x1400ac57f  lea     rcx, [rbp+110h+Process]
0x1400ac583  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400ac588  lea     rdx, [rbp+110h+Process]; void **
0x1400ac58c  mov     ecx, 1000h; unsigned int
0x1400ac591  call    ?GetSiHostProcessHandle@@YAJKPEAPEAX@Z; GetSiHostProcessHandle(ulong,void * *)
0x1400ac596  test    eax, eax
0x1400ac598  js      short loc_1400AC5B0
0x1400ac59a  mov     rcx, [rbp+110h+Process]; Process
0x1400ac59e  call    cs:__imp_GetProcessId
0x1400ac5a5  nop     dword ptr [rax+rax+00h]
0x1400ac5aa  mov     [rdi+230h], eax
0x1400ac5b0  lea     rcx, [rbp+110h+Process]
0x1400ac5b4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400ac5b9  lea     r12, aSoftwareMicros_121; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400ac5c0  test    dword ptr [rdi+0D8h], 800h
0x1400ac5ca  jnz     loc_1400AC711
0x1400ac5d0  mov     [rsp+210h+pcbData], r13; pcbData
0x1400ac5d5  mov     [rsp+210h+pvData], r13; pvData
0x1400ac5da  mov     [rsp+210h+pdwType], r13; pdwType
0x1400ac5df  mov     r9d, 8; dwFlags
0x1400ac5e5  lea     r8, aFirstlogontime_0; "FirstLogonTime"
0x1400ac5ec  mov     rdx, r12; lpSubKey
0x1400ac5ef  mov     r14, 0FFFFFFFF80000001h
0x1400ac5f6  mov     rcx, r14; hkey
0x1400ac5f9  call    cs:__imp_RegGetValueW
0x1400ac600  nop     dword ptr [rax+rax+00h]
0x1400ac605  mov     ebx, 10h
0x1400ac60a  lea     r15d, [rbx-0Dh]
0x1400ac60e  cmp     eax, 2
0x1400ac611  jnz     short loc_1400AC672
0x1400ac613  xorps   xmm0, xmm0
0x1400ac616  movups  xmmword ptr [rbp+110h+Process], xmm0
0x1400ac61a  lea     rcx, [rbp+110h+Process]; lpSystemTime
0x1400ac61e  call    cs:__imp_GetSystemTime
0x1400ac625  nop     dword ptr [rax+rax+00h]
0x1400ac62a  mov     dword ptr [rsp+210h+pvData], ebx; cbData
0x1400ac62e  lea     rax, [rbp+110h+Process]
0x1400ac632  mov     [rsp+210h+pdwType], rax; unsigned int
0x1400ac637  mov     r9d, r15d; dwType
0x1400ac63a  lea     r8, aFirstlogontime_0; "FirstLogonTime"
0x1400ac641  mov     rdx, r12; lpSubKey
0x1400ac644  mov     rcx, r14; hKey
0x1400ac647  call    cs:__imp_RegSetKeyValueW
0x1400ac64e  nop     dword ptr [rax+rax+00h]
0x1400ac653  mov     rcx, [rbp+118h]; this
0x1400ac65a  test    eax, eax
0x1400ac65c  jz      short loc_1400AC672
0x1400ac65e  mov     r9d, eax; char *
0x1400ac661  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac668  mov     edx, 309Eh; void *
0x1400ac66d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400ac672  mov     [rsp+210h+pcbData], r13; pcbData
0x1400ac677  mov     [rsp+210h+pvData], r13; pvData
0x1400ac67c  mov     [rsp+210h+pdwType], r13; pdwType
0x1400ac681  mov     r9d, 8; dwFlags
0x1400ac687  lea     r8, aFirstlogontime; "FirstLogonTimeOnCurrentInstallation"
0x1400ac68e  mov     rdx, r12; lpSubKey
0x1400ac691  mov     rcx, r14; hkey
0x1400ac694  call    cs:__imp_RegGetValueW
0x1400ac69b  nop     dword ptr [rax+rax+00h]
0x1400ac6a0  cmp     eax, 2
0x1400ac6a3  jnz     loc_1400AC7FA
0x1400ac6a9  xorps   xmm0, xmm0
0x1400ac6ac  movups  xmmword ptr [rbp+110h+Process], xmm0
0x1400ac6b0  lea     rcx, [rbp+110h+Process]; lpSystemTime
0x1400ac6b4  call    cs:__imp_GetSystemTime
0x1400ac6bb  nop     dword ptr [rax+rax+00h]
0x1400ac6c0  mov     dword ptr [rsp+210h+pvData], ebx; cbData
0x1400ac6c4  lea     rax, [rbp+110h+Process]
0x1400ac6c8  mov     [rsp+210h+pdwType], rax; unsigned int
0x1400ac6cd  mov     r9d, r15d; dwType
0x1400ac6d0  lea     r8, aFirstlogontime; "FirstLogonTimeOnCurrentInstallation"
0x1400ac6d7  mov     rdx, r12; lpSubKey
0x1400ac6da  mov     rcx, r14; hKey
0x1400ac6dd  call    cs:__imp_RegSetKeyValueW
0x1400ac6e4  nop     dword ptr [rax+rax+00h]
0x1400ac6e9  mov     rcx, [rbp+118h]; this
0x1400ac6f0  test    eax, eax
0x1400ac6f2  jz      loc_1400AC7FA
0x1400ac6f8  mov     r9d, eax; char *
0x1400ac6fb  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac702  mov     edx, 30A5h; void *
0x1400ac707  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400ac70c  jmp     loc_1400AC7FA
0x1400ac711  mov     ecx, 66h ; 'f'
0x1400ac716  call    ?FireOOBEMonitorEvent@@YAJW4OOBEMonitorEvent@@@Z; FireOOBEMonitorEvent(OOBEMonitorEvent)
0x1400ac71b  mov     byte ptr [rsp+210h+var_1D0], sil
0x1400ac720  mov     [rsp+210h+var_1C8], r13d
0x1400ac725  lea     r9, [rsp+210h+var_1C8]; unsigned int *
0x1400ac72a  lea     r8, aExplorerstartc; "ExplorerStartCount"
0x1400ac731  lea     rdx, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400ac738  mov     r14, 0FFFFFFFF80000001h
0x1400ac73f  mov     rcx, r14; HKEY
0x1400ac742  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400ac747  mov     ebx, [rsp+210h+var_1C8]
0x1400ac74b  mov     [rsp+210h+var_1C0], ebx
0x1400ac74f  xorps   xmm0, xmm0
0x1400ac752  movdqu  [rsp+210h+var_1B8], xmm0
0x1400ac758  lea     rcx, [rsp+210h+var_1B8]
0x1400ac75d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400ac762  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400ac769  mov     ecx, 18h; unsigned __int64
0x1400ac76e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400ac773  mov     r15, rax
0x1400ac776  mov     [rbp+110h+Process], rax
0x1400ac77a  mov     r12, r13
0x1400ac77d  test    rax, rax
0x1400ac780  jz      short loc_1400AC79F
0x1400ac782  mov     rcx, rax
0x1400ac785  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILambda@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>(void)
0x1400ac78a  lea     rax, off_1401E05C0
0x1400ac791  mov     [r15], rax
0x1400ac794  mov     [r15+10h], ebx
0x1400ac798  mov     [rbp+110h+Process], r13
0x1400ac79c  mov     r12, r15
0x1400ac79f  lea     rcx, [rbp+110h+Process]
0x1400ac7a3  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____
0x1400ac7a8  mov     qword ptr [rsp+210h+var_1B8], r12
0x1400ac7ad  lea     rdx, [rsp+210h+var_1D0]; struct CLogonTaskFramework **
0x1400ac7b2  lea     rcx, [rbp+110h+Process]; this
0x1400ac7b6  call    ??0_lambda_83de4cbc0c4501b1c4607aaeb53a90cb_@@QEAA@AEAPEAVCLogonTaskFramework@@@Z; _lambda_83de4cbc0c4501b1c4607aaeb53a90cb_::_lambda_83de4cbc0c4501b1c4607aaeb53a90cb_(CLogonTaskFramework * &)
0x1400ac7bb  mov     rdx, rax
0x1400ac7be  lea     rcx, [rsp+210h+var_1C0]
0x1400ac7c3  call    UserOOBERetryHandler__SetMaxRetriesReachedHandler__lambda_c13a568d67465b69e694c83ccd5e808a___
0x1400ac7c8  lea     rcx, [rsp+210h+var_1C0]; this
0x1400ac7cd  call    ?Retry@UserOOBERetryHandler@@QEAAJXZ; UserOOBERetryHandler::Retry(void)
0x1400ac7d2  nop
0x1400ac7d3  lea     rcx, [rsp+210h+var_1C0]; this
0x1400ac7d8  cmp     byte ptr [rsp+210h+var_1D0], r13b
0x1400ac7dd  jnz     short loc_1400AC7EE
0x1400ac7df  call    ??1UserOOBERetryHandler@@QEAA@XZ; UserOOBERetryHandler::~UserOOBERetryHandler(void)
0x1400ac7e4  mov     eax, 80004004h
0x1400ac7e9  jmp     loc_1400ACABC
0x1400ac7ee  call    ??1UserOOBERetryHandler@@QEAA@XZ; UserOOBERetryHandler::~UserOOBERetryHandler(void)
0x1400ac7f3  lea     r12, aSoftwareMicros_121; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400ac7fa  lea     rbx, [rdi+108h]
0x1400ac801  mov     r9, rbx; unsigned __int64 *
0x1400ac804  lea     r8, aLogoncount; "LogonCount"
0x1400ac80b  lea     r15, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400ac812  mov     rdx, r15; unsigned __int16 *
0x1400ac815  call    ?SHRegGetQWORD@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; SHRegGetQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x1400ac81a  test    eax, eax
0x1400ac81c  jns     short loc_1400AC821
0x1400ac81e  mov     [rbx], r13
0x1400ac821  add     [rbx], rsi
0x1400ac824  mov     r9, [rbx]; unsigned __int64
0x1400ac827  lea     r8, aLogoncount; "LogonCount"
0x1400ac82e  mov     rdx, r15; unsigned __int16 *
0x1400ac831  call    ?SHRegSetQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z; SHRegSetQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x1400ac836  mov     rcx, [rbp+118h]; this
0x1400ac83d  test    eax, eax
0x1400ac83f  jns     short loc_1400AC855
0x1400ac841  mov     r9d, eax; char *
0x1400ac844  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac84b  mov     edx, 30AEh; void *
0x1400ac850  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ac855  test    byte ptr [rdi+0D8h], 2
0x1400ac85c  jz      short loc_1400AC87F
0x1400ac85e  mov     r9d, esi; int
0x1400ac861  lea     r8, aUsersignedin; "UserSignedIn"
0x1400ac868  mov     rdx, r15; unsigned __int16 *
0x1400ac86b  mov     rcx, r14; HKEY
0x1400ac86e  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400ac873  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50179255@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50179255@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50179255> `wil::Feature<__WilFeatureTraits_Feature_50179255>::GetImpl(void)'::`2'::impl
0x1400ac87a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50179255@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50179255>::__private_IsEnabled(void)
0x1400ac87f  mov     eax, [rdi+0D8h]
0x1400ac885  test    al, 2
0x1400ac887  jz      short loc_1400AC8C1
0x1400ac889  test    al, 4
0x1400ac88b  jnz     short loc_1400AC8C1
0x1400ac88d  mov     r9d, esi; int
0x1400ac890  lea     r8, aFirstlogononaa; "FirstLogonOnAadcCompliantInstallation"
0x1400ac897  mov     rdx, r12; unsigned __int16 *
0x1400ac89a  mov     rcx, r14; HKEY
0x1400ac89d  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400ac8a2  mov     rcx, [rbp+118h]; this
0x1400ac8a9  test    eax, eax
0x1400ac8ab  jns     short loc_1400AC8C1
0x1400ac8ad  mov     r9d, eax; char *
0x1400ac8b0  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac8b7  mov     edx, 30C0h; void *
0x1400ac8bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ac8c1  mov     r15b, r13b
0x1400ac8c4  mov     [rbp+110h+VersionInformation.dwOSVersionInfoSize], 114h
0x1400ac8cb  xor     edx, edx; Val
0x1400ac8cd  mov     r8d, 110h; Size
0x1400ac8d3  lea     rcx, [rbp+110h+VersionInformation.dwMajorVersion]; void *
0x1400ac8d7  call    memset_0
0x1400ac8dc  lea     rcx, [rbp+110h+VersionInformation]; lpVersionInformation
0x1400ac8e0  call    cs:__imp_GetVersionExW
0x1400ac8e7  nop     dword ptr [rax+rax+00h]
0x1400ac8ec  test    eax, eax
0x1400ac8ee  jz      short loc_1400AC94E
0x1400ac8f0  mov     ebx, [rbp+110h+VersionInformation.dwBuildNumber]
0x1400ac8f3  mov     dword ptr [rbp+110h+Process], r13d
0x1400ac8f7  lea     r9, [rbp+110h+Process]; unsigned int *
0x1400ac8fb  lea     r8, aLastlogonbuild; "LastLogonBuildNumber"
0x1400ac902  mov     rdx, r12; unsigned __int16 *
0x1400ac905  mov     rcx, r14; HKEY
0x1400ac908  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400ac90d  test    eax, eax
0x1400ac90f  js      short loc_1400AC916
0x1400ac911  cmp     ebx, dword ptr [rbp+110h+Process]
0x1400ac914  jz      short loc_1400AC94E
0x1400ac916  mov     r15b, sil
0x1400ac919  mov     r9d, [rbp+110h+VersionInformation.dwBuildNumber]; unsigned int
0x1400ac91d  lea     r8, aLastlogonbuild; "LastLogonBuildNumber"
0x1400ac924  mov     rdx, r12; unsigned __int16 *
0x1400ac927  mov     rcx, r14; HKEY
0x1400ac92a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400ac92f  mov     rcx, [rbp+118h]; this
0x1400ac936  test    eax, eax
0x1400ac938  jns     short loc_1400AC94E
0x1400ac93a  mov     r9d, eax; char *
0x1400ac93d  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac944  mov     edx, 72Eh; void *
0x1400ac949  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ac94e  mov     dword ptr [rsp+210h+var_1D0+4], r13d
0x1400ac953  lea     r9, [rsp+210h+var_1D0+4]; unsigned int *
0x1400ac958  lea     r8, aUbr; "UBR"
0x1400ac95f  lea     rdx, aSoftwareMicros_135; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400ac966  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400ac96d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400ac972  mov     rcx, [rbp+118h]
0x1400ac979  test    eax, eax
0x1400ac97b  jns     short loc_1400AC987
0x1400ac97d  mov     bl, r13b
0x1400ac980  mov     edx, 30D5h
0x1400ac985  jmp     short loc_1400AC9DD
0x1400ac987  mov     ebx, dword ptr [rsp+210h+var_1D0+4]
0x1400ac98b  mov     dword ptr [rbp+110h+Process], r13d
0x1400ac98f  lea     r9, [rbp+110h+Process]; unsigned int *
0x1400ac993  lea     r8, aLastlogonbuild_0; "LastLogonBuildRevision"
0x1400ac99a  mov     rdx, r12; unsigned __int16 *
0x1400ac99d  mov     rcx, r14; HKEY
0x1400ac9a0  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400ac9a5  test    eax, eax
0x1400ac9a7  js      short loc_1400AC9B3
0x1400ac9a9  cmp     ebx, dword ptr [rbp+110h+Process]
0x1400ac9ac  jnz     short loc_1400AC9B3
0x1400ac9ae  mov     bl, r13b
0x1400ac9b1  jmp     short loc_1400AC9EC
0x1400ac9b3  mov     bl, sil
0x1400ac9b6  mov     r9d, dword ptr [rsp+210h+var_1D0+4]; unsigned int
0x1400ac9bb  lea     r8, aLastlogonbuild_0; "LastLogonBuildRevision"
0x1400ac9c2  mov     rdx, r12; unsigned __int16 *
0x1400ac9c5  mov     rcx, r14; HKEY
0x1400ac9c8  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400ac9cd  mov     rcx, [rbp+118h]; this
0x1400ac9d4  test    eax, eax
0x1400ac9d6  jns     short loc_1400AC9EC
0x1400ac9d8  mov     edx, 741h; void *
0x1400ac9dd  mov     r9d, eax; char *
0x1400ac9e0  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400ac9e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400ac9ec  test    r15b, r15b
0x1400ac9ef  jnz     short loc_1400AC9F8
0x1400ac9f1  test    bl, bl
0x1400ac9f3  mov     al, r13b
0x1400ac9f6  jz      short loc_1400AC9FB
0x1400ac9f8  mov     al, sil
0x1400ac9fb  mov     [rdi+110h], al
0x1400aca01  lea     rbx, [rdi+0F8h]
0x1400aca08  mov     r9, rbx; unsigned int *
0x1400aca0b  lea     r8, aAppreadinessgl; "AppReadinessGlobalTimeoutMs"
0x1400aca12  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400aca19  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400aca20  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400aca25  test    eax, eax
0x1400aca27  jns     short loc_1400ACA2F
0x1400aca29  mov     dword ptr [rbx], 668A0h
0x1400aca2f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400aca36  mov     ecx, 8; unsigned __int64
0x1400aca3b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400aca40  mov     rbx, rax
0x1400aca43  mov     [rbp+110h+Process], rax
0x1400aca47  test    rax, rax
0x1400aca4a  jz      short loc_1400ACAA7
  ... truncated ...
```
