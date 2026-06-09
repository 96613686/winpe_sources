# RdpRemoteAppGfxRedirectionHandler::HandleGraphicsUpdateAckPdu(_RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU * const)

- ea: `0x180013e58`
- end: `0x18001403e`
- name: `?HandleGraphicsUpdateAckPdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJQEAU_RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *this, struct _RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU *const, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014c00`

## callees

- `0x1800010f8`
- `0x180001188`
- `0x18000160c`
- `0x180001bfc`
- `0x180005f9c`
- `0x180012b7c`
- `0x180012e60`
- `0x180013e58`
- `0x1800144c8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013f93`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fa1`

## string_xrefs

- `0x180013fe1`: `Failed to signal graphics update event`
- `0x180013f03`: `Failed to remove dirty surface context`
- `0x180013e6c`: `HandleGraphicsUpdateAckPdu`
- `0x180013f55`: `Received Ack for surface not in the list. This is not an error if surface was deleted.`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::HandleGraphicsUpdateAckPdu(
        RdpRemoteAppGfxRedirectionHandler *this,
        struct _RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU *const a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  signed int v12; // edi
  int v13; // ebx
  signed int LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const char *v19; // [rsp+50h] [rbp-10h] BYREF
  CTSCriticalSection *v20; // [rsp+58h] [rbp-8h] BYREF
  const char *v21; // [rsp+90h] [rbp+30h] BYREF
  const char *v22; // [rsp+98h] [rbp+38h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+40h] BYREF
  const char *v24; // [rsp+A8h] [rbp+48h] BYREF

  v4 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  v23 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v21 = (const char *)v4;
    v22 = "HandleGraphicsUpdateAckPdu";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)byte_18003C511,
      a3,
      a4,
      (const unsigned __int16 **)&v22,
      (__int64)&v21);
  }
  v20 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64);
  CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64));
  if ( (unsigned int)CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&public: static int RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(
                       (__int64)this + 112,
                       (__int64)v4,
                       &v23) )
  {
    v9 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 14) + 16LL))((char *)this + 112, v23);
    v12 = v9;
    if ( v9 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      LODWORD(v21) = v9;
      v22 = "HandleGraphicsUpdateAckPdu";
      v24 = "Failed to remove dirty surface context";
      v19 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)byte_18003C4C1,
        v10,
        v11,
        (const unsigned __int16 **)&v19,
        (const unsigned __int16 **)&v24,
        (__int64)&v21,
        (const unsigned __int16 **)&v22);
    }
  }
  else
  {
    v12 = 0;
    if ( (unsigned int)dword_180044008 > 3 )
    {
      v21 = "Received Ack for surface not in the list. This is not an error if surface was deleted.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (__int64)byte_18003C48B,
        v7,
        v8,
        (const unsigned __int16 **)&v21);
    }
  }
  v13 = *((_DWORD *)this + 33);
  CTSAutoLock::~CTSAutoLock(&v20);
  if ( !v13 && !SetEvent(*((HANDLE *)this + 19)) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = "HandleGraphicsUpdateAckPdu";
      v20 = (CTSCriticalSection *)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      LODWORD(v21) = 1156;
      v19 = "Failed to signal graphics update event";
      LODWORD(v22) = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (__int64)byte_18003C431,
        v16,
        v17,
        (const unsigned __int16 **)&v19,
        (__int64)&v22,
        (const unsigned __int16 **)&v20,
        (__int64)&v21,
        (const unsigned __int16 **)&v24);
    }
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013e58  push    rbp
0x180013e5a  push    rbx
0x180013e5b  push    rsi
0x180013e5c  push    rdi
0x180013e5d  push    r14
0x180013e5f  mov     rbp, rsp
0x180013e62  sub     rsp, 60h
0x180013e66  mov     eax, cs:dword_180044008
0x180013e6c  lea     r14, aHandlegraphics; "HandleGraphicsUpdateAckPdu"
0x180013e73  mov     rbx, [rdx+8]
0x180013e77  mov     rsi, rcx
0x180013e7a  mov     [rbp+arg_10], 0
0x180013e82  cmp     eax, 5
0x180013e85  jbe     short loc_180013EAD
0x180013e87  lea     rax, [rbp+arg_0]
0x180013e8b  mov     [rbp+arg_0], rbx
0x180013e8f  mov     [rsp+60h+var_38], rax
0x180013e94  lea     rdx, byte_18003C511
0x180013e9b  lea     rax, [rbp+arg_8]
0x180013e9f  mov     [rbp+arg_8], r14
0x180013ea3  mov     [rsp+60h+var_40], rax
0x180013ea8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180013ead  lea     rcx, [rsi+40h]; this
0x180013eb1  mov     [rbp+var_8], rcx
0x180013eb5  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180013eba  lea     rdi, [rsi+70h]
0x180013ebe  mov     rdx, rbx
0x180013ec1  mov     rcx, rdi
0x180013ec4  lea     r8, [rbp+arg_10]
0x180013ec8  call    ??$Find@PEAUHWND__@@$1?MatchSurfaceByHWND@DirtySurface@RdpRemoteAppGfxRedirectionHandler@@SAHPEAU1@PEAV34@@Z@?$CTSSimpleComPtrArray@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@QEAAHPEAUHWND__@@PEAPEAVDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@Z; CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)
0x180013ecd  test    eax, eax
0x180013ecf  jz      short loc_180013F48
0x180013ed1  mov     rax, [rdi]
0x180013ed4  mov     rcx, rdi
0x180013ed7  mov     rdx, [rbp+arg_10]
0x180013edb  mov     rax, [rax+10h]
0x180013edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ee4  mov     edi, eax
0x180013ee6  test    eax, eax
0x180013ee8  jns     loc_180013F75
0x180013eee  mov     ecx, cs:dword_180044008
0x180013ef4  cmp     ecx, 3
0x180013ef7  jbe     short loc_180013F75
0x180013ef9  mov     dword ptr [rbp+arg_0], eax
0x180013efc  lea     rdx, byte_18003C4C1
0x180013f03  lea     rax, aFailedToRemove_0; "Failed to remove dirty surface context"
0x180013f0a  mov     [rbp+arg_8], r14
0x180013f0e  mov     [rbp+arg_18], rax
0x180013f12  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180013f19  mov     [rbp+var_10], rax
0x180013f1d  lea     rax, [rbp+arg_8]
0x180013f21  mov     [rsp+60h+var_28], rax
0x180013f26  lea     rax, [rbp+arg_0]
0x180013f2a  mov     [rsp+60h+var_30], rax
0x180013f2f  lea     rax, [rbp+arg_18]
0x180013f33  mov     [rsp+60h+var_38], rax
0x180013f38  lea     rax, [rbp+var_10]
0x180013f3c  mov     [rsp+60h+var_40], rax
0x180013f41  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180013f46  jmp     short loc_180013F75
0x180013f48  mov     eax, cs:dword_180044008
0x180013f4e  xor     edi, edi
0x180013f50  cmp     eax, 3
0x180013f53  jbe     short loc_180013F75
0x180013f55  lea     rax, aReceivedAckFor; "Received Ack for surface not in the lis"...
0x180013f5c  mov     [rbp+arg_0], rax
0x180013f60  lea     rdx, byte_18003C48B
0x180013f67  lea     rax, [rbp+arg_0]
0x180013f6b  mov     [rsp+60h+var_40], rax
0x180013f70  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180013f75  mov     ebx, [rsi+84h]
0x180013f7b  lea     rcx, [rbp+var_8]; this
0x180013f7f  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180013f84  test    ebx, ebx
0x180013f86  jnz     loc_180014028
0x180013f8c  mov     rcx, [rsi+98h]; hEvent
0x180013f93  call    cs:__imp_SetEvent
0x180013f99  test    eax, eax
0x180013f9b  jnz     loc_180014028
0x180013fa1  call    cs:__imp_GetLastError
0x180013fa7  mov     edi, eax
0x180013fa9  test    eax, eax
0x180013fab  jle     short loc_180013FB6
0x180013fad  movzx   edi, ax
0x180013fb0  or      edi, 80070000h
0x180013fb6  test    edi, edi
0x180013fb8  mov     eax, 80004005h
0x180013fbd  cmovns  edi, eax
0x180013fc0  mov     eax, cs:dword_180044008
0x180013fc6  cmp     eax, 2
0x180013fc9  jbe     short loc_180014028
0x180013fcb  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180013fd2  mov     [rbp+arg_18], r14
0x180013fd6  mov     [rbp+var_8], rax
0x180013fda  lea     rdx, byte_18003C431
0x180013fe1  lea     rax, aFailedToSignal_1; "Failed to signal graphics update event"
0x180013fe8  mov     dword ptr [rbp+arg_0], 484h
0x180013fef  mov     [rbp+var_10], rax
0x180013ff3  lea     rax, [rbp+arg_18]
0x180013ff7  mov     [rsp+60h+var_20], rax
0x180013ffc  lea     rax, [rbp+arg_0]
0x180014000  mov     [rsp+60h+var_28], rax
0x180014005  lea     rax, [rbp+var_8]
0x180014009  mov     [rsp+60h+var_30], rax
0x18001400e  lea     rax, [rbp+arg_8]
0x180014012  mov     [rsp+60h+var_38], rax
0x180014017  lea     rax, [rbp+var_10]
0x18001401b  mov     [rsp+60h+var_40], rax
0x180014020  mov     dword ptr [rbp+arg_8], edi
0x180014023  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180014028  lea     rcx, [rbp+arg_10]
0x18001402c  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180014031  mov     eax, edi
0x180014033  add     rsp, 60h
0x180014037  pop     r14
0x180014039  pop     rdi
0x18001403a  pop     rsi
0x18001403b  pop     rbx
0x18001403c  pop     rbp
0x18001403d  retn
```
