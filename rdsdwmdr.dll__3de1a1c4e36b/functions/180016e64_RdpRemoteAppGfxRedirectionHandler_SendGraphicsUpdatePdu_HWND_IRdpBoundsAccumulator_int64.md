# RdpRemoteAppGfxRedirectionHandler::SendGraphicsUpdatePdu(HWND__ *,IRdpBoundsAccumulator *,__int64)

- ea: `0x180016e64`
- end: `0x180017182`
- name: `?SendGraphicsUpdatePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@PEAVIRdpBoundsAccumulator@@_J@Z`
- size: `798`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this, HWND, struct IRdpBoundsAccumulator *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180015210`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x180013850`
- `0x1800144c8`
- `0x180016e64`
- `0x18002b960`
- `0x18002c010`

## string_xrefs

- `0x180016e8b`: `SendGraphicsUpdatePdu`
- `0x180016f04`: `Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_PDU`
- `0x1800170e8`: `Failed to send RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_PDU PDU`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::SendGraphicsUpdatePdu(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        struct IRdpBoundsAccumulator *a3,
        __int64 a4)
{
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // rax
  __int16 *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v21; // [rsp+50h] [rbp-59h] BYREF
  HWND v22; // [rsp+58h] [rbp-51h] BYREF
  CTSCriticalSection *v23; // [rsp+60h] [rbp-49h] BYREF
  const char *v24; // [rsp+68h] [rbp-41h] BYREF
  const char *v25; // [rsp+70h] [rbp-39h] BYREF
  const char *v26; // [rsp+78h] [rbp-31h] BYREF
  __int64 v27; // [rsp+80h] [rbp-29h] BYREF
  __int128 v28; // [rsp+88h] [rbp-21h] BYREF
  __int128 v29; // [rsp+98h] [rbp-11h] BYREF
  __int128 v30; // [rsp+A8h] [rbp-1h]
  __int64 v31; // [rsp+B8h] [rbp+Fh]

  v31 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v28 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v22 = a2;
    v21 = "SendGraphicsUpdatePdu";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)word_18003C2AA,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)&v21,
      (__int64)&v22);
  }
  v8 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(this);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = "SendGraphicsUpdatePdu";
      v26 = "Channel not initialized. Dropping RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_PDU";
      LODWORD(v21) = 1230;
      v25 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v23 = (CTSCriticalSection *)"Error HResult failed";
      LODWORD(v22) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&unk_18003C248,
        v9,
        v10,
        (const unsigned __int16 **)&v23,
        (__int64)&v22,
        (const unsigned __int16 **)&v25,
        (__int64)&v21,
        (const unsigned __int16 **)&v24,
        (const unsigned __int16 **)&v26);
    }
    goto LABEL_21;
  }
  v8 = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, __int128 *))(*(_QWORD *)a3 + 152LL))(a3, &v28);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_21;
    v14 = "Failed to get dirty rectangles bounding area";
    LODWORD(v22) = 1236;
    v15 = &word_18003C1E6;
    goto LABEL_20;
  }
  if ( (*(unsigned int (__fastcall **)(struct IRdpBoundsAccumulator *))(*(_QWORD *)a3 + 136LL))(a3) )
  {
    v8 = 0;
    goto LABEL_21;
  }
  v23 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64);
  CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64));
  if ( *((_QWORD *)this + 12) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v27);
    v16 = *((_QWORD *)this + 12);
    v27 = v16;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v27);
  }
  else
  {
    v16 = 0;
  }
  CTSAutoLock::~CTSAutoLock(&v23);
  if ( v16 )
  {
    *((_QWORD *)&v30 + 1) = v28;
    LODWORD(v31) = DWORD2(v28) - v28;
    HIDWORD(v31) = HIDWORD(v28) - DWORD1(v28);
    *(_QWORD *)&v29 = 0x2800000002LL;
    *(_QWORD *)&v30 = a2;
    *((_QWORD *)&v29 + 1) = a4;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, 40, &v29, 0);
    if ( v8 >= 0 || (unsigned int)dword_180044008 <= 2 )
      goto LABEL_21;
    v14 = "Failed to send RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_PDU PDU";
    LODWORD(v22) = 1270;
    v15 = word_18003C12A;
LABEL_20:
    v23 = (CTSCriticalSection *)v14;
    v24 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v26 = "Error HResult failed";
    LODWORD(v21) = v8;
    v25 = "SendGraphicsUpdatePdu";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (__int64)v15,
      v12,
      v13,
      (const unsigned __int16 **)&v26,
      (__int64)&v21,
      (const unsigned __int16 **)&v24,
      (__int64)&v22,
      (const unsigned __int16 **)&v25,
      (const unsigned __int16 **)&v23);
    goto LABEL_21;
  }
  v8 = -2147467261;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v23 = (CTSCriticalSection *)"SendGraphicsUpdatePdu";
    v25 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    LODWORD(v22) = 1252;
    v24 = "Unexpected NULL object";
    LODWORD(v21) = -2147467261;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (__int64)&dword_18003C18C,
      v18,
      v19,
      (const unsigned __int16 **)&v24,
      (__int64)&v21,
      (const unsigned __int16 **)&v25,
      (__int64)&v22,
      (const unsigned __int16 **)&v23);
  }
LABEL_21:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016e64  push    rbp
0x180016e66  push    rbx
0x180016e67  push    rsi
0x180016e68  push    rdi
0x180016e69  push    r12
0x180016e6b  push    r14
0x180016e6d  push    r15
0x180016e6f  lea     rbp, [rsp-27h]
0x180016e74  sub     rsp, 0D0h
0x180016e7b  mov     rax, cs:__security_cookie
0x180016e82  xor     rax, rsp
0x180016e85  mov     [rbp+57h+var_40], rax
0x180016e89  xor     eax, eax
0x180016e8b  lea     r12, aSendgraphicsup; "SendGraphicsUpdatePdu"
0x180016e92  xorps   xmm0, xmm0
0x180016e95  mov     [rbp+57h+var_48], rax
0x180016e99  mov     [rbp+57h+var_80], rax
0x180016e9d  mov     r15, r9
0x180016ea0  mov     eax, cs:dword_180044008
0x180016ea6  mov     rsi, r8
0x180016ea9  mov     r14, rdx
0x180016eac  mov     rdi, rcx
0x180016eaf  movups  [rbp+57h+var_68], xmm0
0x180016eb3  movups  [rbp+57h+var_58], xmm0
0x180016eb7  movdqu  [rbp+57h+var_78], xmm0
0x180016ebc  cmp     eax, 5
0x180016ebf  jbe     short loc_180016EE7
0x180016ec1  lea     rax, [rbp+57h+var_A8]
0x180016ec5  mov     [rbp+57h+var_A8], rdx
0x180016ec9  mov     [rsp+100h+var_D8], rax
0x180016ece  lea     rdx, word_18003C2AA
0x180016ed5  lea     rax, [rbp+57h+var_B0]
0x180016ed9  mov     [rbp+57h+var_B0], r12
0x180016edd  mov     [rsp+100h+var_E0], rax
0x180016ee2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180016ee7  mov     rcx, rdi; this
0x180016eea  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x180016eef  mov     ebx, eax
0x180016ef1  test    eax, eax
0x180016ef3  jns     short loc_180016F70
0x180016ef5  mov     ecx, cs:dword_180044008
0x180016efb  cmp     ecx, 2
0x180016efe  jbe     loc_180017159
0x180016f04  lea     rax, aChannelNotInit; "Channel not initialized. Dropping RDPXR"...
0x180016f0b  mov     [rbp+57h+var_98], r12
0x180016f0f  mov     [rbp+57h+var_88], rax
0x180016f13  lea     rdx, unk_18003C248
0x180016f1a  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180016f21  mov     dword ptr [rbp+57h+var_B0], 4CEh
0x180016f28  mov     [rbp+57h+var_90], rax
0x180016f2c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180016f33  mov     [rbp+57h+var_A0], rax
0x180016f37  lea     rax, [rbp+57h+var_88]
0x180016f3b  mov     [rsp+100h+var_B8], rax
0x180016f40  lea     rax, [rbp+57h+var_98]
0x180016f44  mov     [rsp+100h+var_C0], rax
0x180016f49  lea     rax, [rbp+57h+var_B0]
0x180016f4d  mov     [rsp+100h+var_C8], rax
0x180016f52  lea     rax, [rbp+57h+var_90]
0x180016f56  mov     [rsp+100h+var_D0], rax
0x180016f5b  lea     rax, [rbp+57h+var_A8]
0x180016f5f  mov     [rsp+100h+var_D8], rax
0x180016f64  lea     rax, [rbp+57h+var_A0]
0x180016f68  mov     dword ptr [rbp+57h+var_A8], ebx
0x180016f6b  jmp     loc_18001714F
0x180016f70  mov     rax, [rsi]
0x180016f73  lea     rdx, [rbp+57h+var_78]
0x180016f77  mov     rcx, rsi
0x180016f7a  mov     rax, [rax+98h]
0x180016f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f86  mov     ebx, eax
0x180016f88  test    eax, eax
0x180016f8a  jns     short loc_180016FB5
0x180016f8c  mov     eax, cs:dword_180044008
0x180016f92  cmp     eax, 2
0x180016f95  jbe     loc_180017159
0x180016f9b  lea     rax, aFailedToGetDir; "Failed to get dirty rectangles bounding"...
0x180016fa2  mov     dword ptr [rbp+57h+var_A8], 4D4h
0x180016fa9  lea     rdx, word_18003C1E6
0x180016fb0  jmp     loc_1800170FD
0x180016fb5  mov     rax, [rsi]
0x180016fb8  mov     rcx, rsi
0x180016fbb  mov     rax, [rax+88h]
0x180016fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc7  test    eax, eax
0x180016fc9  jz      short loc_180016FD2
0x180016fcb  xor     ebx, ebx
0x180016fcd  jmp     loc_180017159
0x180016fd2  lea     rcx, [rdi+40h]; this
0x180016fd6  mov     [rbp+57h+var_A0], rcx
0x180016fda  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180016fdf  cmp     qword ptr [rdi+60h], 0
0x180016fe4  jnz     short loc_180016FEA
0x180016fe6  xor     ebx, ebx
0x180016fe8  jmp     short loc_180017004
0x180016fea  lea     rcx, [rbp+57h+var_80]
0x180016fee  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180016ff3  mov     rbx, [rdi+60h]
0x180016ff7  lea     rcx, [rbp+57h+var_80]
0x180016ffb  mov     [rbp+57h+var_80], rbx
0x180016fff  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180017004  lea     rcx, [rbp+57h+var_A0]; this
0x180017008  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18001700d  test    rbx, rbx
0x180017010  jnz     short loc_180017088
0x180017012  mov     eax, cs:dword_180044008
0x180017018  mov     ebx, 80004003h
0x18001701d  cmp     eax, 2
0x180017020  jbe     loc_180017159
0x180017026  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001702d  mov     [rbp+57h+var_A0], r12
0x180017031  mov     [rbp+57h+var_90], rax
0x180017035  lea     rdx, dword_18003C18C
0x18001703c  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180017043  mov     dword ptr [rbp+57h+var_A8], 4E4h
0x18001704a  mov     [rbp+57h+var_98], rax
0x18001704e  lea     rax, [rbp+57h+var_A0]
0x180017052  mov     [rsp+100h+var_C0], rax
0x180017057  lea     rax, [rbp+57h+var_A8]
0x18001705b  mov     [rsp+100h+var_C8], rax
0x180017060  lea     rax, [rbp+57h+var_90]
0x180017064  mov     [rsp+100h+var_D0], rax
0x180017069  lea     rax, [rbp+57h+var_B0]
0x18001706d  mov     [rsp+100h+var_D8], rax
0x180017072  lea     rax, [rbp+57h+var_98]
0x180017076  mov     [rsp+100h+var_E0], rax
0x18001707b  mov     dword ptr [rbp+57h+var_B0], ebx
0x18001707e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180017083  jmp     loc_180017159
0x180017088  mov     r8d, dword ptr [rbp+57h+var_78]
0x18001708c  mov     edx, 28h ; '('
0x180017091  mov     r9d, dword ptr [rbp+57h+var_78+4]
0x180017095  mov     rcx, rbx
0x180017098  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18001709b  sub     eax, r8d
0x18001709e  mov     dword ptr [rbp+57h+var_58+8], r8d
0x1800170a2  mov     dword ptr [rbp+57h+var_48], eax
0x1800170a5  lea     r8, [rbp+57h+var_68]
0x1800170a9  mov     eax, dword ptr [rbp+57h+var_78+0Ch]
0x1800170ac  sub     eax, r9d
0x1800170af  mov     dword ptr [rbp+57h+var_58+0Ch], r9d
0x1800170b3  mov     dword ptr [rbp+57h+var_48+4], eax
0x1800170b6  xor     r9d, r9d
0x1800170b9  mov     dword ptr [rbp+57h+var_68], 2
0x1800170c0  mov     dword ptr [rbp+57h+var_68+4], edx
0x1800170c3  mov     qword ptr [rbp+57h+var_58], r14
0x1800170c7  mov     qword ptr [rbp+57h+var_68+8], r15
0x1800170cb  mov     rax, [rbx]
0x1800170ce  mov     rax, [rax+18h]
0x1800170d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d7  mov     ebx, eax
0x1800170d9  test    eax, eax
0x1800170db  jns     short loc_180017159
0x1800170dd  mov     eax, cs:dword_180044008
0x1800170e3  cmp     eax, 2
0x1800170e6  jbe     short loc_180017159
0x1800170e8  lea     rax, aFailedToSendRd; "Failed to send RDPXREMOTEAPPGFXREDIRECT"...
0x1800170ef  mov     dword ptr [rbp+57h+var_A8], 4F6h
0x1800170f6  lea     rdx, word_18003C12A
0x1800170fd  mov     [rbp+57h+var_A0], rax
0x180017101  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017108  mov     [rbp+57h+var_98], rax
0x18001710c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180017113  mov     [rbp+57h+var_88], rax
0x180017117  lea     rax, [rbp+57h+var_A0]
0x18001711b  mov     [rsp+100h+var_B8], rax
0x180017120  lea     rax, [rbp+57h+var_90]
0x180017124  mov     [rsp+100h+var_C0], rax
0x180017129  lea     rax, [rbp+57h+var_A8]
0x18001712d  mov     [rsp+100h+var_C8], rax
0x180017132  lea     rax, [rbp+57h+var_98]
0x180017136  mov     [rsp+100h+var_D0], rax
0x18001713b  lea     rax, [rbp+57h+var_B0]
0x18001713f  mov     [rsp+100h+var_D8], rax
0x180017144  lea     rax, [rbp+57h+var_88]
0x180017148  mov     dword ptr [rbp+57h+var_B0], ebx
0x18001714b  mov     [rbp+57h+var_90], r12
0x18001714f  mov     [rsp+100h+var_E0], rax
0x180017154  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017159  lea     rcx, [rbp+57h+var_80]
0x18001715d  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180017162  mov     eax, ebx
0x180017164  mov     rcx, [rbp+57h+var_40]
0x180017168  xor     rcx, rsp; StackCookie
0x18001716b  call    __security_check_cookie
0x180017170  add     rsp, 0D0h
0x180017177  pop     r15
0x180017179  pop     r14
0x18001717b  pop     r12
0x18001717d  pop     rdi
0x18001717e  pop     rsi
0x18001717f  pop     rbx
0x180017180  pop     rbp
0x180017181  retn
```
