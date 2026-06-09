# RdpRemoteAppGfxRedirectionHandler::SendCreateCompositionSurfacePdu(HWND__ *,void *)

- ea: `0x180016700`
- end: `0x180016968`
- name: `?SendCreateCompositionSurfacePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@PEAX@Z`
- size: `616`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this, HWND, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800149e0`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x180013850`
- `0x1800144c8`
- `0x180016700`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x180016759`: `Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_CREATE_COMPOSITION_SURFACE_PDU`
- `0x180016772`: `SendCreateCompositionSurfacePdu`
- `0x180016820`: `SendCreateCompositionSurfacePdu`
- `0x1800168e4`: `SendCreateCompositionSurfacePdu`
- `0x1800168cb`: `Failed to send XREMOTEAPPGFXREDIRECTION_PDU_TYPE_CREATE_COMPOSITION_SURFACE PDU`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::SendCreateCompositionSurfacePdu(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        void *a3)
{
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+50h] [rbp-19h] BYREF
  int v18; // [rsp+54h] [rbp-15h] BYREF
  CTSCriticalSection *v19; // [rsp+58h] [rbp-11h] BYREF
  const char *v20; // [rsp+60h] [rbp-9h] BYREF
  const char *v21; // [rsp+68h] [rbp-1h] BYREF
  __int64 v22; // [rsp+70h] [rbp+7h] BYREF
  const char *v23; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v24; // [rsp+80h] [rbp+17h] BYREF
  void *v25; // [rsp+90h] [rbp+27h]

  v24 = 0;
  v25 = 0;
  v22 = 0;
  v6 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(this);
  if ( v6 >= 0 )
  {
    v19 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64);
    CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64));
    if ( *((_QWORD *)this + 12) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v22);
      v9 = *((_QWORD *)this + 12);
      v22 = v9;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v22);
    }
    else
    {
      v9 = 0;
    }
    CTSAutoLock::~CTSAutoLock(&v19);
    if ( v9 )
    {
      *(_QWORD *)&v24 = 0x1800000007LL;
      *((_QWORD *)&v24 + 1) = a2;
      v25 = a3;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, 24, &v24, 0);
      if ( v6 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v18 = 1396;
        v19 = (CTSCriticalSection *)"Failed to send XREMOTEAPPGFXREDIRECTION_PDU_TYPE_CREATE_COMPOSITION_SURFACE PDU";
        v17 = v6;
        v21 = "SendCreateCompositionSurfacePdu";
        v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v23 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v13,
          (__int64)&unk_18003BDD0,
          v14,
          v15,
          (const unsigned __int16 **)&v23,
          (__int64)&v17,
          (const unsigned __int16 **)&v20,
          (__int64)&v18,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v19);
      }
    }
    else
    {
      v6 = -2147467261;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 1382;
        v19 = (CTSCriticalSection *)"SendCreateCompositionSurfacePdu";
        v17 = -2147467261;
        v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v20 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (__int64)word_18003BE32,
          v11,
          v12,
          (const unsigned __int16 **)&v20,
          (__int64)&v17,
          (const unsigned __int16 **)&v21,
          (__int64)&v18,
          (const unsigned __int16 **)&v19);
      }
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v17 = 1375;
    v23 = "Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_CREATE_COMPOSITION_SURFACE_PDU";
    v18 = v6;
    v20 = "SendCreateCompositionSurfacePdu";
    v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v19 = (CTSCriticalSection *)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_18003BE8C,
      v7,
      v8,
      (const unsigned __int16 **)&v19,
      (__int64)&v18,
      (const unsigned __int16 **)&v21,
      (__int64)&v17,
      (const unsigned __int16 **)&v20,
      (const unsigned __int16 **)&v23);
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016700  push    rbp
0x180016702  push    rbx
0x180016703  push    rsi
0x180016704  push    rdi
0x180016705  push    r14
0x180016707  lea     rbp, [rsp-37h]
0x18001670c  sub     rsp, 0A0h
0x180016713  mov     rax, cs:__security_cookie
0x18001671a  xor     rax, rsp
0x18001671d  mov     [rbp+57h+var_28], rax
0x180016721  xor     eax, eax
0x180016723  xorps   xmm0, xmm0
0x180016726  movups  [rbp+57h+var_40], xmm0
0x18001672a  mov     [rbp+57h+var_30], rax
0x18001672e  mov     r14, r8
0x180016731  mov     [rbp+57h+var_50], rax
0x180016735  mov     rsi, rdx
0x180016738  mov     rdi, rcx
0x18001673b  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x180016740  mov     ebx, eax
0x180016742  test    eax, eax
0x180016744  jns     loc_1800167CC
0x18001674a  mov     ecx, cs:dword_180044008
0x180016750  cmp     ecx, 2
0x180016753  jbe     loc_180016943
0x180016759  lea     rax, aChannelNotInit_9; "Channel not initialized. Dropping RDPXR"...
0x180016760  mov     [rbp+57h+var_70], 55Fh
0x180016767  mov     [rbp+57h+var_48], rax
0x18001676b  lea     rdx, dword_18003BE8C
0x180016772  lea     rax, aSendcreatecomp; "SendCreateCompositionSurfacePdu"
0x180016779  mov     [rbp+57h+var_6C], ebx
0x18001677c  mov     [rbp+57h+var_60], rax
0x180016780  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016787  mov     [rbp+57h+var_58], rax
0x18001678b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180016792  mov     [rbp+57h+var_68], rax
0x180016796  lea     rax, [rbp+57h+var_48]
0x18001679a  mov     [rsp+0C0h+var_78], rax
0x18001679f  lea     rax, [rbp+57h+var_60]
0x1800167a3  mov     [rsp+0C0h+var_80], rax
0x1800167a8  lea     rax, [rbp+57h+var_70]
0x1800167ac  mov     [rsp+0C0h+var_88], rax
0x1800167b1  lea     rax, [rbp+57h+var_58]
0x1800167b5  mov     [rsp+0C0h+var_90], rax
0x1800167ba  lea     rax, [rbp+57h+var_6C]
0x1800167be  mov     [rsp+0C0h+var_98], rax
0x1800167c3  lea     rax, [rbp+57h+var_68]
0x1800167c7  jmp     loc_180016939
0x1800167cc  lea     rcx, [rdi+40h]; this
0x1800167d0  mov     [rbp+57h+var_68], rcx
0x1800167d4  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800167d9  cmp     qword ptr [rdi+60h], 0
0x1800167de  jnz     short loc_1800167E4
0x1800167e0  xor     ebx, ebx
0x1800167e2  jmp     short loc_1800167FE
0x1800167e4  lea     rcx, [rbp+57h+var_50]
0x1800167e8  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800167ed  mov     rbx, [rdi+60h]
0x1800167f1  lea     rcx, [rbp+57h+var_50]
0x1800167f5  mov     [rbp+57h+var_50], rbx
0x1800167f9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800167fe  lea     rcx, [rbp+57h+var_68]; this
0x180016802  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180016807  test    rbx, rbx
0x18001680a  jnz     short loc_180016889
0x18001680c  mov     eax, cs:dword_180044008
0x180016812  mov     ebx, 80004003h
0x180016817  cmp     eax, 2
0x18001681a  jbe     loc_180016943
0x180016820  lea     rax, aSendcreatecomp; "SendCreateCompositionSurfacePdu"
0x180016827  mov     [rbp+57h+var_6C], 566h
0x18001682e  mov     [rbp+57h+var_68], rax
0x180016832  lea     rdx, word_18003BE32
0x180016839  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016840  mov     [rbp+57h+var_70], ebx
0x180016843  mov     [rbp+57h+var_58], rax
0x180016847  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x18001684e  mov     [rbp+57h+var_60], rax
0x180016852  lea     rax, [rbp+57h+var_68]
0x180016856  mov     [rsp+0C0h+var_80], rax
0x18001685b  lea     rax, [rbp+57h+var_6C]
0x18001685f  mov     [rsp+0C0h+var_88], rax
0x180016864  lea     rax, [rbp+57h+var_58]
0x180016868  mov     [rsp+0C0h+var_90], rax
0x18001686d  lea     rax, [rbp+57h+var_70]
0x180016871  mov     [rsp+0C0h+var_98], rax
0x180016876  lea     rax, [rbp+57h+var_60]
0x18001687a  mov     [rsp+0C0h+var_A0], rax
0x18001687f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016884  jmp     loc_180016943
0x180016889  mov     edx, 18h
0x18001688e  mov     dword ptr [rbp+57h+var_40], 7
0x180016895  mov     dword ptr [rbp+57h+var_40+4], edx
0x180016898  lea     r8, [rbp+57h+var_40]
0x18001689c  mov     qword ptr [rbp+57h+var_40+8], rsi
0x1800168a0  xor     r9d, r9d
0x1800168a3  mov     [rbp+57h+var_30], r14
0x1800168a7  mov     rcx, rbx
0x1800168aa  mov     rax, [rbx]
0x1800168ad  mov     rax, [rax+18h]
0x1800168b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b6  mov     ebx, eax
0x1800168b8  test    eax, eax
0x1800168ba  jns     loc_180016943
0x1800168c0  mov     eax, cs:dword_180044008
0x1800168c6  cmp     eax, 2
0x1800168c9  jbe     short loc_180016943
0x1800168cb  lea     rax, aFailedToSendXr_3; "Failed to send XREMOTEAPPGFXREDIRECTION"...
0x1800168d2  mov     [rbp+57h+var_6C], 574h
0x1800168d9  mov     [rbp+57h+var_68], rax
0x1800168dd  lea     rdx, unk_18003BDD0
0x1800168e4  lea     rax, aSendcreatecomp; "SendCreateCompositionSurfacePdu"
0x1800168eb  mov     [rbp+57h+var_70], ebx
0x1800168ee  mov     [rbp+57h+var_58], rax
0x1800168f2  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800168f9  mov     [rbp+57h+var_60], rax
0x1800168fd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180016904  mov     [rbp+57h+var_48], rax
0x180016908  lea     rax, [rbp+57h+var_68]
0x18001690c  mov     [rsp+0C0h+var_78], rax
0x180016911  lea     rax, [rbp+57h+var_58]
0x180016915  mov     [rsp+0C0h+var_80], rax
0x18001691a  lea     rax, [rbp+57h+var_6C]
0x18001691e  mov     [rsp+0C0h+var_88], rax
0x180016923  lea     rax, [rbp+57h+var_60]
0x180016927  mov     [rsp+0C0h+var_90], rax
0x18001692c  lea     rax, [rbp+57h+var_70]
0x180016930  mov     [rsp+0C0h+var_98], rax
0x180016935  lea     rax, [rbp+57h+var_48]
0x180016939  mov     [rsp+0C0h+var_A0], rax
0x18001693e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180016943  lea     rcx, [rbp+57h+var_50]
0x180016947  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x18001694c  mov     eax, ebx
0x18001694e  mov     rcx, [rbp+57h+var_28]
0x180016952  xor     rcx, rsp; StackCookie
0x180016955  call    __security_check_cookie
0x18001695a  add     rsp, 0A0h
0x180016961  pop     r14
0x180016963  pop     rdi
0x180016964  pop     rsi
0x180016965  pop     rbx
0x180016966  pop     rbp
0x180016967  retn
```
