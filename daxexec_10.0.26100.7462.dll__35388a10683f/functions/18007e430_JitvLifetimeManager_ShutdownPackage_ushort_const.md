# JitvLifetimeManager::ShutdownPackage(ushort const *)

- ea: `0x18007e430`
- end: `0x18007e858`
- name: `?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z`
- size: `1064`
- prototype: `void __fastcall(JitvLifetimeManager *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18007d540`
- `0x18007d840`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180013100`
- `0x18002031c`
- `0x18003112c`
- `0x18007ac10`
- `0x18007cbe4`
- `0x18007ce58`
- `0x18007cf20`
- `0x18007e430`
- `0x18007e860`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18007e5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18007e5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007e58d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18007e58d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e784`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmRegisterResources` at `0x18007e667`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmRegisterResources` at `0x18007e667`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmStartSession` at `0x18007e62d`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmStartSession` at `0x18007e62d`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmShutdown` at `0x18007e6eb`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmShutdown` at `0x18007e6eb`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmGetList` at `0x18007e6bd`
- `ext-ms-win-base-rstrtmgr-l1-1-0!RmGetList` at `0x18007e6bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
  ProcessesInVirtualizationContext = GetProcessesInVirtualizationContext(v6, &nApplications, &v37);
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
0x18007e430  mov     [rsp-8+arg_10], rbx
0x18007e435  push    rbp
0x18007e436  push    rsi
0x18007e437  push    rdi
0x18007e438  push    r12
0x18007e43a  push    r13
0x18007e43c  push    r14
0x18007e43e  push    r15
0x18007e440  lea     rbp, [rsp-40h]
0x18007e445  sub     rsp, 140h
0x18007e44c  mov     rax, cs:__security_cookie
0x18007e453  xor     rax, rsp
0x18007e456  mov     [rbp+70h+var_40], rax
0x18007e45a  mov     r14, rdx
0x18007e45d  mov     r13, rcx
0x18007e460  xor     r12d, r12d
0x18007e463  mov     [rsp+170h+nApplications], r12d
0x18007e468  mov     [rsp+170h+pv], r12
0x18007e46d  xorps   xmm0, xmm0
0x18007e470  movups  [rbp+70h+var_D0], xmm0
0x18007e474  xorps   xmm1, xmm1
0x18007e477  movdqu  [rbp+70h+var_C0], xmm1
0x18007e47c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007e480  mov     r8, rdi
0x18007e483  inc     r8
0x18007e486  cmp     [rdx+r8*2], r12w
0x18007e48b  jnz     short loc_18007E483
0x18007e48d  lea     rcx, [rbp+70h+var_D0]
0x18007e491  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e496  nop
0x18007e497  lea     rdx, [rbp+70h+var_D0]
0x18007e49b  lea     rcx, [rbp+70h+var_B0]
0x18007e49f  call    ?GetPackageFamilyNameFromFullName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; GetPackageFamilyNameFromFullName(std::wstring const &)
0x18007e4a4  nop
0x18007e4a5  lea     rcx, [rbp+70h+var_D0]; void *
0x18007e4a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e4ae  lea     rax, [rsp+170h+pv]
0x18007e4b3  mov     qword ptr [rsp+170h+ExitTime.dwLowDateTime], rax
0x18007e4b8  mov     [rsp+170h+var_F8], r12
0x18007e4bd  mov     [rbp+70h+var_F0], 1
0x18007e4c1  lea     rcx, [rbp+70h+var_B0]
0x18007e4c5  cmp     [rbp+70h+var_98], 7
0x18007e4ca  cmova   rcx, [rbp+70h+var_B0]
0x18007e4cf  lea     r8, [rsp+170h+var_F8]
0x18007e4d4  lea     rdx, [rsp+170h+nApplications]
0x18007e4d9  call    GetProcessesInVirtualizationContext
0x18007e4de  mov     rcx, [rbp+78h]; this
0x18007e4e2  test    eax, eax
0x18007e4e4  js      loc_18007E7DD
0x18007e4ea  cmp     [rbp+70h+var_F0], r12b
0x18007e4ee  jz      short loc_18007E511
0x18007e4f0  mov     rdx, qword ptr [rsp+170h+ExitTime.dwLowDateTime]
0x18007e4f5  mov     rcx, [rdx]; pv
0x18007e4f8  mov     rax, [rsp+170h+var_F8]
0x18007e4fd  mov     [rdx], rax
0x18007e500  test    rcx, rcx
0x18007e503  jz      short loc_18007E511
0x18007e505  call    cs:__imp_CoTaskMemFree
0x18007e50c  nop     dword ptr [rax+rax+00h]
0x18007e511  mov     eax, [rsp+170h+nApplications]
0x18007e515  test    eax, eax
0x18007e517  jnz     short loc_18007E566
0x18007e519  lea     rcx, [rbp+70h+var_B0]; void *
0x18007e51d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e522  nop
0x18007e523  mov     rcx, [rsp+170h+pv]; pv
0x18007e528  mov     [rsp+170h+pv], r12
0x18007e52d  test    rcx, rcx
0x18007e530  jz      short loc_18007E53E
0x18007e532  call    cs:__imp_CoTaskMemFree
0x18007e539  nop     dword ptr [rax+rax+00h]
0x18007e53e  mov     rcx, [rbp+70h+var_40]
0x18007e542  xor     rcx, rsp; StackCookie
0x18007e545  call    __security_check_cookie
0x18007e54a  mov     rbx, [rsp+170h+arg_10]
0x18007e552  add     rsp, 140h
0x18007e559  pop     r15
0x18007e55b  pop     r14
0x18007e55d  pop     r13
0x18007e55f  pop     r12
0x18007e561  pop     rdi
0x18007e562  pop     rsi
0x18007e563  pop     rbp
0x18007e564  retn
0x18007e566  mov     rdx, rax
0x18007e569  lea     rcx, [rsp+170h+rgApplications]
0x18007e56e  call    ??$make_unique_cotaskmem@$$BY0A@U_RM_UNIQUE_PROCESS@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_RM_UNIQUE_PROCESS@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_RM_UNIQUE_PROCESS [0]>(unsigned __int64)
0x18007e573  nop
0x18007e574  mov     ebx, r12d
0x18007e577  cmp     [rsp+170h+nApplications], r12d
0x18007e57c  jbe     loc_18007E61D
0x18007e582  mov     esi, ebx
0x18007e584  mov     rcx, [rsp+170h+pv]
0x18007e589  mov     rcx, [rcx+rsi*8]; Process
0x18007e58d  call    cs:__imp_GetProcessId
0x18007e594  nop     dword ptr [rax+rax+00h]
0x18007e599  mov     r15d, eax
0x18007e59c  mov     rcx, [rbp+78h]; this
0x18007e5a0  test    eax, eax
0x18007e5a2  jz      loc_18007E81C
0x18007e5a8  mov     qword ptr [rbp+70h+CreationTime.dwLowDateTime], r12
0x18007e5ac  mov     qword ptr [rsp+170h+ExitTime.dwLowDateTime], r12
0x18007e5b1  mov     qword ptr [rbp+70h+KernelTime.dwLowDateTime], r12
0x18007e5b5  mov     qword ptr [rbp+70h+UserTime.dwLowDateTime], r12
0x18007e5b9  mov     r12, [rbp+78h]
0x18007e5bd  lea     rax, [rbp+70h+UserTime]
0x18007e5c1  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x18007e5c6  lea     r9, [rbp+70h+KernelTime]; lpKernelTime
0x18007e5ca  lea     r8, [rsp+170h+ExitTime]; lpExitTime
0x18007e5cf  lea     rdx, [rbp+70h+CreationTime]; lpCreationTime
0x18007e5d3  mov     rcx, [rsp+170h+pv]
0x18007e5d8  mov     rcx, [rcx+rsi*8]; hProcess
0x18007e5dc  call    cs:__imp_GetProcessTimes
0x18007e5e3  nop     dword ptr [rax+rax+00h]
0x18007e5e8  test    eax, eax
0x18007e5ea  jz      loc_18007E807
0x18007e5f0  lea     rdx, [rsi+rsi*2]
0x18007e5f4  mov     rax, [rsp+170h+rgApplications]
0x18007e5f9  mov     [rax+rdx*4], r15d
0x18007e5fd  mov     rcx, [rsp+170h+rgApplications]
0x18007e602  mov     rax, qword ptr [rbp+70h+CreationTime.dwLowDateTime]
0x18007e606  mov     [rcx+rdx*4+4], rax
0x18007e60b  inc     ebx
0x18007e60d  cmp     ebx, [rsp+170h+nApplications]
0x18007e611  mov     r12d, 0
0x18007e617  jb      loc_18007E582
0x18007e61d  mov     [rsp+170h+pSessionHandle], r12d
0x18007e622  lea     r8, [rbp+70h+strSessionKey]; strSessionKey
0x18007e626  xor     edx, edx; dwSessionFlags
0x18007e628  lea     rcx, [rsp+170h+pSessionHandle]; pSessionHandle
0x18007e62d  call    cs:__imp_RmStartSession
0x18007e634  nop     dword ptr [rax+rax+00h]
0x18007e639  mov     rcx, [rbp+78h]; this
0x18007e63d  test    eax, eax
0x18007e63f  jnz     loc_18007E7F2
0x18007e645  mov     [rsp+170h+rgsServiceNames], r12; rgsServiceNames
0x18007e64a  mov     dword ptr [rsp+170h+nServices], r12d; nServices
0x18007e64f  mov     rax, [rsp+170h+rgApplications]
0x18007e654  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x18007e659  mov     r9d, [rsp+170h+nApplications]; nApplications
0x18007e65e  xor     r8d, r8d; rgsFileNames
0x18007e661  xor     edx, edx; nFiles
0x18007e663  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x18007e667  call    cs:__imp_RmRegisterResources
0x18007e66e  nop     dword ptr [rax+rax+00h]
0x18007e673  mov     rcx, [rbp+78h]; this
0x18007e677  test    eax, eax
0x18007e679  jnz     loc_18007E82E
0x18007e67f  mov     edx, [rsp+170h+nApplications]
0x18007e683  lea     rcx, [rsp+170h+rgAffectedApps]
0x18007e688  call    ??$make_unique_cotaskmem@$$BY0A@U_RM_PROCESS_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_RM_PROCESS_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_RM_PROCESS_INFO [0]>(unsigned __int64)
0x18007e68d  nop
0x18007e68e  mov     eax, [rsp+170h+nApplications]
0x18007e692  mov     [rsp+170h+pnProcInfo], eax
0x18007e696  mov     [rsp+170h+pnProcInfoNeeded], r12d
0x18007e69b  mov     [rsp+170h+dwRebootReasons], r12d
0x18007e6a0  lea     rax, [rsp+170h+dwRebootReasons]
0x18007e6a5  mov     [rsp+170h+lpUserTime], rax; unsigned int
0x18007e6aa  mov     r9, [rsp+170h+rgAffectedApps]; rgAffectedApps
0x18007e6af  lea     r8, [rsp+170h+pnProcInfo]; pnProcInfo
0x18007e6b4  lea     rdx, [rsp+170h+pnProcInfoNeeded]; pnProcInfoNeeded
0x18007e6b9  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x18007e6bd  call    cs:__imp_RmGetList
0x18007e6c4  nop     dword ptr [rax+rax+00h]
0x18007e6c9  mov     rcx, [rbp+78h]; this
0x18007e6cd  test    eax, eax
0x18007e6cf  jnz     loc_18007E843
0x18007e6d5  mov     edx, [rsp+170h+dwRebootReasons]
0x18007e6d9  test    edx, edx
0x18007e6db  jnz     loc_18007E7AA
0x18007e6e1  xor     r8d, r8d; fnStatus
0x18007e6e4  lea     edx, [rax+1]; lActionFlags
0x18007e6e7  mov     ecx, [rsp+170h+pSessionHandle]; dwSessionHandle
0x18007e6eb  call    cs:__imp_RmShutdown
0x18007e6f2  nop     dword ptr [rax+rax+00h]
0x18007e6f7  mov     rcx, [rbp+78h]; this
0x18007e6fb  test    eax, eax
0x18007e6fd  jnz     loc_18007E795
0x18007e703  mov     ebx, [rsp+170h+pSessionHandle]
0x18007e707  xorps   xmm0, xmm0
0x18007e70a  movups  [rbp+70h+var_D0], xmm0
0x18007e70e  xorps   xmm1, xmm1
0x18007e711  movdqu  [rbp+70h+var_C0], xmm1
0x18007e716  inc     rdi
0x18007e719  cmp     [r14+rdi*2], r12w
0x18007e71e  jnz     short loc_18007E716
0x18007e720  mov     r8, rdi
0x18007e723  mov     rdx, r14
0x18007e726  lea     rcx, [rbp+70h+var_D0]
0x18007e72a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e72f  nop
0x18007e730  lea     r8, [rbp+70h+var_D0]
0x18007e734  lea     rdx, [rsp+170h+ExitTime]
0x18007e739  lea     rcx, [r13+98h]
0x18007e740  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18007e745  mov     rcx, [rax]
0x18007e748  mov     [rcx+30h], ebx
0x18007e74b  lea     rcx, [rbp+70h+var_D0]; void *
0x18007e74f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e754  nop
0x18007e755  mov     rcx, [rsp+170h+rgAffectedApps]; pv
0x18007e75a  mov     [rsp+170h+rgAffectedApps], r12
0x18007e75f  test    rcx, rcx
0x18007e762  jz      short loc_18007E771
0x18007e764  call    cs:__imp_CoTaskMemFree
0x18007e76b  nop     dword ptr [rax+rax+00h]
0x18007e770  nop
0x18007e771  mov     rcx, [rsp+170h+rgApplications]; pv
0x18007e776  mov     [rsp+170h+rgApplications], r12
0x18007e77b  test    rcx, rcx
0x18007e77e  jz      loc_18007E519
0x18007e784  call    cs:__imp_CoTaskMemFree
0x18007e78b  nop     dword ptr [rax+rax+00h]
0x18007e790  jmp     loc_18007E519
0x18007e795  mov     r9d, eax; char *
0x18007e798  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e79f  mov     edx, 47h ; 'G'; void *
0x18007e7a4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007e7aa  mov     ecx, 80070005h
0x18007e7af  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18007e7b4  mov     r9d, eax; char *
0x18007e7b7  mov     rcx, [rbp+78h]; this
0x18007e7bb  mov     dword ptr [rsp+170h+nServices], edx; char *
0x18007e7bf  lea     rax, aRestartmanager; "RestartManager cannot shutdown process:"...
0x18007e7c6  mov     [rsp+170h+lpUserTime], rax; int
0x18007e7cb  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e7d2  mov     edx, 4Ch ; 'L'; void *
0x18007e7d7  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007e7dd  mov     r9d, eax; char *
0x18007e7e0  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e7e7  mov     edx, 22h ; '"'; void *
0x18007e7ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e7f2  mov     r9d, eax; char *
0x18007e7f5  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e7fc  mov     edx, 3Bh ; ';'; void *
0x18007e801  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007e807  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e80e  mov     edx, 33h ; '3'; void *
0x18007e813  mov     rcx, r12; this
0x18007e816  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007e81c  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e823  mov     edx, 2Dh ; '-'; void *
0x18007e828  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007e82e  mov     r9d, eax; char *
0x18007e831  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e838  mov     edx, 3Dh ; '='; void *
0x18007e83d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007e843  mov     r9d, eax; char *
0x18007e846  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007e84d  mov     edx, 44h ; 'D'; void *
0x18007e852  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
