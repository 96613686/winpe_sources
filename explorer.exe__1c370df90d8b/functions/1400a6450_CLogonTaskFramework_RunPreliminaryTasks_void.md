# CLogonTaskFramework::RunPreliminaryTasks(void)

- ea: `0x1400a6450`
- end: `0x1400a69c7`
- name: `?RunPreliminaryTasks@CLogonTaskFramework@@QEAAJXZ`
- size: `1399`
- prototype: `__int64 __fastcall(CLogonTaskFramework *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14009bed0`

## callees

- `0x14000edcc`
- `0x1400119c8`
- `0x140011d04`
- `0x14001eba8`
- `0x140030944`
- `0x14003588c`
- `0x14007d1a4`
- `0x14008089c`
- `0x140097378`
- `0x14009c654`
- `0x1400a5afc`
- `0x1400a6450`
- `0x1400a69d0`
- `0x1400a6b10`
- `0x1400ae238`
- `0x1400b4940`
- `0x1401040e0`
- `0x1401044a0`
- `0x140104ce0`
- `0x14010f848`
- `0x14012f27c`
- `0x140136bb8`
- `0x14014b548`
- `0x1401a0560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400a64c2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400a64c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a6517`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a65a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a6517`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a65a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400a67da`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400a67da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400a6536`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400a65ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400a6536`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400a65ba`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400a6559`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400a65dd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400a6559`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400a65dd`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400a6976`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400a6981`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400a6976`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1400a6981`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1400a6963`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1400a6963`

## string_xrefs

- `0x1400a656d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a65f5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a673e`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a67aa`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a6831`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a68d4`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a678a`: `FirstLogonOnAadcCompliantInstallation`
- `0x1400a6593`: `FirstLogonTimeOnCurrentInstallation`
- `0x1400a65d0`: `FirstLogonTimeOnCurrentInstallation`
- `0x1400a68ff`: `AppReadinessGlobalTimeoutMs`

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
  _lambda_d8db511de8b31b52038c5c132d92c4d2_ *v9; // rax
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

  _InterlockedExchange((volatile __int32 *)this + 132, 100);
  *(_QWORD *)&Context.Version = this;
  LOBYTE(Context.Reason.Detailed.LocalizedReasonModule) = 1;
  Process[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    Process,
    0);
  if ( (int)GetSiHostProcessHandle(0x1000u, Process) >= 0 )
    *((_DWORD *)this + 136) = GetProcessId(Process[0]);
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
      *(_QWORD *)v7 = &off_1401E26E8;
      v7[4] = v5;
      Process[0] = 0;
      v8 = v7;
    }
    Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____(Process);
    *(_QWORD *)&v32 = v8;
    v9 = _lambda_d8db511de8b31b52038c5c132d92c4d2_::_lambda_d8db511de8b31b52038c5c132d92c4d2_(
           (_lambda_d8db511de8b31b52038c5c132d92c4d2_ *)Process,
           &v29);
    UserOOBERetryHandler::SetMaxRetriesReachedHandler__lambda_b0d6e1ac98fe1da53b22193afe2f8236___(&v31, v9);
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
          (void *)0x3080,
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
          (void *)0x3087,
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
      (void *)0x3090,
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
        (void *)0x30A2,
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
          (void *)0x72A,
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
    v22 = 12471;
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
    v22 = 1853;
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
  _InterlockedExchange((volatile __int32 *)this + 132, 1);
  return result;
}

```

## disassembly

```asm
0x1400a6450  push    rbp
0x1400a6452  push    rbx
0x1400a6453  push    rsi
0x1400a6454  push    rdi
0x1400a6455  push    r12
0x1400a6457  push    r13
0x1400a6459  push    r14
0x1400a645b  push    r15
0x1400a645d  lea     rbp, [rsp-0D8h]
0x1400a6465  sub     rsp, 1D8h
0x1400a646c  mov     rax, cs:__security_cookie
0x1400a6473  xor     rax, rsp
0x1400a6476  mov     [rbp+110h+var_50], rax
0x1400a647d  mov     rdi, rcx
0x1400a6480  mov     eax, 64h ; 'd'
0x1400a6485  xchg    eax, [rcx+210h]
0x1400a648b  mov     qword ptr [rsp+210h+Context.Version], rcx
0x1400a6490  mov     esi, 1
0x1400a6495  mov     byte ptr [rsp+210h+Context.Reason], sil
0x1400a649a  xor     r13d, r13d
0x1400a649d  mov     [rbp+110h+Process], r13
0x1400a64a1  xor     edx, edx
0x1400a64a3  lea     rcx, [rbp+110h+Process]
0x1400a64a7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400a64ac  lea     rdx, [rbp+110h+Process]; void **
0x1400a64b0  mov     ecx, 1000h; unsigned int
0x1400a64b5  call    ?GetSiHostProcessHandle@@YAJKPEAPEAX@Z; GetSiHostProcessHandle(ulong,void * *)
0x1400a64ba  test    eax, eax
0x1400a64bc  js      short loc_1400A64CE
0x1400a64be  mov     rcx, [rbp+110h+Process]; Process
0x1400a64c2  call    cs:__imp_GetProcessId
0x1400a64c8  mov     [rdi+220h], eax
0x1400a64ce  lea     rcx, [rbp+110h+Process]
0x1400a64d2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400a64d7  lea     r12, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a64de  test    dword ptr [rdi+0D8h], 800h
0x1400a64e8  jnz     loc_1400A660B
0x1400a64ee  mov     [rsp+210h+pcbData], r13; pcbData
0x1400a64f3  mov     [rsp+210h+pvData], r13; pvData
0x1400a64f8  mov     [rsp+210h+pdwType], r13; pdwType
0x1400a64fd  mov     r9d, 8; dwFlags
0x1400a6503  lea     r8, aFirstlogontime_0; "FirstLogonTime"
0x1400a650a  mov     rdx, r12; lpSubKey
0x1400a650d  mov     r14, 0FFFFFFFF80000001h
0x1400a6514  mov     rcx, r14; hkey
0x1400a6517  call    cs:__imp_RegGetValueW
0x1400a651d  mov     ebx, 10h
0x1400a6522  lea     r15d, [rbx-0Dh]
0x1400a6526  cmp     eax, 2
0x1400a6529  jnz     short loc_1400A657E
0x1400a652b  xorps   xmm0, xmm0
0x1400a652e  movups  xmmword ptr [rbp+110h+Process], xmm0
0x1400a6532  lea     rcx, [rbp+110h+Process]; lpSystemTime
0x1400a6536  call    cs:__imp_GetSystemTime
0x1400a653c  mov     dword ptr [rsp+210h+pvData], ebx; cbData
0x1400a6540  lea     rax, [rbp+110h+Process]
0x1400a6544  mov     [rsp+210h+pdwType], rax; unsigned int
0x1400a6549  mov     r9d, r15d; dwType
0x1400a654c  lea     r8, aFirstlogontime_0; "FirstLogonTime"
0x1400a6553  mov     rdx, r12; lpSubKey
0x1400a6556  mov     rcx, r14; hKey
0x1400a6559  call    cs:__imp_RegSetKeyValueW
0x1400a655f  mov     rcx, [rbp+118h]; this
0x1400a6566  test    eax, eax
0x1400a6568  jz      short loc_1400A657E
0x1400a656a  mov     r9d, eax; char *
0x1400a656d  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a6574  mov     edx, 3080h; void *
0x1400a6579  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400a657e  mov     [rsp+210h+pcbData], r13; pcbData
0x1400a6583  mov     [rsp+210h+pvData], r13; pvData
0x1400a6588  mov     [rsp+210h+pdwType], r13; pdwType
0x1400a658d  mov     r9d, 8; dwFlags
0x1400a6593  lea     r8, aFirstlogontime; "FirstLogonTimeOnCurrentInstallation"
0x1400a659a  mov     rdx, r12; lpSubKey
0x1400a659d  mov     rcx, r14; hkey
0x1400a65a0  call    cs:__imp_RegGetValueW
0x1400a65a6  cmp     eax, 2
0x1400a65a9  jnz     loc_1400A66F4
0x1400a65af  xorps   xmm0, xmm0
0x1400a65b2  movups  xmmword ptr [rbp+110h+Process], xmm0
0x1400a65b6  lea     rcx, [rbp+110h+Process]; lpSystemTime
0x1400a65ba  call    cs:__imp_GetSystemTime
0x1400a65c0  mov     dword ptr [rsp+210h+pvData], ebx; cbData
0x1400a65c4  lea     rax, [rbp+110h+Process]
0x1400a65c8  mov     [rsp+210h+pdwType], rax; unsigned int
0x1400a65cd  mov     r9d, r15d; dwType
0x1400a65d0  lea     r8, aFirstlogontime; "FirstLogonTimeOnCurrentInstallation"
0x1400a65d7  mov     rdx, r12; lpSubKey
0x1400a65da  mov     rcx, r14; hKey
0x1400a65dd  call    cs:__imp_RegSetKeyValueW
0x1400a65e3  mov     rcx, [rbp+118h]; this
0x1400a65ea  test    eax, eax
0x1400a65ec  jz      loc_1400A66F4
0x1400a65f2  mov     r9d, eax; char *
0x1400a65f5  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a65fc  mov     edx, 3087h; void *
0x1400a6601  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400a6606  jmp     loc_1400A66F4
0x1400a660b  mov     ecx, 66h ; 'f'
0x1400a6610  call    ?FireOOBEMonitorEvent@@YAJW4OOBEMonitorEvent@@@Z; FireOOBEMonitorEvent(OOBEMonitorEvent)
0x1400a6615  mov     byte ptr [rsp+210h+var_1D0], sil
0x1400a661a  mov     [rsp+210h+var_1C8], r13d
0x1400a661f  lea     r9, [rsp+210h+var_1C8]; unsigned int *
0x1400a6624  lea     r8, aExplorerstartc; "ExplorerStartCount"
0x1400a662b  lea     rdx, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a6632  mov     r14, 0FFFFFFFF80000001h
0x1400a6639  mov     rcx, r14; HKEY
0x1400a663c  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a6641  mov     ebx, [rsp+210h+var_1C8]
0x1400a6645  mov     [rsp+210h+var_1C0], ebx
0x1400a6649  xorps   xmm0, xmm0
0x1400a664c  movdqu  [rsp+210h+var_1B8], xmm0
0x1400a6652  lea     rcx, [rsp+210h+var_1B8]
0x1400a6657  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400a665c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400a6663  mov     ecx, 18h; unsigned __int64
0x1400a6668  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400a666d  mov     r15, rax
0x1400a6670  mov     [rbp+110h+Process], rax
0x1400a6674  mov     r12, r13
0x1400a6677  test    rax, rax
0x1400a667a  jz      short loc_1400A6699
0x1400a667c  mov     rcx, rax
0x1400a667f  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UILambda@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ILambda>(void)
0x1400a6684  lea     rax, off_1401E26E8
0x1400a668b  mov     [r15], rax
0x1400a668e  mov     [r15+10h], ebx
0x1400a6692  mov     [rbp+110h+Process], r13
0x1400a6696  mov     r12, r15
0x1400a6699  lea     rcx, [rbp+110h+Process]
0x1400a669d  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____
0x1400a66a2  mov     qword ptr [rsp+210h+var_1B8], r12
0x1400a66a7  lea     rdx, [rsp+210h+var_1D0]; struct CLogonTaskFramework **
0x1400a66ac  lea     rcx, [rbp+110h+Process]; this
0x1400a66b0  call    ??0_lambda_d8db511de8b31b52038c5c132d92c4d2_@@QEAA@AEAPEAVCLogonTaskFramework@@@Z; _lambda_d8db511de8b31b52038c5c132d92c4d2_::_lambda_d8db511de8b31b52038c5c132d92c4d2_(CLogonTaskFramework * &)
0x1400a66b5  mov     rdx, rax
0x1400a66b8  lea     rcx, [rsp+210h+var_1C0]
0x1400a66bd  call    UserOOBERetryHandler__SetMaxRetriesReachedHandler__lambda_b0d6e1ac98fe1da53b22193afe2f8236___
0x1400a66c2  lea     rcx, [rsp+210h+var_1C0]; this
0x1400a66c7  call    ?Retry@UserOOBERetryHandler@@QEAAJXZ; UserOOBERetryHandler::Retry(void)
0x1400a66cc  nop
0x1400a66cd  lea     rcx, [rsp+210h+var_1C0]; this
0x1400a66d2  cmp     byte ptr [rsp+210h+var_1D0], r13b
0x1400a66d7  jnz     short loc_1400A66E8
0x1400a66d9  call    ??1UserOOBERetryHandler@@QEAA@XZ; UserOOBERetryHandler::~UserOOBERetryHandler(void)
0x1400a66de  mov     eax, 80004004h
0x1400a66e3  jmp     loc_1400A699E
0x1400a66e8  call    ??1UserOOBERetryHandler@@QEAA@XZ; UserOOBERetryHandler::~UserOOBERetryHandler(void)
0x1400a66ed  lea     r12, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a66f4  lea     rbx, [rdi+108h]
0x1400a66fb  mov     r9, rbx; unsigned __int64 *
0x1400a66fe  lea     r8, aLogoncount; "LogonCount"
0x1400a6705  lea     r15, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a670c  mov     rdx, r15; unsigned __int16 *
0x1400a670f  call    ?SHRegGetQWORD@@YAJPEAUHKEY__@@PEBG1PEA_K@Z; SHRegGetQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64 *)
0x1400a6714  test    eax, eax
0x1400a6716  jns     short loc_1400A671B
0x1400a6718  mov     [rbx], r13
0x1400a671b  add     [rbx], rsi
0x1400a671e  mov     r9, [rbx]; unsigned __int64
0x1400a6721  lea     r8, aLogoncount; "LogonCount"
0x1400a6728  mov     rdx, r15; unsigned __int16 *
0x1400a672b  call    ?SHRegSetQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z; SHRegSetQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x1400a6730  mov     rcx, [rbp+118h]; this
0x1400a6737  test    eax, eax
0x1400a6739  jns     short loc_1400A674F
0x1400a673b  mov     r9d, eax; char *
0x1400a673e  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a6745  mov     edx, 3090h; void *
0x1400a674a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a674f  test    byte ptr [rdi+0D8h], 2
0x1400a6756  jz      short loc_1400A6779
0x1400a6758  mov     r9d, esi; int
0x1400a675b  lea     r8, aUsersignedin; "UserSignedIn"
0x1400a6762  mov     rdx, r15; unsigned __int16 *
0x1400a6765  mov     rcx, r14; HKEY
0x1400a6768  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400a676d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50179255@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50179255@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50179255> `wil::Feature<__WilFeatureTraits_Feature_50179255>::GetImpl(void)'::`2'::impl
0x1400a6774  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50179255@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50179255>::__private_IsEnabled(void)
0x1400a6779  mov     eax, [rdi+0D8h]
0x1400a677f  test    al, 2
0x1400a6781  jz      short loc_1400A67BB
0x1400a6783  test    al, 4
0x1400a6785  jnz     short loc_1400A67BB
0x1400a6787  mov     r9d, esi; int
0x1400a678a  lea     r8, aFirstlogononaa; "FirstLogonOnAadcCompliantInstallation"
0x1400a6791  mov     rdx, r12; unsigned __int16 *
0x1400a6794  mov     rcx, r14; HKEY
0x1400a6797  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400a679c  mov     rcx, [rbp+118h]; this
0x1400a67a3  test    eax, eax
0x1400a67a5  jns     short loc_1400A67BB
0x1400a67a7  mov     r9d, eax; char *
0x1400a67aa  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a67b1  mov     edx, 30A2h; void *
0x1400a67b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a67bb  mov     r15b, r13b
0x1400a67be  mov     [rbp+110h+VersionInformation.dwOSVersionInfoSize], 114h
0x1400a67c5  xor     edx, edx; Val
0x1400a67c7  mov     r8d, 110h; Size
0x1400a67cd  lea     rcx, [rbp+110h+VersionInformation.dwMajorVersion]; void *
0x1400a67d1  call    memset_0
0x1400a67d6  lea     rcx, [rbp+110h+VersionInformation]; lpVersionInformation
0x1400a67da  call    cs:__imp_GetVersionExW
0x1400a67e0  test    eax, eax
0x1400a67e2  jz      short loc_1400A6842
0x1400a67e4  mov     ebx, [rbp+110h+VersionInformation.dwBuildNumber]
0x1400a67e7  mov     dword ptr [rbp+110h+Process], r13d
0x1400a67eb  lea     r9, [rbp+110h+Process]; unsigned int *
0x1400a67ef  lea     r8, aLastlogonbuild; "LastLogonBuildNumber"
0x1400a67f6  mov     rdx, r12; unsigned __int16 *
0x1400a67f9  mov     rcx, r14; HKEY
0x1400a67fc  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a6801  test    eax, eax
0x1400a6803  js      short loc_1400A680A
0x1400a6805  cmp     ebx, dword ptr [rbp+110h+Process]
0x1400a6808  jz      short loc_1400A6842
0x1400a680a  mov     r15b, sil
0x1400a680d  mov     r9d, [rbp+110h+VersionInformation.dwBuildNumber]; unsigned int
0x1400a6811  lea     r8, aLastlogonbuild; "LastLogonBuildNumber"
0x1400a6818  mov     rdx, r12; unsigned __int16 *
0x1400a681b  mov     rcx, r14; HKEY
0x1400a681e  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400a6823  mov     rcx, [rbp+118h]; this
0x1400a682a  test    eax, eax
0x1400a682c  jns     short loc_1400A6842
0x1400a682e  mov     r9d, eax; char *
0x1400a6831  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a6838  mov     edx, 72Ah; void *
0x1400a683d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a6842  mov     dword ptr [rsp+210h+var_1D0+4], r13d
0x1400a6847  lea     r9, [rsp+210h+var_1D0+4]; unsigned int *
0x1400a684c  lea     r8, aUbr; "UBR"
0x1400a6853  lea     rdx, aSoftwareMicros_134; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400a685a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400a6861  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a6866  mov     rcx, [rbp+118h]
0x1400a686d  test    eax, eax
0x1400a686f  jns     short loc_1400A687B
0x1400a6871  mov     bl, r13b
0x1400a6874  mov     edx, 30B7h
0x1400a6879  jmp     short loc_1400A68D1
0x1400a687b  mov     ebx, dword ptr [rsp+210h+var_1D0+4]
0x1400a687f  mov     dword ptr [rbp+110h+Process], r13d
0x1400a6883  lea     r9, [rbp+110h+Process]; unsigned int *
0x1400a6887  lea     r8, aLastlogonbuild_0; "LastLogonBuildRevision"
0x1400a688e  mov     rdx, r12; unsigned __int16 *
0x1400a6891  mov     rcx, r14; HKEY
0x1400a6894  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a6899  test    eax, eax
0x1400a689b  js      short loc_1400A68A7
0x1400a689d  cmp     ebx, dword ptr [rbp+110h+Process]
0x1400a68a0  jnz     short loc_1400A68A7
0x1400a68a2  mov     bl, r13b
0x1400a68a5  jmp     short loc_1400A68E0
0x1400a68a7  mov     bl, sil
0x1400a68aa  mov     r9d, dword ptr [rsp+210h+var_1D0+4]; unsigned int
0x1400a68af  lea     r8, aLastlogonbuild_0; "LastLogonBuildRevision"
0x1400a68b6  mov     rdx, r12; unsigned __int16 *
0x1400a68b9  mov     rcx, r14; HKEY
0x1400a68bc  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400a68c1  mov     rcx, [rbp+118h]; this
0x1400a68c8  test    eax, eax
0x1400a68ca  jns     short loc_1400A68E0
0x1400a68cc  mov     edx, 73Dh; void *
0x1400a68d1  mov     r9d, eax; char *
0x1400a68d4  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a68db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a68e0  test    r15b, r15b
0x1400a68e3  jnz     short loc_1400A68EC
0x1400a68e5  test    bl, bl
0x1400a68e7  mov     al, r13b
0x1400a68ea  jz      short loc_1400A68EF
0x1400a68ec  mov     al, sil
0x1400a68ef  mov     [rdi+110h], al
0x1400a68f5  lea     rbx, [rdi+0F8h]
0x1400a68fc  mov     r9, rbx; unsigned int *
0x1400a68ff  lea     r8, aAppreadinessgl; "AppReadinessGlobalTimeoutMs"
0x1400a6906  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a690d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400a6914  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a6919  test    eax, eax
0x1400a691b  jns     short loc_1400A6923
0x1400a691d  mov     dword ptr [rbx], 668A0h
0x1400a6923  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400a692a  mov     ecx, 8; unsigned __int64
0x1400a692f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400a6934  mov     rbx, rax
0x1400a6937  mov     [rbp+110h+Process], rax
0x1400a693b  test    rax, rax
0x1400a693e  jz      short loc_1400A6989
0x1400a6940  xorps   xmm0, xmm0
0x1400a6943  movdqu  xmmword ptr [rsp+210h+Context.Reason+8], xmm0
0x1400a6949  mov     [rsp+210h+Context.Version], r13d
0x1400a694e  mov     [rsp+210h+Context.Flags], esi
0x1400a6952  lea     rax, aUsersignin; "UserSignIn"
0x1400a6959  mov     qword ptr [rsp+210h+Context.Reason], rax
0x1400a695e  lea     rcx, [rsp+210h+Context]; Context
0x1400a6963  call    cs:__imp_PowerCreateRequest
  ... truncated ...
```
