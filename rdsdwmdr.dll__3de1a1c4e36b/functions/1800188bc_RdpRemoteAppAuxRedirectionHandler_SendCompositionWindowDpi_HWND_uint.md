# RdpRemoteAppAuxRedirectionHandler::SendCompositionWindowDpi(HWND__ *,uint)

- ea: `0x1800188bc`
- end: `0x180018b23`
- name: `?SendCompositionWindowDpi@RdpRemoteAppAuxRedirectionHandler@@IEAAJPEAUHWND__@@I@Z`
- size: `615`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *__hidden this, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017ed0`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x1800144c8`
- `0x180017a78`
- `0x1800188bc`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x180018914`: `Channel not initialized. Dropping RDPXREMOTEAPPAUXREDIRECTION_COMPOSITION_WINDOW_DPI_PDU`
- `0x18001892d`: `SendCompositionWindowDpi`
- `0x1800189db`: `SendCompositionWindowDpi`
- `0x180018a9f`: `SendCompositionWindowDpi`
- `0x180018a86`: `Failed to send XREMOTEAPPAUXREDIRECTION_PDU_TYPE_COMPOSITION_WINDOW_DPI PDU`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::SendCompositionWindowDpi(
        RdpRemoteAppAuxRedirectionHandler *this,
        HWND a2,
        int a3)
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
  int v25; // [rsp+90h] [rbp+27h]

  v24 = 0;
  v25 = 0;
  v22 = 0;
  v6 = RdpRemoteAppAuxRedirectionHandler::EnsureChannelInitialized(this);
  if ( v6 >= 0 )
  {
    v19 = (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64);
    CTSCriticalSection::Lock((RdpRemoteAppAuxRedirectionHandler *)((char *)this + 64));
    if ( *((_QWORD *)this + 10) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v22);
      v9 = *((_QWORD *)this + 10);
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
      *(_QWORD *)&v24 = 0x1400000005LL;
      *((_QWORD *)&v24 + 1) = a2;
      v25 = a3;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, 20, &v24, 0);
      if ( v6 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v18 = 737;
        v19 = (CTSCriticalSection *)"Failed to send XREMOTEAPPAUXREDIRECTION_PDU_TYPE_COMPOSITION_WINDOW_DPI PDU";
        v17 = v6;
        v21 = "SendCompositionWindowDpi";
        v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v23 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v13,
          (__int64)&dword_18003D9BC,
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
        v18 = 723;
        v19 = (CTSCriticalSection *)"SendCompositionWindowDpi";
        v17 = -2147467261;
        v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v20 = "Unexpected NULL object";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (__int64)&word_18003DA1E,
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
    v17 = 716;
    v23 = "Channel not initialized. Dropping RDPXREMOTEAPPAUXREDIRECTION_COMPOSITION_WINDOW_DPI_PDU";
    v18 = v6;
    v20 = "SendCompositionWindowDpi";
    v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
    v19 = (CTSCriticalSection *)"Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&unk_18003DA78,
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
0x1800188bc  push    rbp
0x1800188be  push    rbx
0x1800188bf  push    rsi
0x1800188c0  push    rdi
0x1800188c1  push    r14
0x1800188c3  lea     rbp, [rsp-37h]
0x1800188c8  sub     rsp, 0A0h
0x1800188cf  mov     rax, cs:__security_cookie
0x1800188d6  xor     rax, rsp
0x1800188d9  mov     [rbp+57h+var_28], rax
0x1800188dd  xor     eax, eax
0x1800188df  xorps   xmm0, xmm0
0x1800188e2  movups  [rbp+57h+var_40], xmm0
0x1800188e6  mov     [rbp+57h+var_30], eax
0x1800188e9  mov     r14d, r8d
0x1800188ec  mov     [rbp+57h+var_50], rax
0x1800188f0  mov     rsi, rdx
0x1800188f3  mov     rdi, rcx
0x1800188f6  call    ?EnsureChannelInitialized@RdpRemoteAppAuxRedirectionHandler@@IEAAJXZ; RdpRemoteAppAuxRedirectionHandler::EnsureChannelInitialized(void)
0x1800188fb  mov     ebx, eax
0x1800188fd  test    eax, eax
0x1800188ff  jns     loc_180018987
0x180018905  mov     ecx, cs:dword_180044008
0x18001890b  cmp     ecx, 2
0x18001890e  jbe     loc_180018AFE
0x180018914  lea     rax, aChannelNotInit_7; "Channel not initialized. Dropping RDPXR"...
0x18001891b  mov     [rbp+57h+var_70], 2CCh
0x180018922  mov     [rbp+57h+var_48], rax
0x180018926  lea     rdx, unk_18003DA78
0x18001892d  lea     rax, aSendcompositio; "SendCompositionWindowDpi"
0x180018934  mov     [rbp+57h+var_6C], ebx
0x180018937  mov     [rbp+57h+var_60], rax
0x18001893b  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018942  mov     [rbp+57h+var_58], rax
0x180018946  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001894d  mov     [rbp+57h+var_68], rax
0x180018951  lea     rax, [rbp+57h+var_48]
0x180018955  mov     [rsp+0C0h+var_78], rax
0x18001895a  lea     rax, [rbp+57h+var_60]
0x18001895e  mov     [rsp+0C0h+var_80], rax
0x180018963  lea     rax, [rbp+57h+var_70]
0x180018967  mov     [rsp+0C0h+var_88], rax
0x18001896c  lea     rax, [rbp+57h+var_58]
0x180018970  mov     [rsp+0C0h+var_90], rax
0x180018975  lea     rax, [rbp+57h+var_6C]
0x180018979  mov     [rsp+0C0h+var_98], rax
0x18001897e  lea     rax, [rbp+57h+var_68]
0x180018982  jmp     loc_180018AF4
0x180018987  lea     rcx, [rdi+40h]; this
0x18001898b  mov     [rbp+57h+var_68], rcx
0x18001898f  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180018994  cmp     qword ptr [rdi+50h], 0
0x180018999  jnz     short loc_18001899F
0x18001899b  xor     ebx, ebx
0x18001899d  jmp     short loc_1800189B9
0x18001899f  lea     rcx, [rbp+57h+var_50]
0x1800189a3  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800189a8  mov     rbx, [rdi+50h]
0x1800189ac  lea     rcx, [rbp+57h+var_50]
0x1800189b0  mov     [rbp+57h+var_50], rbx
0x1800189b4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800189b9  lea     rcx, [rbp+57h+var_68]; this
0x1800189bd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800189c2  test    rbx, rbx
0x1800189c5  jnz     short loc_180018A44
0x1800189c7  mov     eax, cs:dword_180044008
0x1800189cd  mov     ebx, 80004003h
0x1800189d2  cmp     eax, 2
0x1800189d5  jbe     loc_180018AFE
0x1800189db  lea     rax, aSendcompositio; "SendCompositionWindowDpi"
0x1800189e2  mov     [rbp+57h+var_6C], 2D3h
0x1800189e9  mov     [rbp+57h+var_68], rax
0x1800189ed  lea     rdx, word_18003DA1E
0x1800189f4  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800189fb  mov     [rbp+57h+var_70], ebx
0x1800189fe  mov     [rbp+57h+var_58], rax
0x180018a02  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180018a09  mov     [rbp+57h+var_60], rax
0x180018a0d  lea     rax, [rbp+57h+var_68]
0x180018a11  mov     [rsp+0C0h+var_80], rax
0x180018a16  lea     rax, [rbp+57h+var_6C]
0x180018a1a  mov     [rsp+0C0h+var_88], rax
0x180018a1f  lea     rax, [rbp+57h+var_58]
0x180018a23  mov     [rsp+0C0h+var_90], rax
0x180018a28  lea     rax, [rbp+57h+var_70]
0x180018a2c  mov     [rsp+0C0h+var_98], rax
0x180018a31  lea     rax, [rbp+57h+var_60]
0x180018a35  mov     [rsp+0C0h+var_A0], rax
0x180018a3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018a3f  jmp     loc_180018AFE
0x180018a44  mov     edx, 14h
0x180018a49  mov     dword ptr [rbp+57h+var_40], 5
0x180018a50  mov     dword ptr [rbp+57h+var_40+4], edx
0x180018a53  lea     r8, [rbp+57h+var_40]
0x180018a57  mov     qword ptr [rbp+57h+var_40+8], rsi
0x180018a5b  xor     r9d, r9d
0x180018a5e  mov     [rbp+57h+var_30], r14d
0x180018a62  mov     rcx, rbx
0x180018a65  mov     rax, [rbx]
0x180018a68  mov     rax, [rax+18h]
0x180018a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a71  mov     ebx, eax
0x180018a73  test    eax, eax
0x180018a75  jns     loc_180018AFE
0x180018a7b  mov     eax, cs:dword_180044008
0x180018a81  cmp     eax, 2
0x180018a84  jbe     short loc_180018AFE
0x180018a86  lea     rax, aFailedToSendXr_8; "Failed to send XREMOTEAPPAUXREDIRECTION"...
0x180018a8d  mov     [rbp+57h+var_6C], 2E1h
0x180018a94  mov     [rbp+57h+var_68], rax
0x180018a98  lea     rdx, dword_18003D9BC
0x180018a9f  lea     rax, aSendcompositio; "SendCompositionWindowDpi"
0x180018aa6  mov     [rbp+57h+var_70], ebx
0x180018aa9  mov     [rbp+57h+var_58], rax
0x180018aad  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018ab4  mov     [rbp+57h+var_60], rax
0x180018ab8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180018abf  mov     [rbp+57h+var_48], rax
0x180018ac3  lea     rax, [rbp+57h+var_68]
0x180018ac7  mov     [rsp+0C0h+var_78], rax
0x180018acc  lea     rax, [rbp+57h+var_58]
0x180018ad0  mov     [rsp+0C0h+var_80], rax
0x180018ad5  lea     rax, [rbp+57h+var_6C]
0x180018ad9  mov     [rsp+0C0h+var_88], rax
0x180018ade  lea     rax, [rbp+57h+var_60]
0x180018ae2  mov     [rsp+0C0h+var_90], rax
0x180018ae7  lea     rax, [rbp+57h+var_70]
0x180018aeb  mov     [rsp+0C0h+var_98], rax
0x180018af0  lea     rax, [rbp+57h+var_48]
0x180018af4  mov     [rsp+0C0h+var_A0], rax
0x180018af9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180018afe  lea     rcx, [rbp+57h+var_50]
0x180018b02  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180018b07  mov     eax, ebx
0x180018b09  mov     rcx, [rbp+57h+var_28]
0x180018b0d  xor     rcx, rsp; StackCookie
0x180018b10  call    __security_check_cookie
0x180018b15  add     rsp, 0A0h
0x180018b1c  pop     r14
0x180018b1e  pop     rdi
0x180018b1f  pop     rsi
0x180018b20  pop     rbx
0x180018b21  pop     rbp
0x180018b22  retn
```
