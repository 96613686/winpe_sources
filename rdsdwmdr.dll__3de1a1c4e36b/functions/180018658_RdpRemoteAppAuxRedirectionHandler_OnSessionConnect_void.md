# RdpRemoteAppAuxRedirectionHandler::OnSessionConnect(void)

- ea: `0x180018658`
- end: `0x1800188b3`
- name: `?OnSessionConnect@RdpRemoteAppAuxRedirectionHandler@@QEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012238`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x1800144c8`
- `0x180017598`
- `0x180018658`
- `0x18001986c`
- `0x18001fd1c`
- `0x18002c010`

## string_xrefs

- `0x1800186d2`: `CreateServerSideVCManager failed!`
- `0x1800187ba`: `IServerVCChannelManager::OpenDynamicChannel failed!`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::OnSessionConnect(
        RdpRemoteAppAuxRedirectionHandler *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // r14d
  struct IServerVCChannelManager *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct _GUID *v13; // rdx
  struct IServerVCChannelManager *v15; // [rsp+50h] [rbp-30h] BYREF
  CTSCriticalSection *v16; // [rsp+58h] [rbp-28h] BYREF
  const char *v17; // [rsp+60h] [rbp-20h] BYREF
  const char *v18; // [rsp+68h] [rbp-18h] BYREF
  const char *v19; // [rsp+70h] [rbp-10h] BYREF
  const char *v20; // [rsp+78h] [rbp-8h] BYREF
  const char *v21; // [rsp+B8h] [rbp+38h] BYREF
  int v22; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+48h] BYREF

  v23 = 0;
  v15 = 0;
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v21 = "RdpRemoteAppAuxRedirectionHandler::OnSessionConnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)word_18003E49A,
      a3,
      a4,
      (const unsigned __int16 **)&v21);
  }
  RdpRemoteAppAuxRedirectionHandler::CleanupSessionObjects(this);
  v5 = CreateServerSideVCManager(&v15);
  v8 = v5;
  if ( v5 >= 0 )
  {
    v16 = (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64);
    CTSCriticalSection::Lock((RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64));
    v9 = v15;
    v8 = (*(__int64 (__fastcall **)(struct IServerVCChannelManager *, const char *, __int64, _QWORD, int, unsigned __int64, __int64 *))(*(_QWORD *)v15 + 32LL))(
           v15,
           "Microsoft::Windows::RDS::RemoteAppAuxRedirection",
           0xFFFFFFFFLL,
           0,
           1,
           ((unsigned __int64)this + 48) & -(__int64)(this != 0),
           &v23);
    if ( v8 >= 0 )
    {
      if ( v23 != *((_QWORD *)this + 10) )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 80);
        *((_QWORD *)this + 10) = v23;
        TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
      }
      if ( v9 != *((struct IServerVCChannelManager **)this + 11) )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 88);
        *((_QWORD *)this + 11) = v9;
        TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 88);
      }
      CTSAutoLock::~CTSAutoLock(&v16);
      RDSDWMDirectTraceLogging::LogAuxRedirectionChannelOpen(
        (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 104),
        v13);
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v21) = 199;
        v19 = "IServerVCChannelManager::OpenDynamicChannel failed!";
        v22 = v8;
        v18 = "OnSessionConnect";
        v17 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v20 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v10,
          (__int64)&word_18003E3D6,
          v11,
          v12,
          (const unsigned __int16 **)&v20,
          (__int64)&v22,
          (const unsigned __int16 **)&v17,
          (__int64)&v21,
          (const unsigned __int16 **)&v18,
          (const unsigned __int16 **)&v19);
      }
      CTSAutoLock::~CTSAutoLock(&v16);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v21) = 182;
    v16 = (CTSCriticalSection *)"CreateServerSideVCManager failed!";
    v22 = v5;
    v17 = "OnSessionConnect";
    v18 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
    v19 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&unk_18003E438,
      v6,
      v7,
      (const unsigned __int16 **)&v19,
      (__int64)&v22,
      (const unsigned __int16 **)&v18,
      (__int64)&v21,
      (const unsigned __int16 **)&v17,
      (const unsigned __int16 **)&v16);
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v15);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018658  push    rbp
0x18001865a  push    rbx
0x18001865b  push    rsi
0x18001865c  push    rdi
0x18001865d  push    r14
0x18001865f  mov     rbp, rsp
0x180018662  sub     rsp, 80h
0x180018669  mov     eax, cs:dword_180044008
0x18001866f  mov     rdi, rcx
0x180018672  mov     [rbp+arg_18], 0
0x18001867a  mov     [rbp+var_30], 0
0x180018682  cmp     eax, 4
0x180018685  jbe     short loc_1800186A7
0x180018687  lea     rax, aRdpremoteappau; "RdpRemoteAppAuxRedirectionHandler::OnSe"...
0x18001868e  mov     [rbp+arg_8], rax
0x180018692  lea     rdx, word_18003E49A
0x180018699  lea     rax, [rbp+arg_8]
0x18001869d  mov     [rsp+80h+var_60], rax
0x1800186a2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800186a7  mov     rcx, rdi; this
0x1800186aa  call    ?CleanupSessionObjects@RdpRemoteAppAuxRedirectionHandler@@IEAAXXZ; RdpRemoteAppAuxRedirectionHandler::CleanupSessionObjects(void)
0x1800186af  lea     rcx, [rbp+var_30]; struct IServerVCChannelManager **
0x1800186b3  call    ?CreateServerSideVCManager@@YAJPEAPEAUIServerVCChannelManager@@@Z; CreateServerSideVCManager(IServerVCChannelManager * *)
0x1800186b8  mov     r14d, eax
0x1800186bb  test    eax, eax
0x1800186bd  jns     loc_180018750
0x1800186c3  mov     ecx, cs:dword_180044008
0x1800186c9  cmp     ecx, 2
0x1800186cc  jbe     loc_180018890
0x1800186d2  lea     rax, aCreateserversi; "CreateServerSideVCManager failed!"
0x1800186d9  mov     dword ptr [rbp+arg_8], 0B6h
0x1800186e0  mov     [rbp+var_28], rax
0x1800186e4  lea     rdx, unk_18003E438
0x1800186eb  lea     rax, aOnsessionconne_2; "OnSessionConnect"
0x1800186f2  mov     [rbp+arg_10], r14d
0x1800186f6  mov     [rbp+var_20], rax
0x1800186fa  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018701  mov     [rbp+var_18], rax
0x180018705  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001870c  mov     [rbp+var_10], rax
0x180018710  lea     rax, [rbp+var_28]
0x180018714  mov     [rsp+80h+var_38], rax
0x180018719  lea     rax, [rbp+var_20]
0x18001871d  mov     [rsp+80h+var_40], rax
0x180018722  lea     rax, [rbp+arg_8]
0x180018726  mov     [rsp+80h+var_48], rax
0x18001872b  lea     rax, [rbp+var_18]
0x18001872f  mov     [rsp+80h+var_50], rax
0x180018734  lea     rax, [rbp+arg_10]
0x180018738  mov     [rsp+80h+var_58], rax
0x18001873d  lea     rax, [rbp+var_10]
0x180018741  mov     [rsp+80h+var_60], rax
0x180018746  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001874b  jmp     loc_180018890
0x180018750  lea     rcx, [rdi+40h]; this
0x180018754  mov     [rbp+var_28], rcx
0x180018758  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18001875d  mov     rbx, [rbp+var_30]
0x180018761  lea     rcx, [rdi+30h]
0x180018765  mov     rax, rdi
0x180018768  neg     rax
0x18001876b  mov     rdx, [rbx]
0x18001876e  sbb     r8, r8
0x180018771  and     r8, rcx
0x180018774  xor     r9d, r9d
0x180018777  lea     rcx, [rbp+arg_18]
0x18001877b  mov     [rsp+80h+var_50], rcx
0x180018780  mov     rcx, rbx
0x180018783  mov     rax, [rdx+20h]
0x180018787  lea     rdx, aMicrosoftWindo_0; "Microsoft::Windows::RDS::RemoteAppAuxRe"...
0x18001878e  mov     [rsp+80h+var_58], r8
0x180018793  or      r8d, 0FFFFFFFFh
0x180018797  mov     dword ptr [rsp+80h+var_60], 1
0x18001879f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187a4  mov     r14d, eax
0x1800187a7  test    eax, eax
0x1800187a9  jns     loc_18001883E
0x1800187af  mov     eax, cs:dword_180044008
0x1800187b5  cmp     eax, 2
0x1800187b8  jbe     short loc_180018833
0x1800187ba  lea     rax, aIservervcchann; "IServerVCChannelManager::OpenDynamicCha"...
0x1800187c1  mov     dword ptr [rbp+arg_8], 0C7h
0x1800187c8  mov     [rbp+var_10], rax
0x1800187cc  lea     rdx, word_18003E3D6
0x1800187d3  lea     rax, aOnsessionconne_2; "OnSessionConnect"
0x1800187da  mov     [rbp+arg_10], r14d
0x1800187de  mov     [rbp+var_18], rax
0x1800187e2  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800187e9  mov     [rbp+var_20], rax
0x1800187ed  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800187f4  mov     [rbp+var_8], rax
0x1800187f8  lea     rax, [rbp+var_10]
0x1800187fc  mov     [rsp+80h+var_38], rax
0x180018801  lea     rax, [rbp+var_18]
0x180018805  mov     [rsp+80h+var_40], rax
0x18001880a  lea     rax, [rbp+arg_8]
0x18001880e  mov     [rsp+80h+var_48], rax
0x180018813  lea     rax, [rbp+var_20]
0x180018817  mov     [rsp+80h+var_50], rax
0x18001881c  lea     rax, [rbp+arg_10]
0x180018820  mov     [rsp+80h+var_58], rax
0x180018825  lea     rax, [rbp+var_8]
0x180018829  mov     [rsp+80h+var_60], rax
0x18001882e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180018833  lea     rcx, [rbp+var_28]; this
0x180018837  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18001883c  jmp     short loc_180018890
0x18001883e  lea     rsi, [rdi+50h]
0x180018842  mov     rax, [rsi]
0x180018845  cmp     [rbp+arg_18], rax
0x180018849  jz      short loc_180018862
0x18001884b  mov     rcx, rsi
0x18001884e  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018853  mov     rax, [rbp+arg_18]
0x180018857  mov     rcx, rsi
0x18001885a  mov     [rsi], rax
0x18001885d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180018862  lea     rsi, [rdi+58h]
0x180018866  cmp     rbx, [rsi]
0x180018869  jz      short loc_18001887E
0x18001886b  mov     rcx, rsi
0x18001886e  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018873  mov     rcx, rsi
0x180018876  mov     [rsi], rbx
0x180018879  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001887e  lea     rcx, [rbp+var_28]; this
0x180018882  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180018887  lea     rcx, [rdi+68h]; this
0x18001888b  call    ?LogAuxRedirectionChannelOpen@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@@Z; RDSDWMDirectTraceLogging::LogAuxRedirectionChannelOpen(_GUID *)
0x180018890  lea     rcx, [rbp+var_30]
0x180018894  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018899  lea     rcx, [rbp+arg_18]
0x18001889d  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800188a2  mov     eax, r14d
0x1800188a5  add     rsp, 80h
0x1800188ac  pop     r14
0x1800188ae  pop     rdi
0x1800188af  pop     rsi
0x1800188b0  pop     rbx
0x1800188b1  pop     rbp
0x1800188b2  retn
```
