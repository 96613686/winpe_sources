# JitvLifetimeManager::ShutdownPackage(ushort const *)

- ea: `0x18007ff60`
- end: `0x180080388`
- name: `?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z`
- size: `1064`
- prototype: `void __fastcall(JitvLifetimeManager *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007f040`
- `0x18007f350`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x180014e74`
- `0x1800210fc`
- `0x180032cf0`
- `0x18007c7b0`
- `0x18007e70c`
- `0x18007e974`
- `0x18007ea3c`
- `0x18007ff60`
- `0x180080390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800800bd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800800bd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18008010c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18008010c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008028c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800802ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008028c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800802ac`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmRegisterResources` at `0x180080197`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmRegisterResources` at `0x180080197`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmStartSession` at `0x18008015d`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmStartSession` at `0x18008015d`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmShutdown` at `0x180080213`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmShutdown` at `0x180080213`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmGetList` at `0x1800801e9`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmGetList` at `0x1800801e9`

## pseudocode

```c
void __fastcall JitvLifetimeManager::ShutdownPackage(JitvLifetimeManager *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r8
  _QWORD *v6; // rcx
  int ProcessesInVirtualizationContext; // eax
  void *v8; // rcx
  void *v9; // rcx
  UINT i; // ebx
  const char *v11; // r9
  DWORD ProcessId; // r15d
  const char *v13; // r9
  __int64 v14; // rdx
  DWORD started; // eax
  DWORD v16; // eax
  DWORD List; // eax
  DWORD v18; // eax
  DWORD v19; // ebx
  RM_PROCESS_INFO *__attribute__((__org_arrdim(0,0))) v20; // rcx
  RM_UNIQUE_PROCESS *__attribute__((__org_arrdim(0,0))) v21; // rcx
  unsigned int v22; // eax
  int v23; // edx
  unsigned int lpUserTime; // [rsp+20h] [rbp-E0h]
  unsigned int lpUserTimea; // [rsp+20h] [rbp-E0h]
  unsigned int lpUserTimeb; // [rsp+20h] [rbp-E0h]
  const char *nServices; // [rsp+28h] [rbp-D8h]
  UINT nApplications; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pSessionHandle; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwRebootReasons; // [rsp+50h] [rbp-B0h] BYREF
  UINT pnProcInfoNeeded; // [rsp+54h] [rbp-ACh] BYREF
  RM_UNIQUE_PROCESS *__attribute__((__org_arrdim(0,0))) rgApplications; // [rsp+58h] [rbp-A8h] BYREF
  UINT pnProcInfo; // [rsp+60h] [rbp-A0h] BYREF
  RM_PROCESS_INFO *__attribute__((__org_arrdim(0,0))) rgAffectedApps; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME ExitTime; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  char v38; // [rsp+80h] [rbp-80h]
  struct _FILETIME CreationTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME KernelTime; // [rsp+98h] [rbp-68h] BYREF
  __int128 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-50h]
  _QWORD v44[4]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR strSessionKey[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  nApplications = 0;
  pv = 0;
  v42 = 0;
  v43 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  std::wstring::_Construct<1,unsigned short const *>(&v42, a2, v5);
  GetPackageFamilyNameFromFullName(v44, &v42);
  std::wstring::~wstring(&v42);
  ExitTime = (struct _FILETIME)&pv;
  v37 = 0;
  v38 = 1;
  v6 = v44;
  if ( v44[3] > 7u )
    v6 = (_QWORD *)v44[0];
  ProcessesInVirtualizationContext = GetProcessesInVirtualizationContext(
                                       (__int64)v6,
                                       (__int64)&nApplications,
                                       (__int64)&v37);
  if ( ProcessesInVirtualizationContext < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
      (const char *)(unsigned int)ProcessesInVirtualizationContext,
      lpUserTime);
  if ( v38 )
  {
    v8 = **(void ***)&ExitTime;
    **(_QWORD **)&ExitTime = v37;
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( nApplications )
  {
    wil::make_unique_cotaskmem<_RM_UNIQUE_PROCESS [0]>(&rgApplications, nApplications);
    for ( i = 0; i < nApplications; ++i )
    {
      ProcessId = GetProcessId(*((HANDLE *)pv + i));
      if ( !ProcessId )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          v11);
      CreationTime = 0;
      ExitTime = 0;
      KernelTime = 0;
      UserTime = 0;
      if ( !GetProcessTimes(*((HANDLE *)pv + i), &CreationTime, &ExitTime, &KernelTime, &UserTime) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          v13);
      v14 = i;
      rgApplications[v14].dwProcessId = ProcessId;
      rgApplications[v14].ProcessStartTime = CreationTime;
    }
    pSessionHandle = 0;
    started = RmStartSession(&pSessionHandle, 0, strSessionKey);
    if ( started )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        (const char *)started,
        lpUserTime);
    v16 = RmRegisterResources(pSessionHandle, 0, 0, nApplications, rgApplications, 0, 0);
    if ( v16 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        (const char *)v16,
        lpUserTimea);
    wil::make_unique_cotaskmem<_RM_PROCESS_INFO [0]>(&rgAffectedApps, nApplications);
    pnProcInfo = nApplications;
    pnProcInfoNeeded = 0;
    dwRebootReasons = 0;
    List = RmGetList(pSessionHandle, &pnProcInfoNeeded, &pnProcInfo, rgAffectedApps, &dwRebootReasons);
    if ( List )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        (const char *)List,
        lpUserTimeb);
    if ( dwRebootReasons )
    {
      v22 = wil::verify_hresult(2147942405LL);
      LODWORD(nServices) = v23;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        (const char *)v22,
        (int)"RestartManager cannot shutdown process: %d",
        nServices);
    }
    v18 = RmShutdown(pSessionHandle, 1u, 0);
    if ( v18 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        (const char *)v18,
        lpUserTimeb);
    v19 = pSessionHandle;
    v42 = 0;
    v43 = 0;
    do
      ++v4;
    while ( a2[v4] );
    std::wstring::_Construct<1,unsigned short const *>(&v42, a2, v4);
    *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Try_emplace<std::wstring,>(
                             (char *)this + 152,
                             &ExitTime,
                             &v42)
              + 48LL) = v19;
    std::wstring::~wstring(&v42);
    v20 = rgAffectedApps;
    rgAffectedApps = 0;
    if ( v20 )
      CoTaskMemFree(v20);
    v21 = rgApplications;
    rgApplications = 0;
    if ( v21 )
      CoTaskMemFree(v21);
  }
  std::wstring::~wstring(v44);
  v9 = pv;
  pv = 0;
  if ( v9 )
    CoTaskMemFree(v9);
}

```

## disassembly

```asm
0x18007ff60  mov     [rsp-8+arg_10], rbx
0x18007ff65  push    rbp
0x18007ff66  push    rsi
0x18007ff67  push    rdi
0x18007ff68  push    r12
0x18007ff6a  push    r13
0x18007ff6c  push    r14
0x18007ff6e  push    r15
0x18007ff70  lea     rbp, [rsp-40h]
0x18007ff75  sub     rsp, 140h
0x18007ff7c  mov     rax, cs:__security_cookie
0x18007ff83  xor     rax, rsp
0x18007ff86  mov     [rbp+70h+var_40], rax
0x18007ff8a  mov     r14, rdx
0x18007ff8d  mov     r13, rcx
0x18007ff90  xor     r12d, r12d
0x18007ff93  mov     [rsp+170h+nApplications], r12d
0x18007ff98  mov     [rsp+170h+pv], r12
0x18007ff9d  xorps   xmm0, xmm0
0x18007ffa0  movups  [rbp+70h+var_D0], xmm0
0x18007ffa4  xorps   xmm1, xmm1
0x18007ffa7  movdqu  [rbp+70h+var_C0], xmm1
0x18007ffac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007ffb0  mov     r8, rdi
0x18007ffb3  inc     r8
0x18007ffb6  cmp     [rdx+r8*2], r12w
0x18007ffbb  jnz     short loc_18007FFB3
0x18007ffbd  lea     rcx, [rbp+70h+var_D0]
0x18007ffc1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007ffc6  nop
0x18007ffc7  lea     rdx, [rbp+70h+var_D0]
0x18007ffcb  lea     rcx, [rbp+70h+var_B0]
0x18007ffcf  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x18007ffd4  nop
0x18007ffd5  lea     rcx, [rbp+70h+var_D0]; void *
0x18007ffd9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ffde  lea     rax, [rsp+170h+pv]
0x18007ffe3  mov     qword ptr [rsp+170h+ExitTime.dwLowDateTime], rax
0x18007ffe8  mov     [rsp+170h+var_F8], r12
0x18007ffed  mov     [rbp+70h+var_F0], 1
0x18007fff1  lea     rcx, [rbp+70h+var_B0]
0x18007fff5  cmp     [rbp+70h+var_98], 7
0x18007fffa  cmova   rcx, [rbp+70h+var_B0]
0x18007ffff  lea     r8, [rsp+170h+var_F8]
0x180080004  lea     rdx, [rsp+170h+nApplications]
0x180080009  call    GetProcessesInVirtualizationContext
0x18008000e  mov     rcx, [rbp+78h]; this
0x180080012  test    eax, eax
0x180080014  js      loc_180080305
0x18008001a  cmp     [rbp+70h+var_F0], r12b
0x18008001e  jz      short loc_180080041
0x180080020  mov     rdx, qword ptr [rsp+170h+ExitTime.dwLowDateTime]
0x180080025  mov     rcx, [rdx]; pv
0x180080028  mov     rax, [rsp+170h+var_F8]
0x18008002d  mov     [rdx], rax
0x180080030  test    rcx, rcx
0x180080033  jz      short loc_180080041
0x180080035  call    cs:__imp_CoTaskMemFree
0x18008003c  nop     dword ptr [rax+rax+00h]
0x180080041  mov     eax, [rsp+170h+nApplications]
0x180080045  test    eax, eax
0x180080047  jnz     short loc_180080096
0x180080049  lea     rcx, [rbp+70h+var_B0]; void *
0x18008004d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080052  nop
0x180080053  mov     rcx, [rsp+170h+pv]; pv
0x180080058  mov     [rsp+170h+pv], r12
0x18008005d  test    rcx, rcx
0x180080060  jz      short loc_18008006E
0x180080062  call    cs:__imp_CoTaskMemFree
0x180080069  nop     dword ptr [rax+rax+00h]
0x18008006e  mov     rcx, [rbp+70h+var_40]
0x180080072  xor     rcx, rsp; StackCookie
0x180080075  call    __security_check_cookie
0x18008007a  mov     rbx, [rsp+170h+arg_10]
0x180080082  add     rsp, 140h
0x180080089  pop     r15
0x18008008b  pop     r14
0x18008008d  pop     r13
0x18008008f  pop     r12
0x180080091  pop     rdi
0x180080092  pop     rsi
0x180080093  pop     rbp
0x180080094  retn
0x180080096  mov     rdx, rax
0x180080099  lea     rcx, [rsp+170h+rgApplications]
0x18008009e  call    ??$make_unique_cotaskmem@$$BY0A@U_RM_UNIQUE_PROCESS@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_RM_UNIQUE_PROCESS@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_RM_UNIQUE_PROCESS [0]>(unsigned __int64)
0x1800800a3  nop
0x1800800a4  mov     ebx, r12d
0x1800800a7  cmp     [rsp+170h+nApplications], r12d
0x1800800ac  jbe     loc_18008014D
0x1800800b2  mov     esi, ebx
0x1800800b4  mov     rcx, [rsp+170h+pv]
0x1800800b9  mov     rcx, [rcx+rsi*8]; Process
0x1800800bd  call    cs:__imp_GetProcessId
0x1800800c4  nop     dword ptr [rax+rax+00h]
0x1800800c9  mov     r15d, eax
0x1800800cc  mov     rcx, [rbp+78h]; this
0x1800800d0  test    eax, eax
0x1800800d2  jz      loc_180080344
0x1800800d8  mov     qword ptr [rbp+70h+CreationTime.dwLowDateTime], r12
0x1800800dc  mov     qword ptr [rsp+170h+ExitTime.dwLowDateTime], r12
0x1800800e1  mov     qword ptr [rbp+70h+KernelTime.dwLowDateTime], r12
0x1800800e5  mov     qword ptr [rbp+70h+UserTime.dwLowDateTime], r12
0x1800800e9  mov     r12, [rbp+78h]
0x1800800ed  lea     rax, [rbp+70h+UserTime]
0x1800800f1  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x1800800f6  lea     r9, [rbp+70h+KernelTime]; lpKernelTime
0x1800800fa  lea     r8, [rsp+170h+ExitTime]; lpExitTime
0x1800800ff  lea     rdx, [rbp+70h+CreationTime]; lpCreationTime
0x180080103  mov     rcx, [rsp+170h+pv]
0x180080108  mov     rcx, [rcx+rsi*8]; hProcess
0x18008010c  call    cs:__imp_GetProcessTimes
0x180080113  nop     dword ptr [rax+rax+00h]
0x180080118  test    eax, eax
0x18008011a  jz      loc_18008032F
0x180080120  lea     rdx, [rsi+rsi*2]
0x180080124  mov     rax, [rsp+170h+rgApplications]
0x180080129  mov     [rax+rdx*4], r15d
0x18008012d  mov     rcx, [rsp+170h+rgApplications]
0x180080132  mov     rax, qword ptr [rbp+70h+CreationTime.dwLowDateTime]
0x180080136  mov     [rcx+rdx*4+4], rax
0x18008013b  inc     ebx
0x18008013d  cmp     ebx, [rsp+170h+nApplications]
0x180080141  mov     r12d, 0
0x180080147  jb      loc_1800800B2
0x18008014d  mov     [rsp+170h+pSessionHandle], r12d
0x180080152  lea     r8, [rbp+70h+strSessionKey]; strSessionKey
0x180080156  xor     edx, edx; dwSessionFlags
0x180080158  lea     rcx, [rsp+170h+pSessionHandle]; pSessionHandle
0x18008015d  call    cs:__imp_RmStartSession
0x180080164  nop     dword ptr [rax+rax+00h]
0x180080169  mov     rcx, [rbp+78h]; this
0x18008016d  test    eax, eax
0x18008016f  jnz     loc_18008031A
0x180080175  mov     rax, [rsp+170h+rgApplications]
0x18008017a  mov     [rsp+170h+rgsServiceNames], r12; rgsServiceNames
0x18008017f  mov     dword ptr [rsp+170h+nServices], r12d; nServices
0x180080184  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x180080189  mov     r9d, [rsp+170h+nApplications]; nApplications
0x18008018e  xor     r8d, r8d; rgsFileNames
0x180080191  xor     edx, edx; nFiles
0x180080193  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x180080197  call    cs:__imp_RmRegisterResources
0x18008019e  nop     dword ptr [rax+rax+00h]
0x1800801a3  test    eax, eax
0x1800801a5  jnz     loc_180080356
0x1800801ab  mov     edx, [rsp+170h+nApplications]
0x1800801af  lea     rcx, [rsp+170h+rgAffectedApps]
0x1800801b4  call    ??$make_unique_cotaskmem@$$BY0A@U_RM_PROCESS_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_RM_PROCESS_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_RM_PROCESS_INFO [0]>(unsigned __int64)
0x1800801b9  nop
0x1800801ba  mov     eax, [rsp+170h+nApplications]
0x1800801be  mov     [rsp+170h+pnProcInfo], eax
0x1800801c2  mov     [rsp+170h+pnProcInfoNeeded], r12d
0x1800801c7  mov     [rsp+170h+dwRebootReasons], r12d
0x1800801cc  lea     rax, [rsp+170h+dwRebootReasons]
0x1800801d1  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x1800801d6  mov     r9, [rsp+170h+rgAffectedApps]; rgAffectedApps
0x1800801db  lea     r8, [rsp+170h+pnProcInfo]; pnProcInfo
0x1800801e0  lea     rdx, [rsp+170h+pnProcInfoNeeded]; pnProcInfoNeeded
0x1800801e5  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x1800801e9  call    cs:__imp_RmGetList
0x1800801f0  nop     dword ptr [rax+rax+00h]
0x1800801f5  test    eax, eax
0x1800801f7  jnz     loc_18008036F
0x1800801fd  mov     edx, [rsp+170h+dwRebootReasons]
0x180080201  test    edx, edx
0x180080203  jnz     loc_1800802D2
0x180080209  xor     r8d, r8d; fnStatus
0x18008020c  lea     edx, [rax+1]; lActionFlags
0x18008020f  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x180080213  call    cs:__imp_RmShutdown
0x18008021a  nop     dword ptr [rax+rax+00h]
0x18008021f  mov     rcx, [rbp+78h]; this
0x180080223  test    eax, eax
0x180080225  jnz     loc_1800802BD
0x18008022b  mov     ebx, [rsp+170h+pSessionHandle]
0x18008022f  xorps   xmm0, xmm0
0x180080232  movups  [rbp+70h+var_D0], xmm0
0x180080236  xorps   xmm1, xmm1
0x180080239  movdqu  [rbp+70h+var_C0], xmm1
0x18008023e  inc     rdi
0x180080241  cmp     [r14+rdi*2], r12w
0x180080246  jnz     short loc_18008023E
0x180080248  mov     r8, rdi
0x18008024b  mov     rdx, r14
0x18008024e  lea     rcx, [rbp+70h+var_D0]
0x180080252  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180080257  nop
0x180080258  lea     r8, [rbp+70h+var_D0]
0x18008025c  lea     rdx, [rsp+170h+ExitTime]
0x180080261  lea     rcx, [r13+98h]
0x180080268  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18008026d  mov     rcx, [rax]
0x180080270  mov     [rcx+30h], ebx
0x180080273  lea     rcx, [rbp+70h+var_D0]; void *
0x180080277  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008027c  nop
0x18008027d  mov     rcx, [rsp+170h+rgAffectedApps]; pv
0x180080282  mov     [rsp+170h+rgAffectedApps], r12
0x180080287  test    rcx, rcx
0x18008028a  jz      short loc_180080299
0x18008028c  call    cs:__imp_CoTaskMemFree
0x180080293  nop     dword ptr [rax+rax+00h]
0x180080298  nop
0x180080299  mov     rcx, [rsp+170h+rgApplications]; pv
0x18008029e  mov     [rsp+170h+rgApplications], r12
0x1800802a3  test    rcx, rcx
0x1800802a6  jz      loc_180080049
0x1800802ac  call    cs:__imp_CoTaskMemFree
0x1800802b3  nop     dword ptr [rax+rax+00h]
0x1800802b8  jmp     loc_180080049
0x1800802bd  mov     r9d, eax; char *
0x1800802c0  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800802c7  mov     edx, 47h ; 'G'; void *
0x1800802cc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800802d2  mov     ecx, 80070005h
0x1800802d7  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800802dc  mov     r9d, eax; char *
0x1800802df  mov     rcx, [rbp+78h]; this
0x1800802e3  mov     dword ptr [rsp+170h+nServices], edx; char *
0x1800802e7  lea     rax, aRestartmanager; "RestartManager cannot shutdown process:"...
0x1800802ee  mov     [rsp+170h+lpUserTime], rax; int
0x1800802f3  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800802fa  mov     edx, 4Ch ; 'L'; void *
0x1800802ff  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180080305  mov     r9d, eax; char *
0x180080308  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008030f  mov     edx, 22h ; '"'; void *
0x180080314  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008031a  mov     r9d, eax; char *
0x18008031d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180080324  mov     edx, 3Bh ; ';'; void *
0x180080329  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008032f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180080336  mov     edx, 33h ; '3'; void *
0x18008033b  mov     rcx, r12; this
0x18008033e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180080344  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008034b  mov     edx, 2Dh ; '-'; void *
0x180080350  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180080356  mov     rcx, [rbp+78h]; this
0x18008035a  mov     r9d, eax; char *
0x18008035d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x180080364  mov     edx, 3Dh ; '='; void *
0x180080369  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008036f  mov     rcx, [rbp+78h]; this
0x180080373  mov     r9d, eax; char *
0x180080376  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008037d  mov     edx, 44h ; 'D'; void *
0x180080382  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
