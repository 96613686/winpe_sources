# Container::Manager::Service::CmsService::Stop(long,_GUID const &)

- ea: `0x180024f5c`
- end: `0x180025372`
- name: `?Stop@CmsService@Service@Manager@Container@@QEAAXJAEBU_GUID@@@Z`
- size: `1046`
- prototype: `void __fastcall(Container::Manager::Service::CmsService *__hidden this, int, const struct _GUID *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800245c0`
- `0x180026440`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000b49c`
- `0x18000da68`
- `0x1800103a4`
- `0x180016718`
- `0x1800242bc`
- `0x180024bc0`
- `0x180024cf4`
- `0x180024e28`
- `0x180024f5c`
- `0x1800261a0`
- `0x180045aa0`
- `0x180075554`
- `0x180190f64`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002531e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002531e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800252a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025006`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800250b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025346`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025006`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800250b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025346`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024f8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025217`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024f8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025217`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800252da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800252da`
- `wcimage!WcWaitForPendingFileCompressionOperations` at `0x180025283`
- `wcimage!WcWaitForPendingFileCompressionOperations` at `0x180025283`

## string_xrefs

- `0x180024fc0`: `ServiceStop_DiagRpcServerShutdown`
- `0x18002506d`: `ServiceStop_RpcServerShutdown`
- `0x18002511a`: `ServiceStop_CmCoreShutdown`
- `0x180025226`: `onecore\base\gendrv\silos\clem\service\service.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Service::CmsService::Stop(
        Container::Manager::Service::CmsService *this,
        DWORD a2,
        const struct _GUID *a3)
{
  ULONGLONG TickCount64; // rax
  int v6; // ebx
  ULONGLONG v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v11; // xmm0
  RTL_SRWLOCK *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  RTL_SRWLOCK *v17; // rcx
  unsigned int v18; // edi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int128 v21; // xmm0
  RTL_SRWLOCK *v22; // rcx
  int v23; // eax
  Container::Manager::Core::Details::Globals *v24; // rcx
  Container::Manager::Core::Details::Globals *v25; // rbx
  ULONGLONG v26; // rbx
  int v27; // eax
  unsigned __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 i; // rbx
  Container::Manager::Service::CmsService *v32; // rcx
  const char *v33; // r9
  int LastError; // eax
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v36[34]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  TickCount64 = GetTickCount64();
  v6 = dword_18021E4B0 + 30000;
  v7 = TickCount64;
  Container::Manager::Service::CmsService::UpdateServiceStopPhase(v8, 1, (unsigned int)(dword_18021E4B0 + 30000));
  if ( byte_18021E500 )
  {
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v36,
      "ServiceStop_DiagRpcServerShutdown");
    v36[0] = &CmTraceProvider::ServiceStop_DiagRpcServerShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v36, SRWLock);
    v10 = v37;
    v11 = (__int128)*a3;
    v12 = SRWLock[0];
    *(_BYTE *)(v37 + 4) = 1;
    *(_OWORD *)(v10 + 24) = v11;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    CmTraceProvider::ServiceStop_DiagRpcServerShutdown::StartActivity((CmTraceProvider::ServiceStop_DiagRpcServerShutdown *)v36);
    Container::Manager::Rpc::Server::Shutdown((Container::Manager::Rpc::Server *)&off_18021E4F0);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36, 0);
    v36[0] = &CmTraceProvider::ServiceStop_DiagRpcServerShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
  }
  v13 = v6 - 500;
  Container::Manager::Service::CmsService::UpdateServiceStopPhase(v9, 2, v13);
  if ( byte_18021E4E8 )
  {
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v36,
      "ServiceStop_RpcServerShutdown");
    v36[0] = &CmTraceProvider::ServiceStop_RpcServerShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v36, SRWLock);
    v15 = v37;
    v16 = (__int128)*a3;
    v17 = SRWLock[0];
    *(_BYTE *)(v37 + 4) = 1;
    *(_OWORD *)(v15 + 24) = v16;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    CmTraceProvider::ServiceStop_RpcServerShutdown::StartActivity((CmTraceProvider::ServiceStop_RpcServerShutdown *)v36);
    Container::Manager::Rpc::Server::Shutdown((Container::Manager::Rpc::Server *)&off_18021E4D8);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36, 0);
    v36[0] = &CmTraceProvider::ServiceStop_RpcServerShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
  }
  v18 = v13 - 500;
  Container::Manager::Service::CmsService::UpdateServiceStopPhase(v14, 3, v13 - 500);
  if ( byte_18021E4B4 )
  {
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v36,
      "ServiceStop_CmCoreShutdown");
    v36[0] = &CmTraceProvider::ServiceStop_CmCoreShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v36, SRWLock);
    v20 = v37;
    v21 = (__int128)*a3;
    v22 = SRWLock[0];
    *(_BYTE *)(v37 + 4) = 1;
    *(_OWORD *)(v20 + 24) = v21;
    if ( v22 )
      ReleaseSRWLockExclusive(v22);
    CmTraceProvider::ServiceStop_CmCoreShutdown::StartActivity((CmTraceProvider::ServiceStop_CmCoreShutdown *)v36);
    v23 = Container::Manager::Core::SetGlobalDebugFlags(0);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v23,
        (int)SRWLock[0]);
    v25 = Container::Manager::Core::g_globals;
    Container::Manager::Core::g_globals = 0;
    if ( v25 )
    {
      Container::Manager::Core::Details::Globals::Destroy(v24);
      operator delete(v25, (const struct std::nothrow_t *)1);
    }
    Container::Manager::Core::g_hostState = 0;
    Container::Manager::Core::g_manualHostStateFlags = 0;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36, 0);
    v36[0] = &CmTraceProvider::ServiceStop_CmCoreShutdown::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
  }
  Container::Manager::Service::CmsService::UpdateServiceStopPhase(v19, 4, v18 - dword_18021E4B0);
  v26 = GetTickCount64();
  v27 = dword_18021E4B0;
  v28 = v26 - v7;
  if ( v28 >= (unsigned int)(dword_18021E4B0 + 30000) )
  {
    v29 = 0;
  }
  else
  {
    if ( v28 > 0xFFFFFFFF )
    {
      LODWORD(v28) = -1;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
        (const char *)0x80070216LL,
        (int)SRWLock[0]);
      v27 = dword_18021E4B0;
    }
    v29 = (unsigned int)(v27 - v28 + 30000);
    if ( (unsigned int)v29 >= 0x7530 )
      v29 = 30000;
  }
  WcWaitForPendingFileCompressionOperations(v29);
  Container::Manager::Service::CmsService::UpdateServiceStopPhase(v30, 5, 0);
  AcquireSRWLockExclusive(&pv);
  for ( i = 0; i < 0x258; ++i )
  {
    ServiceStatus.dwWin32ExitCode = a2;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwCheckPoint = 0;
    if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
      break;
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x139,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
                  v33);
    if ( LastError >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\service.cpp",
      (const char *)(unsigned int)LastError,
      (int)SRWLock[0]);
    Sleep(0x64u);
  }
  Container::Manager::Service::CmsService::Reset(v32);
  ReleaseSRWLockExclusive(&pv);
}

```

## disassembly

```asm
0x180024f5c  push    rbp
0x180024f5e  push    rbx
0x180024f5f  push    rsi
0x180024f60  push    rdi
0x180024f61  push    r14
0x180024f63  push    r15
0x180024f65  lea     rbp, [rsp-98h]
0x180024f6d  sub     rsp, 198h
0x180024f74  mov     rax, cs:__security_cookie
0x180024f7b  xor     rax, rsp
0x180024f7e  mov     [rbp+0C0h+var_40], rax
0x180024f85  mov     rsi, r8
0x180024f88  mov     r15d, edx
0x180024f8b  call    cs:__imp_GetTickCount64
0x180024f92  nop     dword ptr [rax+rax+00h]
0x180024f97  mov     ebx, cs:dword_18021E4B0
0x180024f9d  mov     edx, 1
0x180024fa2  add     ebx, 7530h
0x180024fa8  mov     r14, rax
0x180024fab  mov     r8d, ebx
0x180024fae  call    ?UpdateServiceStopPhase@CmsService@Service@Manager@Container@@AEAAXW4ServiceStopPhase@1234@K@Z; Container::Manager::Service::CmsService::UpdateServiceStopPhase(Container::Manager::Service::CmsService::ServiceStopPhase,ulong)
0x180024fb3  cmp     cs:byte_18021E500, 0
0x180024fba  jz      loc_18002504D
0x180024fc0  lea     rdx, aServicestopDia; "ServiceStop_DiagRpcServerShutdown"
0x180024fc7  lea     rcx, [rsp+1C0h+var_190]
0x180024fcc  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024fd1  lea     rdi, ??_7ServiceStop_DiagRpcServerShutdown@CmTraceProvider@@6B@; const CmTraceProvider::ServiceStop_DiagRpcServerShutdown::`vftable'
0x180024fd8  lea     rdx, [rsp+1C0h+SRWLock]
0x180024fdd  mov     [rsp+1C0h+var_190], rdi
0x180024fe2  lea     rcx, [rsp+1C0h+var_190]
0x180024fe7  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024fec  mov     rax, [rbp+0C0h+var_80]
0x180024ff0  movups  xmm0, xmmword ptr [rsi]
0x180024ff3  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x180024ff8  mov     byte ptr [rax+4], 1
0x180024ffc  movdqu  xmmword ptr [rax+18h], xmm0
0x180025001  test    rcx, rcx
0x180025004  jz      short loc_180025012
0x180025006  call    cs:__imp_ReleaseSRWLockExclusive
0x18002500d  nop     dword ptr [rax+rax+00h]
0x180025012  lea     rcx, [rsp+1C0h+var_190]; this
0x180025017  call    ?StartActivity@ServiceStop_DiagRpcServerShutdown@CmTraceProvider@@QEAAXXZ; CmTraceProvider::ServiceStop_DiagRpcServerShutdown::StartActivity(void)
0x18002501c  lea     rcx, off_18021E4F0; this
0x180025023  call    ?Shutdown@Server@Rpc@Manager@Container@@QEAAXXZ; Container::Manager::Rpc::Server::Shutdown(void)
0x180025028  xor     edx, edx
0x18002502a  lea     rcx, [rsp+1C0h+var_190]
0x18002502f  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180025034  lea     rcx, [rsp+1C0h+var_190]
0x180025039  mov     [rsp+1C0h+var_190], rdi
0x18002503e  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180025043  lea     rcx, [rsp+1C0h+var_190]
0x180025048  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002504d  add     ebx, 0FFFFFE0Ch
0x180025053  mov     edx, 2
0x180025058  mov     r8d, ebx
0x18002505b  call    ?UpdateServiceStopPhase@CmsService@Service@Manager@Container@@AEAAXW4ServiceStopPhase@1234@K@Z; Container::Manager::Service::CmsService::UpdateServiceStopPhase(Container::Manager::Service::CmsService::ServiceStopPhase,ulong)
0x180025060  cmp     cs:byte_18021E4E8, 0
0x180025067  jz      loc_1800250FA
0x18002506d  lea     rdx, aServicestopRpc; "ServiceStop_RpcServerShutdown"
0x180025074  lea     rcx, [rsp+1C0h+var_190]
0x180025079  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002507e  lea     rdi, ??_7ServiceStop_RpcServerShutdown@CmTraceProvider@@6B@; const CmTraceProvider::ServiceStop_RpcServerShutdown::`vftable'
0x180025085  lea     rdx, [rsp+1C0h+SRWLock]
0x18002508a  mov     [rsp+1C0h+var_190], rdi
0x18002508f  lea     rcx, [rsp+1C0h+var_190]
0x180025094  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025099  mov     rax, [rbp+0C0h+var_80]
0x18002509d  movups  xmm0, xmmword ptr [rsi]
0x1800250a0  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x1800250a5  mov     byte ptr [rax+4], 1
0x1800250a9  movdqu  xmmword ptr [rax+18h], xmm0
0x1800250ae  test    rcx, rcx
0x1800250b1  jz      short loc_1800250BF
0x1800250b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800250ba  nop     dword ptr [rax+rax+00h]
0x1800250bf  lea     rcx, [rsp+1C0h+var_190]; this
0x1800250c4  call    ?StartActivity@ServiceStop_RpcServerShutdown@CmTraceProvider@@QEAAXXZ; CmTraceProvider::ServiceStop_RpcServerShutdown::StartActivity(void)
0x1800250c9  lea     rcx, off_18021E4D8; this
0x1800250d0  call    ?Shutdown@Server@Rpc@Manager@Container@@QEAAXXZ; Container::Manager::Rpc::Server::Shutdown(void)
0x1800250d5  xor     edx, edx
0x1800250d7  lea     rcx, [rsp+1C0h+var_190]
0x1800250dc  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800250e1  lea     rcx, [rsp+1C0h+var_190]
0x1800250e6  mov     [rsp+1C0h+var_190], rdi
0x1800250eb  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800250f0  lea     rcx, [rsp+1C0h+var_190]
0x1800250f5  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800250fa  lea     edi, [rbx-1F4h]
0x180025100  mov     edx, 3
0x180025105  mov     r8d, edi
0x180025108  call    ?UpdateServiceStopPhase@CmsService@Service@Manager@Container@@AEAAXW4ServiceStopPhase@1234@K@Z; Container::Manager::Service::CmsService::UpdateServiceStopPhase(Container::Manager::Service::CmsService::ServiceStopPhase,ulong)
0x18002510d  cmp     cs:byte_18021E4B4, 0
0x180025114  jz      loc_180025204
0x18002511a  lea     rdx, aServicestopCmc; "ServiceStop_CmCoreShutdown"
0x180025121  lea     rcx, [rsp+1C0h+var_190]
0x180025126  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002512b  lea     rax, ??_7ServiceStop_CmCoreShutdown@CmTraceProvider@@6B@; const CmTraceProvider::ServiceStop_CmCoreShutdown::`vftable'
0x180025132  lea     rdx, [rsp+1C0h+SRWLock]
0x180025137  mov     [rsp+1C0h+var_190], rax
0x18002513c  lea     rcx, [rsp+1C0h+var_190]
0x180025141  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025146  mov     rax, [rbp+0C0h+var_80]
0x18002514a  movups  xmm0, xmmword ptr [rsi]
0x18002514d  mov     rcx, [rsp+1C0h+SRWLock]; SRWLock
0x180025152  mov     byte ptr [rax+4], 1
0x180025156  movdqu  xmmword ptr [rax+18h], xmm0
0x18002515b  test    rcx, rcx
0x18002515e  jz      short loc_18002516C
0x180025160  call    cs:__imp_ReleaseSRWLockExclusive
0x180025167  nop     dword ptr [rax+rax+00h]
0x18002516c  lea     rcx, [rsp+1C0h+var_190]; this
0x180025171  call    ?StartActivity@ServiceStop_CmCoreShutdown@CmTraceProvider@@QEAAXXZ; CmTraceProvider::ServiceStop_CmCoreShutdown::StartActivity(void)
0x180025176  xor     ecx, ecx
0x180025178  call    ?SetGlobalDebugFlags@Core@Manager@Container@@YAJW4_CMS_GLOBAL_DEBUG_FLAGS@@@Z; Container::Manager::Core::SetGlobalDebugFlags(_CMS_GLOBAL_DEBUG_FLAGS)
0x18002517d  test    eax, eax
0x18002517f  jns     short loc_18002519C
0x180025181  mov     rcx, [rbp+0C8h]; this
0x180025188  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18002518f  mov     r9d, eax; char *
0x180025192  mov     edx, 2AAh; void *
0x180025197  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002519c  mov     rbx, cs:?g_globals@Core@Manager@Container@@3V?$unique_ptr@VGlobals@Details@Core@Manager@Container@@U?$default_delete@VGlobals@Details@Core@Manager@Container@@@wistd@@@wistd@@A; wistd::unique_ptr<Container::Manager::Core::Details::Globals,wistd::default_delete<Container::Manager::Core::Details::Globals>> Container::Manager::Core::g_globals
0x1800251a3  mov     cs:?g_globals@Core@Manager@Container@@3V?$unique_ptr@VGlobals@Details@Core@Manager@Container@@U?$default_delete@VGlobals@Details@Core@Manager@Container@@@wistd@@@wistd@@A, 0; wistd::unique_ptr<Container::Manager::Core::Details::Globals,wistd::default_delete<Container::Manager::Core::Details::Globals>> Container::Manager::Core::g_globals
0x1800251ae  test    rbx, rbx
0x1800251b1  jz      short loc_1800251C5
0x1800251b3  call    ?Destroy@Globals@Details@Core@Manager@Container@@QEAAXXZ; Container::Manager::Core::Details::Globals::Destroy(void)
0x1800251b8  mov     edx, 1; struct std::nothrow_t *
0x1800251bd  mov     rcx, rbx; void *
0x1800251c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800251c5  xor     edx, edx
0x1800251c7  mov     cs:?g_hostState@Core@Manager@Container@@3UContainerHostState@Details@123@A, 0; Container::Manager::Core::Details::ContainerHostState Container::Manager::Core::g_hostState
0x1800251d0  lea     rcx, [rsp+1C0h+var_190]
0x1800251d5  mov     cs:?g_manualHostStateFlags@Core@Manager@Container@@3W4_CMS_MANUAL_HOST_STATE_FLAGS@@A, 0; _CMS_MANUAL_HOST_STATE_FLAGS Container::Manager::Core::g_manualHostStateFlags
0x1800251df  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800251e4  lea     rax, ??_7ServiceStop_CmCoreShutdown@CmTraceProvider@@6B@; const CmTraceProvider::ServiceStop_CmCoreShutdown::`vftable'
0x1800251eb  lea     rcx, [rsp+1C0h+var_190]
0x1800251f0  mov     [rsp+1C0h+var_190], rax
0x1800251f5  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800251fa  lea     rcx, [rsp+1C0h+var_190]
0x1800251ff  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180025204  sub     edi, cs:dword_18021E4B0
0x18002520a  mov     edx, 4
0x18002520f  mov     r8d, edi
0x180025212  call    ?UpdateServiceStopPhase@CmsService@Service@Manager@Container@@AEAAXW4ServiceStopPhase@1234@K@Z; Container::Manager::Service::CmsService::UpdateServiceStopPhase(Container::Manager::Service::CmsService::ServiceStopPhase,ulong)
0x180025217  call    cs:__imp_GetTickCount64
0x18002521e  nop     dword ptr [rax+rax+00h]
0x180025223  mov     rbx, rax
0x180025226  lea     rdi, aOnecoreBaseGen_19; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18002522d  mov     eax, cs:dword_18021E4B0
0x180025233  sub     rbx, r14
0x180025236  lea     edx, [rax+7530h]
0x18002523c  cmp     rbx, rdx
0x18002523f  jnb     short loc_180025281
0x180025241  mov     ecx, 0FFFFFFFFh
0x180025246  cmp     rbx, rcx
0x180025249  jbe     short loc_18002526D
0x18002524b  mov     ebx, ecx
0x18002524d  mov     r9d, 80070216h; char *
0x180025253  mov     rcx, [rbp+0C8h]; this
0x18002525a  mov     r8, rdi; unsigned int
0x18002525d  mov     edx, 183h; void *
0x180025262  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025267  mov     eax, cs:dword_18021E4B0
0x18002526d  sub     eax, ebx
0x18002526f  lea     ecx, [rax+7530h]
0x180025275  mov     eax, 7530h
0x18002527a  cmp     ecx, eax
0x18002527c  cmovnb  ecx, eax
0x18002527f  jmp     short loc_180025283
0x180025281  xor     ecx, ecx
0x180025283  call    cs:__imp_WcWaitForPendingFileCompressionOperations
0x18002528a  nop     dword ptr [rax+rax+00h]
0x18002528f  xor     r8d, r8d
0x180025292  lea     edx, [r8+5]
0x180025296  call    ?UpdateServiceStopPhase@CmsService@Service@Manager@Container@@AEAAXW4ServiceStopPhase@1234@K@Z; Container::Manager::Service::CmsService::UpdateServiceStopPhase(Container::Manager::Service::CmsService::ServiceStopPhase,ulong)
0x18002529b  lea     rcx, pv; SRWLock
0x1800252a2  call    cs:__imp_AcquireSRWLockExclusive
0x1800252a9  nop     dword ptr [rax+rax+00h]
0x1800252ae  xor     ebx, ebx
0x1800252b0  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800252b7  lea     rdx, ServiceStatus; lpServiceStatus
0x1800252be  mov     cs:ServiceStatus.dwWin32ExitCode, r15d
0x1800252c5  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x1800252d0  mov     cs:ServiceStatus.dwCheckPoint, 0
0x1800252da  call    cs:__imp_SetServiceStatus
0x1800252e1  nop     dword ptr [rax+rax+00h]
0x1800252e6  test    eax, eax
0x1800252e8  jnz     short loc_18002533A
0x1800252ea  mov     rcx, [rbp+0C8h]; this
0x1800252f1  mov     r8, rdi; unsigned int
0x1800252f4  mov     edx, 139h; void *
0x1800252f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800252fe  test    eax, eax
0x180025300  jns     short loc_18002533A
0x180025302  mov     rcx, [rbp+0C8h]; this
0x180025309  mov     r9d, eax; char *
0x18002530c  mov     r8, rdi; unsigned int
0x18002530f  mov     edx, 1A4h; void *
0x180025314  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025319  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002531e  call    cs:__imp_Sleep
0x180025325  nop     dword ptr [rax+rax+00h]
0x18002532a  inc     rbx
0x18002532d  cmp     rbx, 258h
0x180025334  jb      loc_1800252B0
0x18002533a  call    ?Reset@CmsService@Service@Manager@Container@@AEAAXXZ; Container::Manager::Service::CmsService::Reset(void)
0x18002533f  lea     rcx, pv; SRWLock
0x180025346  call    cs:__imp_ReleaseSRWLockExclusive
0x18002534d  nop     dword ptr [rax+rax+00h]
0x180025352  mov     rcx, [rbp+0C0h+var_40]
0x180025359  xor     rcx, rsp; StackCookie
0x18002535c  call    __security_check_cookie
0x180025361  add     rsp, 198h
0x180025368  pop     r15
0x18002536a  pop     r14
0x18002536c  pop     rdi
0x18002536d  pop     rsi
0x18002536e  pop     rbx
0x18002536f  pop     rbp
0x180025370  retn
```
