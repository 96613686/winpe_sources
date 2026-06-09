# CService::Stop(void)

- ea: `0x180051f5c`
- end: `0x1800521cf`
- name: `?Stop@CService@@IEAAJXZ`
- size: `627`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18002ae4c`

## callees

- `0x180003b14`
- `0x18000f260`
- `0x180010fb0`
- `0x18001ce00`
- `0x18001fd20`
- `0x180020e20`
- `0x180025070`
- `0x18004b460`
- `0x180051f5c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005203e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005203e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800520f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800520f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800520eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800520eb`
- `USER32!UnregisterDeviceNotification` at `0x180052136`
- `USER32!UnregisterDeviceNotification` at `0x180052136`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180052144`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180052144`

## string_xrefs

- `0x180052155`: `LSM Service Stopped...`

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
  if ( (unsigned int)dword_1800DA020 > 2 )
  {
    v18[0] = "LSM Service Stopped...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v14,
      (unsigned int)&word_1800C035E,
      v15,
      v16,
      (__int64)v18);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v18, (struct CResource *)&g_ProviderLock);
  if ( RegisteredProvider )
  {
    TraceLoggingUnregister_EventUnregister(&dword_1800DA020);
    RegisteredProvider = 0;
  }
  CAutoLock::Unlock((CAutoLock *)v18);
  return 0;
}

```

## disassembly

```asm
0x180051f5c  mov     [rsp+arg_8], rbx
0x180051f61  push    rdi
0x180051f62  sub     rsp, 70h
0x180051f66  mov     rax, cs:__security_cookie
0x180051f6d  xor     rax, rsp
0x180051f70  mov     [rsp+78h+var_18], rax
0x180051f75  mov     rbx, rcx
0x180051f78  xorps   xmm0, xmm0
0x180051f7b  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180051f80  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x180051f85  mov     rcx, [rcx+40h]
0x180051f89  test    rcx, rcx
0x180051f8c  jz      short loc_180051FB7
0x180051f8e  mov     rax, [rcx]
0x180051f91  mov     rax, [rax+28h]
0x180051f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f9a  mov     rcx, [rbx+40h]
0x180051f9e  mov     qword ptr [rbx+40h], 0
0x180051fa6  test    rcx, rcx
0x180051fa9  jz      short loc_180051FB7
0x180051fab  mov     rax, [rcx]
0x180051fae  mov     rax, [rax+10h]
0x180051fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fb7  mov     rcx, [rbx+10h]
0x180051fbb  test    rcx, rcx
0x180051fbe  jz      short loc_180051FD5
0x180051fc0  mov     rax, [rcx]
0x180051fc3  mov     rax, [rax+20h]
0x180051fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fcc  lea     rcx, [rbx+10h]
0x180051fd0  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180051fd5  mov     rcx, [rbx+8]
0x180051fd9  test    rcx, rcx
0x180051fdc  jz      short loc_180051FF3
0x180051fde  mov     rax, [rcx]
0x180051fe1  mov     rax, [rax+20h]
0x180051fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fea  lea     rcx, [rbx+8]
0x180051fee  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x180051ff3  mov     rcx, [rbx+20h]
0x180051ff7  test    rcx, rcx
0x180051ffa  jz      short loc_180052013
0x180051ffc  mov     rax, [rcx]
0x180051fff  mov     rax, [rax+18h]
0x180052003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052008  xor     edx, edx
0x18005200a  lea     rcx, [rbx+20h]
0x18005200e  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180052013  lea     rcx, [rbx+28h]
0x180052017  xor     edx, edx
0x180052019  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18005201e  mov     rcx, [rbx]
0x180052021  test    rcx, rcx
0x180052024  jz      short loc_180052035
0x180052026  mov     rax, [rcx]
0x180052029  mov     rax, [rax+0A8h]
0x180052030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052035  mov     rcx, [rbx+48h]; hEvent
0x180052039  test    rcx, rcx
0x18005203c  jz      short loc_180052044
0x18005203e  call    cs:__imp_ResetEvent
0x180052044  mov     rcx, cs:?pGlobalInstance@ICsrMgr@@0PEAV1@EA; ICsrMgr * ICsrMgr::pGlobalInstance
0x18005204b  mov     cs:?pGlobalInstance@ICsrMgr@@0PEAV1@EA, 0; ICsrMgr * ICsrMgr::pGlobalInstance
0x180052056  test    rcx, rcx
0x180052059  jz      short loc_180052067
0x18005205b  mov     rax, [rcx]
0x18005205e  mov     rax, [rax+10h]
0x180052062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052067  mov     rcx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18005206e  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, 0; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180052079  test    rcx, rcx
0x18005207c  jz      short loc_18005208A
0x18005207e  mov     rax, [rcx]
0x180052081  mov     rax, [rax+10h]
0x180052085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005208a  mov     rcx, cs:?pGlobalInstance@IPublicRpc@@0PEAV1@EA; IPublicRpc * IPublicRpc::pGlobalInstance
0x180052091  mov     cs:?pGlobalInstance@IPublicRpc@@0PEAV1@EA, 0; IPublicRpc * IPublicRpc::pGlobalInstance
0x18005209c  test    rcx, rcx
0x18005209f  jz      short loc_1800520AD
0x1800520a1  mov     rax, [rcx]
0x1800520a4  mov     rax, [rax+10h]
0x1800520a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520ad  mov     rcx, cs:?pGlobalInstance@IPrivateRpc@@0PEAV1@EA; IPrivateRpc * IPrivateRpc::pGlobalInstance
0x1800520b4  mov     cs:?pGlobalInstance@IPrivateRpc@@0PEAV1@EA, 0; IPrivateRpc * IPrivateRpc::pGlobalInstance
0x1800520bf  test    rcx, rcx
0x1800520c2  jz      short loc_1800520D0
0x1800520c4  mov     rax, [rcx]
0x1800520c7  mov     rax, [rax+10h]
0x1800520cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520d0  mov     rcx, rbx
0x1800520d3  call    ??4?$SmartPtr@VITSRpcClientTrackerMgr@@@@QEAAAEAV0@PEAVITSRpcClientTrackerMgr@@@Z; SmartPtr<ITSRpcClientTrackerMgr>::operator=(ITSRpcClientTrackerMgr *)
0x1800520d8  mov     edi, 1
0x1800520dd  mov     rcx, cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA; pwk
0x1800520e4  test    rcx, rcx
0x1800520e7  jz      short loc_180052109
0x1800520e9  mov     edx, edi; fCancelPendingCallbacks
0x1800520eb  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800520f1  mov     rcx, cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA; pwk
0x1800520f8  call    cs:__imp_CloseThreadpoolWork
0x1800520fe  mov     cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA, 0; _TP_WORK * CGlassTerminal::staticCreateGlassSessionWork
0x180052109  mov     qword ptr [rbx+74h], 0
0x180052111  mov     [rbx+64h], edi
0x180052114  movups  xmm0, xmmword ptr [rbx+60h]
0x180052118  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18005211d  movups  xmm1, xmmword ptr [rbx+6Ch]
0x180052121  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm1
0x180052126  mov     rdi, [rbx+58h]
0x18005212a  mov     rcx, [rbx+80h]; Handle
0x180052131  test    rcx, rcx
0x180052134  jz      short loc_18005213C
0x180052136  call    cs:__imp_UnregisterDeviceNotification
0x18005213c  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180052141  mov     rcx, rdi; hServiceStatus
0x180052144  call    cs:__imp_SetServiceStatus
0x18005214a  mov     eax, cs:dword_1800DA020
0x180052150  cmp     eax, 2
0x180052153  jbe     short loc_180052177
0x180052155  lea     rax, aLsmServiceStop; "LSM Service Stopped..."
0x18005215c  mov     [rsp+78h+var_48], rax
0x180052161  lea     rax, [rsp+78h+var_48]
0x180052166  mov     [rsp+78h+var_58], rax
0x18005216b  lea     rdx, word_1800C035E
0x180052172  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180052177  lea     rdx, ?g_ProviderLock@@3VCResource@@A; struct CResource *
0x18005217e  lea     rcx, [rsp+78h+var_48]; this
0x180052183  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180052188  cmp     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x18005218f  jz      short loc_1800521A7
0x180052191  lea     rcx, dword_1800DA020
0x180052198  call    TraceLoggingUnregister_EventUnregister
0x18005219d  mov     cs:?RegisteredProvider@@3HA, 0; int RegisteredProvider
0x1800521a7  lea     rcx, [rsp+78h+var_48]; this
0x1800521ac  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800521b1  nop
0x1800521b2  xor     eax, eax
0x1800521b4  mov     rcx, [rsp+78h+var_18]
0x1800521b9  xor     rcx, rsp; StackCookie
0x1800521bc  call    __security_check_cookie
0x1800521c1  mov     rbx, [rsp+78h+arg_8]
0x1800521c9  add     rsp, 70h
0x1800521cd  pop     rdi
0x1800521ce  retn
```
