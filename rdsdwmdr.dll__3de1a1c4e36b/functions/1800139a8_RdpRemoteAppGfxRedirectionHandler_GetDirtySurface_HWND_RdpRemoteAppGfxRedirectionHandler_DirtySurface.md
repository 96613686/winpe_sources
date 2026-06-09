# RdpRemoteAppGfxRedirectionHandler::GetDirtySurface(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)

- ea: `0x1800139a8`
- end: `0x180013c1c`
- name: `?GetDirtySurface@RdpRemoteAppGfxRedirectionHandler@@AEAAJPEAUHWND__@@PEAPEAVDirtySurface@1@@Z`
- size: `628`
- prototype: `__int64 __fastcall(__int64 this, HWND, struct RdpRemoteAppGfxRedirectionHandler::DirtySurface **, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016190`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x180005f9c`
- `0x180012b7c`
- `0x180013350`
- `0x1800139a8`
- `0x18002c010`

## string_xrefs

- `0x180013b57`: `Failed to create dirty surface context`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::GetDirtySurface(
        __int64 this,
        HWND a2,
        struct RdpRemoteAppGfxRedirectionHandler::DirtySurface **a3,
        __int64 a4)
{
  int v6; // ebx
  __int16 *v7; // rdx
  const unsigned __int16 **v8; // rax
  char *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct RdpRemoteAppGfxRedirectionHandler::DirtySurface *v13; // rsi
  const char **v15; // [rsp+30h] [rbp-50h]
  const char **v16; // [rsp+40h] [rbp-40h]
  const unsigned __int16 **v17; // [rsp+48h] [rbp-38h]
  struct RdpRemoteAppGfxRedirectionHandler::DirtySurface *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-10h] BYREF
  HWND v23; // [rsp+B0h] [rbp+30h] BYREF
  const char *v24; // [rsp+B8h] [rbp+38h] BYREF

  v18 = 0;
  if ( a3 )
  {
    if ( !a2 )
    {
      v6 = -2147418113;
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_18;
      LODWORD(v23) = 1469;
      v21 = "GetDirtySurface called with NULL hwnd.";
      v7 = &word_18003BB96;
      v20 = "GetDirtySurface";
      v19 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v22[0] = "Error condition failed";
      v17 = (const unsigned __int16 **)&v21;
      v16 = &v20;
      v15 = &v19;
      v8 = (const unsigned __int16 **)v22;
LABEL_7:
      LODWORD(v24) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v7,
        (__int64)a3,
        a4,
        v8,
        (__int64)&v24,
        (const unsigned __int16 **)v15,
        (__int64)&v23,
        (const unsigned __int16 **)v16,
        v17);
      goto LABEL_18;
    }
    v9 = (char *)(this + 112);
    if ( (unsigned int)CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&public: static int RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(
                         this + 112,
                         (__int64)a2,
                         &v18) )
    {
      v6 = 0;
      *a3 = v18;
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 5 )
      {
        v23 = a2;
        v24 = "Dirty surface context not found - creating a new one";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v10,
          (__int64)byte_18003BB53,
          v11,
          v12,
          (const unsigned __int16 **)&v24,
          (__int64)&v23);
      }
      v6 = RdpRemoteAppGfxRedirectionHandler::DirtySurface::CreateInstance(a2, &v18);
      if ( v6 < 0 )
      {
        this = (unsigned int)dword_180044008;
        if ( (unsigned int)dword_180044008 <= 2 )
          goto LABEL_18;
        LODWORD(v23) = 1482;
        v22[0] = "Failed to create dirty surface context";
        v7 = (__int16 *)byte_18003BAF1;
        v21 = "GetDirtySurface";
        v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v19 = "Error HResult failed";
        v17 = (const unsigned __int16 **)v22;
        v16 = &v21;
        v15 = &v20;
        v8 = (const unsigned __int16 **)&v19;
        goto LABEL_7;
      }
      v13 = v18;
      v6 = (*(__int64 (__fastcall **)(char *, struct RdpRemoteAppGfxRedirectionHandler::DirtySurface *))(*(_QWORD *)v9 + 8LL))(
             v9,
             v18);
      if ( v6 < 0 )
        goto LABEL_18;
      *a3 = v13;
    }
    v18 = 0;
    goto LABEL_18;
  }
  v6 = -2147467261;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v23) = 1468;
    v19 = "GetDirtySurface";
    LODWORD(v24) = -2147467261;
    v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v21 = "Unexpected NULL object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      this,
      (__int64)&unk_18003BBF8,
      0,
      a4,
      (const unsigned __int16 **)&v21,
      (__int64)&v24,
      (const unsigned __int16 **)&v20,
      (__int64)&v23,
      (const unsigned __int16 **)&v19);
  }
LABEL_18:
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800139a8  mov     r11, rsp
0x1800139ab  mov     [r11+8], rbx
0x1800139af  mov     [r11+10h], rsi
0x1800139b3  push    rbp
0x1800139b4  push    rdi
0x1800139b5  push    r14
0x1800139b7  mov     rbp, rsp
0x1800139ba  sub     rsp, 80h
0x1800139c1  mov     [rbp+var_30], 0
0x1800139c9  mov     rdi, r8
0x1800139cc  mov     rbx, rdx
0x1800139cf  test    r8, r8
0x1800139d2  jnz     short loc_180013A4C
0x1800139d4  mov     eax, cs:dword_180044008
0x1800139da  mov     ebx, 80004003h
0x1800139df  cmp     eax, 2
0x1800139e2  jbe     loc_180013BF9
0x1800139e8  lea     rax, aGetdirtysurfac_0; "GetDirtySurface"
0x1800139ef  mov     dword ptr [rbp+arg_10], 5BCh
0x1800139f6  mov     [rbp+var_28], rax
0x1800139fa  lea     rdx, unk_18003BBF8
0x180013a01  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180013a08  mov     dword ptr [rbp+arg_18], ebx
0x180013a0b  mov     [rbp+var_20], rax
0x180013a0f  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180013a16  mov     [rbp+var_18], rax
0x180013a1a  lea     rax, [rbp+var_28]
0x180013a1e  mov     [r11-58h], rax
0x180013a22  lea     rax, [rbp+arg_10]
0x180013a26  mov     [r11-60h], rax
0x180013a2a  lea     rax, [rbp+var_20]
0x180013a2e  mov     [r11-68h], rax
0x180013a32  lea     rax, [rbp+arg_18]
0x180013a36  mov     [r11-70h], rax
0x180013a3a  lea     rax, [rbp+var_18]
0x180013a3e  mov     [r11-78h], rax
0x180013a42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180013a47  jmp     loc_180013BF9
0x180013a4c  test    rbx, rbx
0x180013a4f  jnz     loc_180013AE6
0x180013a55  mov     eax, cs:dword_180044008
0x180013a5b  mov     ebx, 8000FFFFh
0x180013a60  cmp     eax, 2
0x180013a63  jbe     loc_180013BF9
0x180013a69  lea     rax, aGetdirtysurfac; "GetDirtySurface called with NULL hwnd."
0x180013a70  mov     dword ptr [rbp+arg_10], 5BDh
0x180013a77  mov     [rbp+var_18], rax
0x180013a7b  lea     rdx, word_18003BB96
0x180013a82  lea     rax, aGetdirtysurfac_0; "GetDirtySurface"
0x180013a89  mov     [rbp+var_20], rax
0x180013a8d  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180013a94  mov     [rbp+var_28], rax
0x180013a98  lea     rax, aErrorCondition; "Error condition failed"
0x180013a9f  mov     [rbp+var_10], rax
0x180013aa3  lea     rax, [rbp+var_18]
0x180013aa7  mov     [rsp+80h+var_38], rax
0x180013aac  lea     rax, [rbp+var_20]
0x180013ab0  mov     [rsp+80h+var_40], rax
0x180013ab5  lea     rax, [rbp+arg_10]
0x180013ab9  mov     [rsp+80h+var_48], rax
0x180013abe  lea     rax, [rbp+var_28]
0x180013ac2  mov     [rsp+80h+var_50], rax
0x180013ac7  lea     rax, [rbp+arg_18]
0x180013acb  mov     [rsp+80h+var_58], rax
0x180013ad0  lea     rax, [rbp+var_10]
0x180013ad4  mov     [rsp+80h+var_60], rax
0x180013ad9  mov     dword ptr [rbp+arg_18], ebx
0x180013adc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180013ae1  jmp     loc_180013BF9
0x180013ae6  lea     r14, [rcx+70h]
0x180013aea  mov     rcx, r14
0x180013aed  lea     r8, [rbp+var_30]
0x180013af1  call    ??$Find@PEAUHWND__@@$1?MatchSurfaceByHWND@DirtySurface@RdpRemoteAppGfxRedirectionHandler@@SAHPEAU1@PEAV34@@Z@?$CTSSimpleComPtrArray@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@QEAAHPEAUHWND__@@PEAPEAVDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@Z; CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)
0x180013af6  test    eax, eax
0x180013af8  jnz     loc_180013BE8
0x180013afe  mov     eax, cs:dword_180044008
0x180013b04  cmp     eax, 5
0x180013b07  jbe     short loc_180013B36
0x180013b09  lea     rax, aDirtySurfaceCo; "Dirty surface context not found - creat"...
0x180013b10  mov     [rbp+arg_10], rbx
0x180013b14  mov     [rbp+arg_18], rax
0x180013b18  lea     rdx, byte_18003BB53
0x180013b1f  lea     rax, [rbp+arg_10]
0x180013b23  mov     [rsp+80h+var_58], rax
0x180013b28  lea     rax, [rbp+arg_18]
0x180013b2c  mov     [rsp+80h+var_60], rax
0x180013b31  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180013b36  lea     rdx, [rbp+var_30]; struct RdpRemoteAppGfxRedirectionHandler::DirtySurface **
0x180013b3a  mov     rcx, rbx; HWND
0x180013b3d  call    ?CreateInstance@DirtySurface@RdpRemoteAppGfxRedirectionHandler@@SAJPEAUHWND__@@PEAPEAV12@@Z; RdpRemoteAppGfxRedirectionHandler::DirtySurface::CreateInstance(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)
0x180013b42  mov     ebx, eax
0x180013b44  test    eax, eax
0x180013b46  jns     short loc_180013BC7
0x180013b48  mov     ecx, cs:dword_180044008
0x180013b4e  cmp     ecx, 2
0x180013b51  jbe     loc_180013BF9
0x180013b57  lea     rax, aFailedToCreate_14; "Failed to create dirty surface context"
0x180013b5e  mov     dword ptr [rbp+arg_10], 5CAh
0x180013b65  mov     [rbp+var_10], rax
0x180013b69  lea     rdx, byte_18003BAF1
0x180013b70  lea     rax, aGetdirtysurfac_0; "GetDirtySurface"
0x180013b77  mov     [rbp+var_18], rax
0x180013b7b  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180013b82  mov     [rbp+var_20], rax
0x180013b86  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180013b8d  mov     [rbp+var_28], rax
0x180013b91  lea     rax, [rbp+var_10]
0x180013b95  mov     [rsp+80h+var_38], rax
0x180013b9a  lea     rax, [rbp+var_18]
0x180013b9e  mov     [rsp+80h+var_40], rax
0x180013ba3  lea     rax, [rbp+arg_10]
0x180013ba7  mov     [rsp+80h+var_48], rax
0x180013bac  lea     rax, [rbp+var_20]
0x180013bb0  mov     [rsp+80h+var_50], rax
0x180013bb5  lea     rax, [rbp+arg_18]
0x180013bb9  mov     [rsp+80h+var_58], rax
0x180013bbe  lea     rax, [rbp+var_28]
0x180013bc2  jmp     loc_180013AD4
0x180013bc7  mov     rax, [r14]
0x180013bca  mov     rcx, r14
0x180013bcd  mov     rsi, [rbp+var_30]
0x180013bd1  mov     rdx, rsi
0x180013bd4  mov     rax, [rax+8]
0x180013bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bdd  mov     ebx, eax
0x180013bdf  test    eax, eax
0x180013be1  js      short loc_180013BF9
0x180013be3  mov     [rdi], rsi
0x180013be6  jmp     short loc_180013BF1
0x180013be8  mov     rax, [rbp+var_30]
0x180013bec  xor     ebx, ebx
0x180013bee  mov     [rdi], rax
0x180013bf1  mov     [rbp+var_30], 0
0x180013bf9  lea     rcx, [rbp+var_30]
0x180013bfd  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x180013c02  lea     r11, [rsp+80h+var_s0]
0x180013c0a  mov     eax, ebx
0x180013c0c  mov     rbx, [r11+20h]
0x180013c10  mov     rsi, [r11+28h]
0x180013c14  mov     rsp, r11
0x180013c17  pop     r14
0x180013c19  pop     rdi
0x180013c1a  pop     rbp
0x180013c1b  retn
```
