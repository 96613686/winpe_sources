# RdpRemoteAppGfxRedirectionHandler::SendDeleteSurfacePdu(HWND__ *)

- ea: `0x180016970`
- end: `0x180016bd5`
- name: `?SendDeleteSurfacePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180015ff0`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x180013850`
- `0x1800144c8`
- `0x180016970`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x1800169c5`: `Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_DELETE_SURFACE_PDU`
- `0x1800169de`: `SendDeleteSurfacePdu`
- `0x180016a8c`: `SendDeleteSurfacePdu`
- `0x180016b4c`: `SendDeleteSurfacePdu`
- `0x180016b33`: `Failed to send XREMOTEAPPGFXREDIRECTION_PDU_TYPE_DELETE_SURFACE PDU`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::SendDeleteSurfacePdu(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+50h] [rbp-9h] BYREF
  int v16; // [rsp+54h] [rbp-5h] BYREF
  CTSCriticalSection *v17; // [rsp+58h] [rbp-1h] BYREF
  const char *v18; // [rsp+60h] [rbp+7h] BYREF
  const char *v19; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+70h] [rbp+17h] BYREF
  const char *v21; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v22; // [rsp+80h] [rbp+27h] BYREF

  v20 = 0;
  v22 = 0;
  v4 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(this);
  if ( v4 >= 0 )
  {
    v17 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64);
    CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64));
    if ( *((_QWORD *)this + 12) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v20);
      v7 = *((_QWORD *)this + 12);
      v20 = v7;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v20);
    }
    else
    {
      v7 = 0;
    }
    CTSAutoLock::~CTSAutoLock(&v17);
    if ( v7 )
    {
      *(_QWORD *)&v22 = 0x1000000005LL;
      *((_QWORD *)&v22 + 1) = a2;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, 16, &v22, 0);
      if ( v4 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v16 = 1311;
        v17 = (CTSCriticalSection *)"Failed to send XREMOTEAPPGFXREDIRECTION_PDU_TYPE_DELETE_SURFACE PDU";
        v15 = v4;
        v19 = "SendDeleteSurfacePdu";
        v18 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v21 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (__int64)&dword_18003C00C,
          v12,
          v13,
          (const unsigned __int16 **)&v21,
          (__int64)&v15,
          (const unsigned __int16 **)&v18,
          (__int64)&v16,
          (const unsigned __int16 **)&v19,
          (const unsigned __int16 **)&v17);
      }
    }
    else
    {
      v4 = -2147467261;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v16 = 1298;
        v17 = (CTSCriticalSection *)"SendDeleteSurfacePdu";
        v15 = -2147467261;
        v19 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v18 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v8,
          (__int64)&word_18003C06E,
          v9,
          v10,
          (const unsigned __int16 **)&v18,
          (__int64)&v15,
          (const unsigned __int16 **)&v19,
          (__int64)&v16,
          (const unsigned __int16 **)&v17);
      }
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v15 = 1291;
    v21 = "Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_DELETE_SURFACE_PDU";
    v16 = v4;
    v18 = "SendDeleteSurfacePdu";
    v19 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v17 = (CTSCriticalSection *)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&unk_18003C0C8,
      v5,
      v6,
      (const unsigned __int16 **)&v17,
      (__int64)&v16,
      (const unsigned __int16 **)&v19,
      (__int64)&v15,
      (const unsigned __int16 **)&v18,
      (const unsigned __int16 **)&v21);
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016970  mov     [rsp-8+arg_10], rbx
0x180016975  push    rbp
0x180016976  push    rsi
0x180016977  push    rdi
0x180016978  lea     rbp, [rsp-47h]
0x18001697d  sub     rsp, 0A0h
0x180016984  mov     rax, cs:__security_cookie
0x18001698b  xor     rax, rsp
0x18001698e  mov     [rbp+57h+var_20], rax
0x180016992  xorps   xmm0, xmm0
0x180016995  mov     [rbp+57h+var_40], 0
0x18001699d  movups  [rbp+57h+var_30], xmm0
0x1800169a1  mov     rsi, rdx
0x1800169a4  mov     rdi, rcx
0x1800169a7  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x1800169ac  mov     ebx, eax
0x1800169ae  test    eax, eax
0x1800169b0  jns     loc_180016A38
0x1800169b6  mov     ecx, cs:dword_180044008
0x1800169bc  cmp     ecx, 2
0x1800169bf  jbe     loc_180016BAB
0x1800169c5  lea     rax, aChannelNotInit_10; "Channel not initialized. Dropping RDPXR"...
0x1800169cc  mov     [rbp+57h+var_60], 50Bh
0x1800169d3  mov     [rbp+57h+var_38], rax
0x1800169d7  lea     rdx, unk_18003C0C8
0x1800169de  lea     rax, aSenddeletesurf; "SendDeleteSurfacePdu"
0x1800169e5  mov     [rbp+57h+var_5C], ebx
0x1800169e8  mov     [rbp+57h+var_50], rax
0x1800169ec  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800169f3  mov     [rbp+57h+var_48], rax
0x1800169f7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800169fe  mov     [rbp+57h+var_58], rax
0x180016a02  lea     rax, [rbp+57h+var_38]
0x180016a06  mov     [rsp+0B0h+var_68], rax
0x180016a0b  lea     rax, [rbp+57h+var_50]
0x180016a0f  mov     [rsp+0B0h+var_70], rax
0x180016a14  lea     rax, [rbp+57h+var_60]
0x180016a18  mov     [rsp+0B0h+var_78], rax
0x180016a1d  lea     rax, [rbp+57h+var_48]
0x180016a21  mov     [rsp+0B0h+var_80], rax
0x180016a26  lea     rax, [rbp+57h+var_5C]
0x180016a2a  mov     [rsp+0B0h+var_88], rax
0x180016a2f  lea     rax, [rbp+57h+var_58]
0x180016a33  jmp     loc_180016BA1
0x180016a38  lea     rcx, [rdi+40h]; this
0x180016a3c  mov     [rbp+57h+var_58], rcx
0x180016a40  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180016a45  cmp     qword ptr [rdi+60h], 0
0x180016a4a  jnz     short loc_180016A50
0x180016a4c  xor     ebx, ebx
0x180016a4e  jmp     short loc_180016A6A
0x180016a50  lea     rcx, [rbp+57h+var_40]
0x180016a54  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180016a59  mov     rbx, [rdi+60h]
0x180016a5d  lea     rcx, [rbp+57h+var_40]
0x180016a61  mov     [rbp+57h+var_40], rbx
0x180016a65  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180016a6a  lea     rcx, [rbp+57h+var_58]; this
0x180016a6e  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180016a73  test    rbx, rbx
0x180016a76  jnz     short loc_180016AF5
0x180016a78  mov     eax, cs:dword_180044008
0x180016a7e  mov     ebx, 80004003h
0x180016a83  cmp     eax, 2
0x180016a86  jbe     loc_180016BAB
0x180016a8c  lea     rax, aSenddeletesurf; "SendDeleteSurfacePdu"
0x180016a93  mov     [rbp+57h+var_5C], 512h
0x180016a9a  mov     [rbp+57h+var_58], rax
0x180016a9e  lea     rdx, word_18003C06E
0x180016aa5  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016aac  mov     [rbp+57h+var_60], ebx
0x180016aaf  mov     [rbp+57h+var_48], rax
0x180016ab3  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180016aba  mov     [rbp+57h+var_50], rax
0x180016abe  lea     rax, [rbp+57h+var_58]
0x180016ac2  mov     [rsp+0B0h+var_70], rax
0x180016ac7  lea     rax, [rbp+57h+var_5C]
0x180016acb  mov     [rsp+0B0h+var_78], rax
0x180016ad0  lea     rax, [rbp+57h+var_48]
0x180016ad4  mov     [rsp+0B0h+var_80], rax
0x180016ad9  lea     rax, [rbp+57h+var_60]
0x180016add  mov     [rsp+0B0h+var_88], rax
0x180016ae2  lea     rax, [rbp+57h+var_50]
0x180016ae6  mov     [rsp+0B0h+var_90], rax
0x180016aeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016af0  jmp     loc_180016BAB
0x180016af5  mov     edx, 10h
0x180016afa  mov     dword ptr [rbp+57h+var_30], 5
0x180016b01  mov     dword ptr [rbp+57h+var_30+4], edx
0x180016b04  lea     r8, [rbp+57h+var_30]
0x180016b08  mov     qword ptr [rbp+57h+var_30+8], rsi
0x180016b0c  xor     r9d, r9d
0x180016b0f  mov     rax, [rbx]
0x180016b12  mov     rcx, rbx
0x180016b15  mov     rax, [rax+18h]
0x180016b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b1e  mov     ebx, eax
0x180016b20  test    eax, eax
0x180016b22  jns     loc_180016BAB
0x180016b28  mov     eax, cs:dword_180044008
0x180016b2e  cmp     eax, 2
0x180016b31  jbe     short loc_180016BAB
0x180016b33  lea     rax, aFailedToSendXr_6; "Failed to send XREMOTEAPPGFXREDIRECTION"...
0x180016b3a  mov     [rbp+57h+var_5C], 51Fh
0x180016b41  mov     [rbp+57h+var_58], rax
0x180016b45  lea     rdx, dword_18003C00C
0x180016b4c  lea     rax, aSenddeletesurf; "SendDeleteSurfacePdu"
0x180016b53  mov     [rbp+57h+var_60], ebx
0x180016b56  mov     [rbp+57h+var_48], rax
0x180016b5a  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016b61  mov     [rbp+57h+var_50], rax
0x180016b65  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180016b6c  mov     [rbp+57h+var_38], rax
0x180016b70  lea     rax, [rbp+57h+var_58]
0x180016b74  mov     [rsp+0B0h+var_68], rax
0x180016b79  lea     rax, [rbp+57h+var_48]
0x180016b7d  mov     [rsp+0B0h+var_70], rax
0x180016b82  lea     rax, [rbp+57h+var_5C]
0x180016b86  mov     [rsp+0B0h+var_78], rax
0x180016b8b  lea     rax, [rbp+57h+var_50]
0x180016b8f  mov     [rsp+0B0h+var_80], rax
0x180016b94  lea     rax, [rbp+57h+var_60]
0x180016b98  mov     [rsp+0B0h+var_88], rax
0x180016b9d  lea     rax, [rbp+57h+var_38]
0x180016ba1  mov     [rsp+0B0h+var_90], rax
0x180016ba6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180016bab  lea     rcx, [rbp+57h+var_40]
0x180016baf  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180016bb4  mov     eax, ebx
0x180016bb6  mov     rcx, [rbp+57h+var_20]
0x180016bba  xor     rcx, rsp; StackCookie
0x180016bbd  call    __security_check_cookie
0x180016bc2  mov     rbx, [rsp+0B0h+arg_10]
0x180016bca  add     rsp, 0A0h
0x180016bd1  pop     rdi
0x180016bd2  pop     rsi
0x180016bd3  pop     rbp
0x180016bd4  retn
```
