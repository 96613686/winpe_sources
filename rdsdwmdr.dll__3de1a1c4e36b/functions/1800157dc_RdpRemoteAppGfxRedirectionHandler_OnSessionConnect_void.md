# RdpRemoteAppGfxRedirectionHandler::OnSessionConnect(void)

- ea: `0x1800157dc`
- end: `0x180015a59`
- name: `?OnSessionConnect@RdpRemoteAppGfxRedirectionHandler@@QEAAJXZ`
- size: `637`
- prototype: `__int64 __fastcall(LARGE_INTEGER *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012238`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x1800130c0`
- `0x1800144c8`
- `0x1800157dc`
- `0x1800196a4`
- `0x180019ea0`
- `0x18001fd1c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180015a21`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180015a21`

## string_xrefs

- `0x180015856`: `CreateServerSideVCManager failed!`
- `0x18001593e`: `IServerVCChannelManager::OpenDynamicChannel failed!`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnSessionConnect(
        LARGE_INTEGER *this,
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
  __int64 v14; // rdx
  struct IServerVCChannelManager *v16; // [rsp+50h] [rbp-30h] BYREF
  CTSCriticalSection *v17; // [rsp+58h] [rbp-28h] BYREF
  const char *v18; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  const char *v20; // [rsp+70h] [rbp-10h] BYREF
  const char *v21; // [rsp+78h] [rbp-8h] BYREF
  const char *v22; // [rsp+B8h] [rbp+38h] BYREF
  int v23; // [rsp+C0h] [rbp+40h] BYREF
  LARGE_INTEGER v24; // [rsp+C8h] [rbp+48h] BYREF

  v24.QuadPart = 0;
  v16 = 0;
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v22 = "RdpRemoteAppGfxRedirectionHandler::OnSessionConnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)&dword_18003D364,
      a3,
      a4,
      (const unsigned __int16 **)&v22);
  }
  RdpRemoteAppGfxRedirectionHandler::CleanupSessionObjects((RdpRemoteAppGfxRedirectionHandler *)this);
  v5 = CreateServerSideVCManager(&v16);
  v8 = v5;
  if ( v5 >= 0 )
  {
    v17 = (CTSCriticalSection *)&this[8];
    CTSCriticalSection::Lock((CTSCriticalSection *)&this[8]);
    v9 = v16;
    v8 = (*(__int64 (__fastcall **)(struct IServerVCChannelManager *, const char *, __int64, _QWORD, int, unsigned __int64, LARGE_INTEGER *))(*(_QWORD *)v16 + 32LL))(
           v16,
           "Microsoft::Windows::RDS::RemoteAppGraphicsRedirection",
           0xFFFFFFFFLL,
           0,
           1,
           (unsigned __int64)&this[7] & -(__int64)(this != 0),
           &v24);
    if ( v8 >= 0 )
    {
      if ( v24.QuadPart != this[12].QuadPart )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&this[12]);
        this[12] = v24;
        TCntPtr<ITSAsyncCallback>::SafeAddRef(&this[12]);
      }
      if ( v9 != (struct IServerVCChannelManager *)this[13].QuadPart )
      {
        TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&this[13]);
        this[13].QuadPart = (LONGLONG)v9;
        TCntPtr<ITSAsyncCallback>::SafeAddRef(&this[13]);
      }
      CTSAutoLock::~CTSAutoLock(&v17);
      RDSDWMDirectTraceLogging::LogVAILRedirectionChannelOpen((RDSDWMDirectTraceLogging *)&this[21], v13);
      QueryPerformanceFrequency(this + 24);
      this[25].QuadPart = RDSDWMDirectTraceLogging::GetCurrentMsTime((RDSDWMDirectTraceLogging *)this[24].QuadPart, v14);
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v22) = 427;
        v20 = "IServerVCChannelManager::OpenDynamicChannel failed!";
        v23 = v8;
        v19 = "OnSessionConnect";
        v18 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v21 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v10,
          (__int64)&unk_18003D2A0,
          v11,
          v12,
          (const unsigned __int16 **)&v21,
          (__int64)&v23,
          (const unsigned __int16 **)&v18,
          (__int64)&v22,
          (const unsigned __int16 **)&v19,
          (const unsigned __int16 **)&v20);
      }
      CTSAutoLock::~CTSAutoLock(&v17);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v22) = 410;
    v17 = (CTSCriticalSection *)"CreateServerSideVCManager failed!";
    v23 = v5;
    v18 = "OnSessionConnect";
    v19 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v20 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)word_18003D302,
      v6,
      v7,
      (const unsigned __int16 **)&v20,
      (__int64)&v23,
      (const unsigned __int16 **)&v19,
      (__int64)&v22,
      (const unsigned __int16 **)&v18,
      (const unsigned __int16 **)&v17);
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v16);
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800157dc  push    rbp
0x1800157de  push    rbx
0x1800157df  push    rsi
0x1800157e0  push    rdi
0x1800157e1  push    r14
0x1800157e3  mov     rbp, rsp
0x1800157e6  sub     rsp, 80h
0x1800157ed  mov     eax, cs:dword_180044008
0x1800157f3  mov     rdi, rcx
0x1800157f6  mov     [rbp+arg_18], 0
0x1800157fe  mov     [rbp+var_30], 0
0x180015806  cmp     eax, 4
0x180015809  jbe     short loc_18001582B
0x18001580b  lea     rax, aRdpremoteappgf_0; "RdpRemoteAppGfxRedirectionHandler::OnSe"...
0x180015812  mov     [rbp+arg_8], rax
0x180015816  lea     rdx, dword_18003D364
0x18001581d  lea     rax, [rbp+arg_8]
0x180015821  mov     [rsp+80h+var_60], rax
0x180015826  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001582b  mov     rcx, rdi; this
0x18001582e  call    ?CleanupSessionObjects@RdpRemoteAppGfxRedirectionHandler@@IEAAXXZ; RdpRemoteAppGfxRedirectionHandler::CleanupSessionObjects(void)
0x180015833  lea     rcx, [rbp+var_30]; struct IServerVCChannelManager **
0x180015837  call    ?CreateServerSideVCManager@@YAJPEAPEAUIServerVCChannelManager@@@Z; CreateServerSideVCManager(IServerVCChannelManager * *)
0x18001583c  mov     r14d, eax
0x18001583f  test    eax, eax
0x180015841  jns     loc_1800158D4
0x180015847  mov     ecx, cs:dword_180044008
0x18001584d  cmp     ecx, 2
0x180015850  jbe     loc_180015A36
0x180015856  lea     rax, aCreateserversi; "CreateServerSideVCManager failed!"
0x18001585d  mov     dword ptr [rbp+arg_8], 19Ah
0x180015864  mov     [rbp+var_28], rax
0x180015868  lea     rdx, word_18003D302
0x18001586f  lea     rax, aOnsessionconne_2; "OnSessionConnect"
0x180015876  mov     [rbp+arg_10], r14d
0x18001587a  mov     [rbp+var_20], rax
0x18001587e  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015885  mov     [rbp+var_18], rax
0x180015889  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015890  mov     [rbp+var_10], rax
0x180015894  lea     rax, [rbp+var_28]
0x180015898  mov     [rsp+80h+var_38], rax
0x18001589d  lea     rax, [rbp+var_20]
0x1800158a1  mov     [rsp+80h+var_40], rax
0x1800158a6  lea     rax, [rbp+arg_8]
0x1800158aa  mov     [rsp+80h+var_48], rax
0x1800158af  lea     rax, [rbp+var_18]
0x1800158b3  mov     [rsp+80h+var_50], rax
0x1800158b8  lea     rax, [rbp+arg_10]
0x1800158bc  mov     [rsp+80h+var_58], rax
0x1800158c1  lea     rax, [rbp+var_10]
0x1800158c5  mov     [rsp+80h+var_60], rax
0x1800158ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800158cf  jmp     loc_180015A36
0x1800158d4  lea     rcx, [rdi+40h]; this
0x1800158d8  mov     [rbp+var_28], rcx
0x1800158dc  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800158e1  mov     rbx, [rbp+var_30]
0x1800158e5  lea     rcx, [rdi+38h]
0x1800158e9  mov     rax, rdi
0x1800158ec  neg     rax
0x1800158ef  mov     rdx, [rbx]
0x1800158f2  sbb     r8, r8
0x1800158f5  and     r8, rcx
0x1800158f8  xor     r9d, r9d
0x1800158fb  lea     rcx, [rbp+arg_18]
0x1800158ff  mov     [rsp+80h+var_50], rcx
0x180015904  mov     rcx, rbx
0x180015907  mov     rax, [rdx+20h]
0x18001590b  lea     rdx, aMicrosoftWindo; "Microsoft::Windows::RDS::RemoteAppGraph"...
0x180015912  mov     [rsp+80h+var_58], r8
0x180015917  or      r8d, 0FFFFFFFFh
0x18001591b  mov     dword ptr [rsp+80h+var_60], 1
0x180015923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015928  mov     r14d, eax
0x18001592b  test    eax, eax
0x18001592d  jns     loc_1800159C2
0x180015933  mov     eax, cs:dword_180044008
0x180015939  cmp     eax, 2
0x18001593c  jbe     short loc_1800159B7
0x18001593e  lea     rax, aIservervcchann; "IServerVCChannelManager::OpenDynamicCha"...
0x180015945  mov     dword ptr [rbp+arg_8], 1ABh
0x18001594c  mov     [rbp+var_10], rax
0x180015950  lea     rdx, unk_18003D2A0
0x180015957  lea     rax, aOnsessionconne_2; "OnSessionConnect"
0x18001595e  mov     [rbp+arg_10], r14d
0x180015962  mov     [rbp+var_18], rax
0x180015966  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001596d  mov     [rbp+var_20], rax
0x180015971  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015978  mov     [rbp+var_8], rax
0x18001597c  lea     rax, [rbp+var_10]
0x180015980  mov     [rsp+80h+var_38], rax
0x180015985  lea     rax, [rbp+var_18]
0x180015989  mov     [rsp+80h+var_40], rax
0x18001598e  lea     rax, [rbp+arg_8]
0x180015992  mov     [rsp+80h+var_48], rax
0x180015997  lea     rax, [rbp+var_20]
0x18001599b  mov     [rsp+80h+var_50], rax
0x1800159a0  lea     rax, [rbp+arg_10]
0x1800159a4  mov     [rsp+80h+var_58], rax
0x1800159a9  lea     rax, [rbp+var_8]
0x1800159ad  mov     [rsp+80h+var_60], rax
0x1800159b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800159b7  lea     rcx, [rbp+var_28]; this
0x1800159bb  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800159c0  jmp     short loc_180015A36
0x1800159c2  lea     rsi, [rdi+60h]
0x1800159c6  mov     rax, [rsi]
0x1800159c9  cmp     [rbp+arg_18], rax
0x1800159cd  jz      short loc_1800159E6
0x1800159cf  mov     rcx, rsi
0x1800159d2  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800159d7  mov     rax, [rbp+arg_18]
0x1800159db  mov     rcx, rsi
0x1800159de  mov     [rsi], rax
0x1800159e1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800159e6  lea     rsi, [rdi+68h]
0x1800159ea  cmp     rbx, [rsi]
0x1800159ed  jz      short loc_180015A02
0x1800159ef  mov     rcx, rsi
0x1800159f2  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800159f7  mov     rcx, rsi
0x1800159fa  mov     [rsi], rbx
0x1800159fd  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180015a02  lea     rcx, [rbp+var_28]; this
0x180015a06  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180015a0b  lea     rcx, [rdi+0A8h]; this
0x180015a12  call    ?LogVAILRedirectionChannelOpen@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@@Z; RDSDWMDirectTraceLogging::LogVAILRedirectionChannelOpen(_GUID *)
0x180015a17  lea     rbx, [rdi+0C0h]
0x180015a1e  mov     rcx, rbx; lpFrequency
0x180015a21  call    cs:__imp_QueryPerformanceFrequency
0x180015a27  mov     rcx, [rbx]; this
0x180015a2a  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x180015a2f  mov     [rdi+0C8h], rax
0x180015a36  lea     rcx, [rbp+var_30]
0x180015a3a  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180015a3f  lea     rcx, [rbp+arg_18]
0x180015a43  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180015a48  mov     eax, r14d
0x180015a4b  add     rsp, 80h
0x180015a52  pop     r14
0x180015a54  pop     rdi
0x180015a55  pop     rsi
0x180015a56  pop     rbx
0x180015a57  pop     rbp
0x180015a58  retn
```
