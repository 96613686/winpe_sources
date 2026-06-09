# CService::Stop(void)

- ea: `0x180055694`
- end: `0x180055926`
- name: `?Stop@CService@@IEAAJXZ`
- size: `658`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002cf00`

## callees

- `0x180003b38`
- `0x1800129d0`
- `0x180012e04`
- `0x180014b20`
- `0x180022030`
- `0x180022ec0`
- `0x18002701c`
- `0x18004e850`
- `0x180055694`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055776`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180055776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005583c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005583c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180055829`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180055829`
- `USER32!UnregisterDeviceNotification` at `0x180055880`
- `USER32!UnregisterDeviceNotification` at `0x180055880`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180055894`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180055894`

## string_xrefs

- `0x1800558ab`: `LSM Service Stopped...`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CService::Stop(CService *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  struct ICsrMgr *v8; // rcx
  struct ISessionManagerInternal *v9; // rcx
  struct IPublicRpc *v10; // rcx
  struct IPrivateRpc *v11; // rcx
  SERVICE_STATUS_HANDLE v12; // rdi
  void *v13; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD v18[2]; // [rsp+30h] [rbp-48h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
    v3 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = 0;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
    SmartPtr<ITSRpcClientTrackerMgr>::operator=((char *)this + 16);
  }
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
    SmartPtr<ITSRpcClientTrackerMgr>::operator=((char *)this + 8);
  }
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    SmartPtr<IWinlogonNotify>::operator=((char *)this + 32, 0);
  }
  SmartPtr<ITerminal>::operator=((char *)this + 40, 0);
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 168LL))(*(_QWORD *)this);
  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 )
    ResetEvent(v7);
  v8 = ICsrMgr::pGlobalInstance;
  ICsrMgr::pGlobalInstance = 0;
  if ( v8 )
    (*(void (__fastcall **)(struct ICsrMgr *))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = ISessionManagerInternal::pSMGlobalInstance;
  ISessionManagerInternal::pSMGlobalInstance = 0;
  if ( v9 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = IPublicRpc::pGlobalInstance;
  IPublicRpc::pGlobalInstance = 0;
  if ( v10 )
    (*(void (__fastcall **)(struct IPublicRpc *))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = IPrivateRpc::pGlobalInstance;
  IPrivateRpc::pGlobalInstance = 0;
  if ( v11 )
    (*(void (__fastcall **)(struct IPrivateRpc *))(*(_QWORD *)v11 + 16LL))(v11);
  SmartPtr<ITSRpcClientTrackerMgr>::operator=(this);
  if ( CGlassTerminal::staticCreateGlassSessionWork )
  {
    WaitForThreadpoolWorkCallbacks(CGlassTerminal::staticCreateGlassSessionWork, 1);
    CloseThreadpoolWork(CGlassTerminal::staticCreateGlassSessionWork);
    CGlassTerminal::staticCreateGlassSessionWork = 0;
  }
  *(_QWORD *)((char *)this + 116) = 0;
  *((_DWORD *)this + 25) = 1;
  *(_OWORD *)&ServiceStatus.dwServiceType = *((_OWORD *)this + 6);
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = *(_OWORD *)((char *)this + 108);
  v12 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 11);
  v13 = (void *)*((_QWORD *)this + 16);
  if ( v13 )
    UnregisterDeviceNotification(v13);
  SetServiceStatus(v12, &ServiceStatus);
  if ( (unsigned int)dword_1800DF020 > 2 )
  {
    v18[0] = "LSM Service Stopped...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v14,
      (unsigned int)&word_1800C54E6,
      v15,
      v16,
      (__int64)v18);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v18, (struct CResource *)&g_ProviderLock);
  if ( RegisteredProvider )
  {
    TraceLoggingUnregister_EventUnregister(&dword_1800DF020);
    RegisteredProvider = 0;
  }
  CAutoLock::Unlock((CAutoLock *)v18);
  return 0;
}

```

## disassembly

```asm
0x180055694  mov     [rsp+arg_8], rbx
0x180055699  push    rdi
0x18005569a  sub     rsp, 70h
0x18005569e  mov     rax, cs:__security_cookie
0x1800556a5  xor     rax, rsp
0x1800556a8  mov     [rsp+78h+var_18], rax
0x1800556ad  mov     rbx, rcx
0x1800556b0  xorps   xmm0, xmm0
0x1800556b3  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800556b8  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800556bd  mov     rcx, [rcx+40h]
0x1800556c1  test    rcx, rcx
0x1800556c4  jz      short loc_1800556EF
0x1800556c6  mov     rax, [rcx]
0x1800556c9  mov     rax, [rax+28h]
0x1800556cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556d2  mov     rcx, [rbx+40h]
0x1800556d6  mov     qword ptr [rbx+40h], 0
0x1800556de  test    rcx, rcx
0x1800556e1  jz      short loc_1800556EF
0x1800556e3  mov     rax, [rcx]
0x1800556e6  mov     rax, [rax+10h]
0x1800556ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556ef  mov     rcx, [rbx+10h]
0x1800556f3  test    rcx, rcx
0x1800556f6  jz      short loc_18005570D
0x1800556f8  mov     rax, [rcx]
0x1800556fb  mov     rax, [rax+20h]
0x1800556ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055704  lea     rcx, [rbx+10h]
0x180055708  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x18005570d  mov     rcx, [rbx+8]
0x180055711  test    rcx, rcx
0x180055714  jz      short loc_18005572B
0x180055716  mov     rax, [rcx]
0x180055719  mov     rax, [rax+20h]
0x18005571d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055722  lea     rcx, [rbx+8]
0x180055726  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x18005572b  mov     rcx, [rbx+20h]
0x18005572f  test    rcx, rcx
0x180055732  jz      short loc_18005574B
0x180055734  mov     rax, [rcx]
0x180055737  mov     rax, [rax+18h]
0x18005573b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055740  xor     edx, edx
0x180055742  lea     rcx, [rbx+20h]
0x180055746  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x18005574b  lea     rcx, [rbx+28h]
0x18005574f  xor     edx, edx
0x180055751  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180055756  mov     rcx, [rbx]
0x180055759  test    rcx, rcx
0x18005575c  jz      short loc_18005576D
0x18005575e  mov     rax, [rcx]
0x180055761  mov     rax, [rax+0A8h]
0x180055768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005576d  mov     rcx, [rbx+48h]; hEvent
0x180055771  test    rcx, rcx
0x180055774  jz      short loc_180055782
0x180055776  call    cs:__imp_ResetEvent
0x18005577d  nop     dword ptr [rax+rax+00h]
0x180055782  mov     rcx, cs:?pGlobalInstance@ICsrMgr@@0PEAV1@EA; ICsrMgr * ICsrMgr::pGlobalInstance
0x180055789  mov     cs:?pGlobalInstance@ICsrMgr@@0PEAV1@EA, 0; ICsrMgr * ICsrMgr::pGlobalInstance
0x180055794  test    rcx, rcx
0x180055797  jz      short loc_1800557A5
0x180055799  mov     rax, [rcx]
0x18005579c  mov     rax, [rax+10h]
0x1800557a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557a5  mov     rcx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x1800557ac  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, 0; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x1800557b7  test    rcx, rcx
0x1800557ba  jz      short loc_1800557C8
0x1800557bc  mov     rax, [rcx]
0x1800557bf  mov     rax, [rax+10h]
0x1800557c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557c8  mov     rcx, cs:?pGlobalInstance@IPublicRpc@@0PEAV1@EA; IPublicRpc * IPublicRpc::pGlobalInstance
0x1800557cf  mov     cs:?pGlobalInstance@IPublicRpc@@0PEAV1@EA, 0; IPublicRpc * IPublicRpc::pGlobalInstance
0x1800557da  test    rcx, rcx
0x1800557dd  jz      short loc_1800557EB
0x1800557df  mov     rax, [rcx]
0x1800557e2  mov     rax, [rax+10h]
0x1800557e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557eb  mov     rcx, cs:?pGlobalInstance@IPrivateRpc@@0PEAV1@EA; IPrivateRpc * IPrivateRpc::pGlobalInstance
0x1800557f2  mov     cs:?pGlobalInstance@IPrivateRpc@@0PEAV1@EA, 0; IPrivateRpc * IPrivateRpc::pGlobalInstance
0x1800557fd  test    rcx, rcx
0x180055800  jz      short loc_18005580E
0x180055802  mov     rax, [rcx]
0x180055805  mov     rax, [rax+10h]
0x180055809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005580e  mov     rcx, rbx
0x180055811  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180055816  mov     edi, 1
0x18005581b  mov     rcx, cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA; pwk
0x180055822  test    rcx, rcx
0x180055825  jz      short loc_180055853
0x180055827  mov     edx, edi; fCancelPendingCallbacks
0x180055829  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180055830  nop     dword ptr [rax+rax+00h]
0x180055835  mov     rcx, cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA; pwk
0x18005583c  call    cs:__imp_CloseThreadpoolWork
0x180055843  nop     dword ptr [rax+rax+00h]
0x180055848  mov     cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA, 0; _TP_WORK * CGlassTerminal::staticCreateGlassSessionWork
0x180055853  mov     qword ptr [rbx+74h], 0
0x18005585b  mov     [rbx+64h], edi
0x18005585e  movups  xmm0, xmmword ptr [rbx+60h]
0x180055862  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180055867  movups  xmm1, xmmword ptr [rbx+6Ch]
0x18005586b  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm1
0x180055870  mov     rdi, [rbx+58h]
0x180055874  mov     rcx, [rbx+80h]; Handle
0x18005587b  test    rcx, rcx
0x18005587e  jz      short loc_18005588C
0x180055880  call    cs:__imp_UnregisterDeviceNotification
0x180055887  nop     dword ptr [rax+rax+00h]
0x18005588c  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180055891  mov     rcx, rdi; hServiceStatus
0x180055894  call    cs:__imp_SetServiceStatus
0x18005589b  nop     dword ptr [rax+rax+00h]
0x1800558a0  mov     eax, cs:dword_1800DF020
0x1800558a6  cmp     eax, 2
0x1800558a9  jbe     short loc_1800558CD
0x1800558ab  lea     rax, aLsmServiceStop; "LSM Service Stopped..."
0x1800558b2  mov     [rsp+78h+var_48], rax
0x1800558b7  lea     rax, [rsp+78h+var_48]
0x1800558bc  mov     [rsp+78h+var_58], rax
0x1800558c1  lea     rdx, word_1800C54E6
0x1800558c8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800558cd  lea     rdx, ?g_ProviderLock@@3VCResource@@A; struct CResource *
0x1800558d4  lea     rcx, [rsp+78h+var_48]; this
0x1800558d9  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800558de  cmp     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x1800558e5  jz      short loc_1800558FD
0x1800558e7  lea     rcx, dword_1800DF020
0x1800558ee  call    TraceLoggingUnregister_EventUnregister
0x1800558f3  mov     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x1800558fd  lea     rcx, [rsp+78h+var_48]; this
0x180055902  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180055907  nop
0x180055908  xor     eax, eax
0x18005590a  mov     rcx, [rsp+78h+var_18]
0x18005590f  xor     rcx, rsp; StackCookie
0x180055912  call    __security_check_cookie
0x180055917  mov     rbx, [rsp+78h+arg_8]
0x18005591f  add     rsp, 70h
0x180055923  pop     rdi
0x180055924  retn
```
