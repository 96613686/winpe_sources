# RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceCreated(HWND__ *,ushort const *,HDC__ *,uint,uint,uint,uint,int)

- ea: `0x180015bc0`
- end: `0x180015fe3`
- name: `?OnWndSurfaceCreated@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHWND__@@PEBGPEAUHDC__@@IIIIH@Z`
- size: `1059`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *this, HWND, const unsigned __int16 *, __int64, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x1800032d4`
- `0x180003314`
- `0x18000c4ec`
- `0x18000f068`
- `0x18000f08c`
- `0x180012e60`
- `0x180013850`
- `0x1800144c8`
- `0x180015bc0`
- `0x180017188`
- `0x18002c010`

## string_xrefs

- `0x180015be2`: `OnWndSurfaceCreated`
- `0x180015e52`: `OnWndSurfaceCreated`
- `0x180015f55`: `OnWndSurfaceCreated`
- `0x180015d05`: `Channel not initialized. Dropping PRDPXREMOTEAPPGFXREDIRECTION_CREATE_SURFACE_PDU`
- `0x180015ef8`: `StringCchCopyW failed to copy section name`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceCreated(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  __int16 *v20; // rdx
  const unsigned __int16 **v21; // rax
  int v22; // ebx
  int v23; // r14d
  void *v24; // rax
  unsigned int *v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  const char *v29; // rax
  __int16 *v30; // rdx
  const unsigned __int16 **v32; // [rsp+30h] [rbp-50h]
  const char **v33; // [rsp+40h] [rbp-40h]
  const char **v34; // [rsp+48h] [rbp-38h]
  HWND v35; // [rsp+50h] [rbp-30h] BYREF
  __int64 v36; // [rsp+58h] [rbp-28h] BYREF
  CTSCriticalSection *v37; // [rsp+60h] [rbp-20h] BYREF
  const char *v38; // [rsp+68h] [rbp-18h] BYREF
  const char *v39; // [rsp+70h] [rbp-10h] BYREF
  const char *v40; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int64 v41; // [rsp+B0h] [rbp+30h] BYREF

  v36 = 0;
  v41 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v35 = a2;
    v37 = (CTSCriticalSection *)"OnWndSurfaceCreated";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)&unk_18003CAA8,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)&v37,
      (__int64)&v35);
  }
  v37 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 16);
  CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 16));
  if ( *((_QWORD *)this + 6) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v36);
    v11 = *((_QWORD *)this + 6);
    v36 = v11;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v36);
  }
  else
  {
    v11 = 0;
  }
  CTSAutoLock::~CTSAutoLock(&v37);
  if ( v11 )
  {
    v15 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized((RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48));
    if ( v15 < 0 )
    {
      v19 = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_27;
      v38 = "OnWndSurfaceCreated";
      v39 = "Channel not initialized. Dropping PRDPXREMOTEAPPGFXREDIRECTION_CREATE_SURFACE_PDU";
      v20 = (__int16 *)&dword_18003C9EC;
      LODWORD(v41) = 906;
      v37 = (CTSCriticalSection *)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v40 = "Error HResult failed";
      v34 = &v39;
      v33 = &v38;
      v32 = (const unsigned __int16 **)&v37;
      v21 = (const unsigned __int16 **)&v40;
LABEL_12:
      LODWORD(v35) = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (__int64)v20,
        v17,
        v18,
        v21,
        (__int64)&v35,
        v32,
        (__int64)&v41,
        (const unsigned __int16 **)v33,
        (const unsigned __int16 **)v34);
      goto LABEL_27;
    }
    v15 = StringCchLengthW(a3, v16, &v41);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_27;
      v39 = "OnWndSurfaceCreated";
      v40 = "StringCchLengthW failed to determine length of section name";
      v20 = word_18003C98A;
      LODWORD(v41) = 912;
      v38 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v37 = (CTSCriticalSection *)"Error HResult failed";
      v34 = &v40;
      v33 = &v39;
      v32 = (const unsigned __int16 **)&v38;
      v21 = (const unsigned __int16 **)&v37;
      goto LABEL_12;
    }
    v22 = v41;
    v23 = 2 * v41 + 38;
    v24 = operator new(2 * v41 + 38);
    v25 = (unsigned int *)v24;
    if ( !v24 )
    {
      v15 = -2147024882;
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_27;
      LODWORD(v41) = 925;
      v40 = "Failed to allocate DPXREMOTEAPPGFXREDIRECTION_SHAREDMEM_SECTION_INFO_PDU";
      v20 = (__int16 *)&unk_18003C928;
      v39 = "OnWndSurfaceCreated";
      v38 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v37 = (CTSCriticalSection *)"Error condition failed";
      v34 = &v40;
      v33 = &v39;
      v32 = (const unsigned __int16 **)&v38;
      v21 = (const unsigned __int16 **)&v37;
      goto LABEL_12;
    }
    *(_DWORD *)v24 = 4;
    *((_DWORD *)v24 + 1) = v23;
    *((_DWORD *)v24 + 4) = a6;
    *((_DWORD *)v24 + 6) = a8;
    *((_DWORD *)v24 + 7) = a7;
    *((_DWORD *)v24 + 5) = a5;
    *((_QWORD *)v24 + 1) = a2;
    *((_DWORD *)v24 + 8) = v22 + 1;
    v15 = StringCchCopyW((unsigned __int16 *)v24 + 18, (unsigned int)(v22 + 1), a3);
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v11 + 24LL))(
              v11,
              v25[1],
              v25,
              0);
      if ( v15 >= 0 || (unsigned int)dword_180044008 <= 2 )
        goto LABEL_26;
      v29 = "Failed to send XREMOTEAPPGFXREDIRECTION_PDU_TYPE_SHAREDMEM_SECTION_INFO PDU";
      LODWORD(v41) = 946;
      v30 = (__int16 *)&dword_18003C864;
    }
    else
    {
      if ( (unsigned int)dword_180044008 <= 2 )
      {
LABEL_26:
        operator delete(v25);
        goto LABEL_27;
      }
      v29 = "StringCchCopyW failed to copy section name";
      LODWORD(v41) = 940;
      v30 = &word_18003C8C6;
    }
    v40 = v29;
    v39 = "OnWndSurfaceCreated";
    v38 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v37 = (CTSCriticalSection *)"Error HResult failed";
    LODWORD(v35) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v26,
      (__int64)v30,
      v27,
      v28,
      (const unsigned __int16 **)&v37,
      (__int64)&v35,
      (const unsigned __int16 **)&v38,
      (__int64)&v41,
      (const unsigned __int16 **)&v39,
      (const unsigned __int16 **)&v40);
    goto LABEL_26;
  }
  v15 = -2147467261;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v37 = (CTSCriticalSection *)"OnWndSurfaceCreated";
    v38 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    LODWORD(v41) = 900;
    v39 = "Unexpected NULL object";
    LODWORD(v35) = -2147467261;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v12,
      (__int64)&word_18003CA4E,
      v13,
      v14,
      (const unsigned __int16 **)&v39,
      (__int64)&v35,
      (const unsigned __int16 **)&v38,
      (__int64)&v41,
      (const unsigned __int16 **)&v37);
  }
LABEL_27:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v36);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180015bc0  mov     [rsp-28h+arg_8], rbx
0x180015bc5  mov     [rsp-28h+arg_10], rsi
0x180015bca  push    rbp
0x180015bcb  push    rdi
0x180015bcc  push    r12
0x180015bce  push    r14
0x180015bd0  push    r15
0x180015bd2  mov     rbp, rsp
0x180015bd5  sub     rsp, 80h
0x180015bdc  mov     eax, cs:dword_180044008
0x180015be2  lea     rdi, aOnwndsurfacecr; "OnWndSurfaceCreated"
0x180015be9  mov     [rbp+var_28], 0
0x180015bf1  mov     r12, r8
0x180015bf4  mov     [rbp+arg_0], 0
0x180015bfc  mov     r15, rdx
0x180015bff  mov     rbx, rcx
0x180015c02  cmp     eax, 5
0x180015c05  jbe     short loc_180015C2D
0x180015c07  lea     rax, [rbp+var_30]
0x180015c0b  mov     [rbp+var_30], rdx
0x180015c0f  mov     [rsp+80h+var_58], rax
0x180015c14  lea     rdx, unk_18003CAA8
0x180015c1b  lea     rax, [rbp+var_20]
0x180015c1f  mov     [rbp+var_20], rdi
0x180015c23  mov     [rsp+80h+var_60], rax
0x180015c28  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180015c2d  lea     rcx, [rbx+10h]; this
0x180015c31  mov     [rbp+var_20], rcx
0x180015c35  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180015c3a  cmp     qword ptr [rbx+30h], 0
0x180015c3f  jnz     short loc_180015C45
0x180015c41  xor     esi, esi
0x180015c43  jmp     short loc_180015C5F
0x180015c45  lea     rcx, [rbp+var_28]
0x180015c49  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180015c4e  mov     rsi, [rbx+30h]
0x180015c52  lea     rcx, [rbp+var_28]
0x180015c56  mov     [rbp+var_28], rsi
0x180015c5a  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180015c5f  lea     rcx, [rbp+var_20]; this
0x180015c63  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180015c68  test    rsi, rsi
0x180015c6b  jnz     short loc_180015CE3
0x180015c6d  mov     eax, cs:dword_180044008
0x180015c73  mov     ebx, 80004003h
0x180015c78  cmp     eax, 2
0x180015c7b  jbe     loc_180015FBC
0x180015c81  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015c88  mov     [rbp+var_20], rdi
0x180015c8c  mov     [rbp+var_18], rax
0x180015c90  lea     rdx, word_18003CA4E
0x180015c97  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180015c9e  mov     dword ptr [rbp+arg_0], 384h
0x180015ca5  mov     [rbp+var_10], rax
0x180015ca9  lea     rax, [rbp+var_20]
0x180015cad  mov     [rsp+80h+var_40], rax
0x180015cb2  lea     rax, [rbp+arg_0]
0x180015cb6  mov     [rsp+80h+var_48], rax
0x180015cbb  lea     rax, [rbp+var_18]
0x180015cbf  mov     [rsp+80h+var_50], rax
0x180015cc4  lea     rax, [rbp+var_30]
0x180015cc8  mov     [rsp+80h+var_58], rax
0x180015ccd  lea     rax, [rbp+var_10]
0x180015cd1  mov     [rsp+80h+var_60], rax
0x180015cd6  mov     dword ptr [rbp+var_30], ebx
0x180015cd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180015cde  jmp     loc_180015FBC
0x180015ce3  lea     rcx, [rbx-30h]; this
0x180015ce7  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x180015cec  mov     ebx, eax
0x180015cee  test    eax, eax
0x180015cf0  jns     loc_180015D7B
0x180015cf6  mov     ecx, cs:dword_180044008
0x180015cfc  cmp     ecx, 2
0x180015cff  jbe     loc_180015FBC
0x180015d05  lea     rax, aChannelNotInit_5; "Channel not initialized. Dropping PRDPX"...
0x180015d0c  mov     [rbp+var_18], rdi
0x180015d10  mov     [rbp+var_10], rax
0x180015d14  lea     rdx, dword_18003C9EC
0x180015d1b  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015d22  mov     dword ptr [rbp+arg_0], 38Ah
0x180015d29  mov     [rbp+var_20], rax
0x180015d2d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015d34  mov     [rbp+var_8], rax
0x180015d38  lea     rax, [rbp+var_10]
0x180015d3c  mov     [rsp+80h+var_38], rax
0x180015d41  lea     rax, [rbp+var_18]
0x180015d45  mov     [rsp+80h+var_40], rax
0x180015d4a  lea     rax, [rbp+arg_0]
0x180015d4e  mov     [rsp+80h+var_48], rax
0x180015d53  lea     rax, [rbp+var_20]
0x180015d57  mov     [rsp+80h+var_50], rax
0x180015d5c  lea     rax, [rbp+var_30]
0x180015d60  mov     [rsp+80h+var_58], rax
0x180015d65  lea     rax, [rbp+var_8]
0x180015d69  mov     dword ptr [rbp+var_30], ebx
0x180015d6c  mov     [rsp+80h+var_60], rax
0x180015d71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180015d76  jmp     loc_180015FBC
0x180015d7b  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x180015d7f  mov     rcx, r12; unsigned __int16 *
0x180015d82  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180015d87  mov     ebx, eax
0x180015d89  test    eax, eax
0x180015d8b  jns     short loc_180015E05
0x180015d8d  mov     eax, cs:dword_180044008
0x180015d93  cmp     eax, 2
0x180015d96  jbe     loc_180015FBC
0x180015d9c  lea     rax, aStringcchlengt; "StringCchLengthW failed to determine le"...
0x180015da3  mov     [rbp+var_10], rdi
0x180015da7  mov     [rbp+var_8], rax
0x180015dab  lea     rdx, word_18003C98A
0x180015db2  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015db9  mov     dword ptr [rbp+arg_0], 390h
0x180015dc0  mov     [rbp+var_18], rax
0x180015dc4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015dcb  mov     [rbp+var_20], rax
0x180015dcf  lea     rax, [rbp+var_8]
0x180015dd3  mov     [rsp+80h+var_38], rax
0x180015dd8  lea     rax, [rbp+var_10]
0x180015ddc  mov     [rsp+80h+var_40], rax
0x180015de1  lea     rax, [rbp+arg_0]
0x180015de5  mov     [rsp+80h+var_48], rax
0x180015dea  lea     rax, [rbp+var_18]
0x180015dee  mov     [rsp+80h+var_50], rax
0x180015df3  lea     rax, [rbp+var_30]
0x180015df7  mov     [rsp+80h+var_58], rax
0x180015dfc  lea     rax, [rbp+var_20]
0x180015e00  jmp     loc_180015D69
0x180015e05  mov     rbx, [rbp+arg_0]
0x180015e09  lea     r14, ds:26h[rbx*2]
0x180015e11  mov     rcx, r14; Size
0x180015e14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015e19  mov     rdi, rax
0x180015e1c  test    rax, rax
0x180015e1f  jnz     loc_180015EA9
0x180015e25  mov     eax, cs:dword_180044008
0x180015e2b  mov     ebx, 8007000Eh
0x180015e30  cmp     eax, 2
0x180015e33  jbe     loc_180015FBC
0x180015e39  lea     rax, aFailedToAlloca_4; "Failed to allocate DPXREMOTEAPPGFXREDIR"...
0x180015e40  mov     dword ptr [rbp+arg_0], 39Dh
0x180015e47  mov     [rbp+var_8], rax
0x180015e4b  lea     rdx, unk_18003C928
0x180015e52  lea     rax, aOnwndsurfacecr; "OnWndSurfaceCreated"
0x180015e59  mov     [rbp+var_10], rax
0x180015e5d  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015e64  mov     [rbp+var_18], rax
0x180015e68  lea     rax, aErrorCondition; "Error condition failed"
0x180015e6f  mov     [rbp+var_20], rax
0x180015e73  lea     rax, [rbp+var_8]
0x180015e77  mov     [rsp+80h+var_38], rax
0x180015e7c  lea     rax, [rbp+var_10]
0x180015e80  mov     [rsp+80h+var_40], rax
0x180015e85  lea     rax, [rbp+arg_0]
0x180015e89  mov     [rsp+80h+var_48], rax
0x180015e8e  lea     rax, [rbp+var_18]
0x180015e92  mov     [rsp+80h+var_50], rax
0x180015e97  lea     rax, [rbp+var_30]
0x180015e9b  mov     [rsp+80h+var_58], rax
0x180015ea0  lea     rax, [rbp+var_20]
0x180015ea4  jmp     loc_180015D69
0x180015ea9  mov     dword ptr [rax], 4
0x180015eaf  lea     rcx, [rdi+24h]; unsigned __int16 *
0x180015eb3  mov     [rax+4], r14d
0x180015eb7  mov     r8, r12; unsigned __int16 *
0x180015eba  mov     eax, [rbp+arg_28]
0x180015ebd  mov     [rdi+10h], eax
0x180015ec0  mov     eax, [rbp+arg_38]
0x180015ec3  mov     [rdi+18h], eax
0x180015ec6  mov     eax, [rbp+arg_30]
0x180015ec9  mov     [rdi+1Ch], eax
0x180015ecc  mov     eax, [rbp+arg_20]
0x180015ecf  mov     [rdi+14h], eax
0x180015ed2  lea     eax, [rbx+1]
0x180015ed5  mov     edx, eax; unsigned __int64
0x180015ed7  mov     [rdi+8], r15
0x180015edb  mov     [rdi+20h], eax
0x180015ede  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015ee3  mov     ebx, eax
0x180015ee5  test    eax, eax
0x180015ee7  jns     short loc_180015F0F
0x180015ee9  mov     eax, cs:dword_180044008
0x180015eef  cmp     eax, 2
0x180015ef2  jbe     loc_180015FB4
0x180015ef8  lea     rax, aStringcchcopyw; "StringCchCopyW failed to copy section n"...
0x180015eff  mov     dword ptr [rbp+arg_0], 3ACh
0x180015f06  lea     rdx, word_18003C8C6
0x180015f0d  jmp     short loc_180015F51
0x180015f0f  mov     rax, [rsi]
0x180015f12  xor     r9d, r9d
0x180015f15  mov     edx, [rdi+4]
0x180015f18  mov     r8, rdi
0x180015f1b  mov     rcx, rsi
0x180015f1e  mov     rax, [rax+18h]
0x180015f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f27  mov     ebx, eax
0x180015f29  test    eax, eax
0x180015f2b  jns     loc_180015FB4
0x180015f31  mov     eax, cs:dword_180044008
0x180015f37  cmp     eax, 2
0x180015f3a  jbe     short loc_180015FB4
0x180015f3c  lea     rax, aFailedToSendXr_0; "Failed to send XREMOTEAPPGFXREDIRECTION"...
0x180015f43  mov     dword ptr [rbp+arg_0], 3B2h
0x180015f4a  lea     rdx, dword_18003C864
0x180015f51  mov     [rbp+var_8], rax
0x180015f55  lea     rax, aOnwndsurfacecr; "OnWndSurfaceCreated"
0x180015f5c  mov     [rbp+var_10], rax
0x180015f60  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015f67  mov     [rbp+var_18], rax
0x180015f6b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015f72  mov     [rbp+var_20], rax
0x180015f76  lea     rax, [rbp+var_8]
0x180015f7a  mov     [rsp+80h+var_38], rax
0x180015f7f  lea     rax, [rbp+var_10]
0x180015f83  mov     [rsp+80h+var_40], rax
0x180015f88  lea     rax, [rbp+arg_0]
0x180015f8c  mov     [rsp+80h+var_48], rax
0x180015f91  lea     rax, [rbp+var_18]
0x180015f95  mov     [rsp+80h+var_50], rax
0x180015f9a  lea     rax, [rbp+var_30]
0x180015f9e  mov     [rsp+80h+var_58], rax
0x180015fa3  lea     rax, [rbp+var_20]
0x180015fa7  mov     [rsp+80h+var_60], rax
0x180015fac  mov     dword ptr [rbp+var_30], ebx
0x180015faf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180015fb4  mov     rcx, rdi; Block
0x180015fb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015fbc  lea     rcx, [rbp+var_28]
0x180015fc0  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180015fc5  lea     r11, [rsp+80h+var_s0]
0x180015fcd  mov     eax, ebx
0x180015fcf  mov     rbx, [r11+38h]
0x180015fd3  mov     rsi, [r11+40h]
0x180015fd7  mov     rsp, r11
0x180015fda  pop     r15
0x180015fdc  pop     r14
0x180015fde  pop     r12
0x180015fe0  pop     rdi
0x180015fe1  pop     rbp
0x180015fe2  retn
```
