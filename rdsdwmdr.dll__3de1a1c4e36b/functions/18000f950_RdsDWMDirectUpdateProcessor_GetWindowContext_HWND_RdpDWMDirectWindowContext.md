# RdsDWMDirectUpdateProcessor::GetWindowContext(HWND__ *,RdpDWMDirectWindowContext * *)

- ea: `0x18000f950`
- end: `0x18000fb71`
- name: `?GetWindowContext@RdsDWMDirectUpdateProcessor@@IEAAJPEAUHWND__@@PEAPEAVRdpDWMDirectWindowContext@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(__int64 this, HWND, struct RdpDWMDirectWindowContext **, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180010a30`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180001bfc`
- `0x180005f9c`
- `0x18000d6ac`
- `0x18000f950`
- `0x18002c010`

## string_xrefs

- `0x18000f9ab`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000fa3b`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::GetWindowContext(
        __int64 this,
        HWND a2,
        struct RdpDWMDirectWindowContext **a3,
        __int64 a4)
{
  __int64 v6; // r15
  int v7; // ebx
  __int64 v8; // rdx
  struct RdpDWMDirectWindowContext *v9; // rsi
  struct RdpDWMDirectWindowContext *v11; // [rsp+50h] [rbp-30h] BYREF
  const char *v12; // [rsp+58h] [rbp-28h] BYREF
  const char *v13; // [rsp+60h] [rbp-20h] BYREF
  const char *v14; // [rsp+68h] [rbp-18h] BYREF
  const char *v15; // [rsp+70h] [rbp-10h] BYREF
  HWND v16; // [rsp+C0h] [rbp+40h] BYREF
  const char *v17; // [rsp+C8h] [rbp+48h] BYREF

  v11 = 0;
  v6 = this;
  if ( !a3 )
  {
    v7 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v16) = 490;
      v12 = "GetWindowContext";
      LODWORD(v17) = -2147467261;
      v13 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v14 = "Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        this,
        (__int64)&byte_18003B527,
        0,
        a4,
        (const unsigned __int16 **)&v14,
        (__int64)&v17,
        (const unsigned __int16 **)&v13,
        (__int64)&v16,
        (const unsigned __int16 **)&v12);
    }
    goto LABEL_17;
  }
  if ( !a2 )
  {
    v7 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v16) = 491;
      v14 = "GetWindowContext called with NULL hwnd.";
      LODWORD(v17) = -2147418113;
      v13 = "GetWindowContext";
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v15 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)word_18003B4DA,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v15,
        (__int64)&v17,
        (const unsigned __int16 **)&v12,
        (__int64)&v16,
        (const unsigned __int16 **)&v13,
        (const unsigned __int16 **)&v14);
    }
    goto LABEL_17;
  }
  if ( *(_DWORD *)(this + 28) )
  {
    v8 = *(_QWORD *)(this + 16);
    this = 0;
    while ( 1 )
    {
      v9 = *(struct RdpDWMDirectWindowContext **)(v8 + 8 * this);
      if ( a2 == *((HWND *)v9 + 8) )
        break;
      this = (unsigned int)(this + 1);
      if ( (unsigned int)this >= *(_DWORD *)(v6 + 28) )
        goto LABEL_11;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 4) + 8LL))(*((_QWORD *)v9 + 4));
    v7 = 0;
    goto LABEL_16;
  }
LABEL_11:
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v16 = a2;
    v17 = "Rendering context not found - creating a new one";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      this,
      (__int64)&byte_18003B4AF,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)&v17,
      (__int64)&v16);
  }
  v7 = RdpDWMDirectWindowContext::CreateInstance(
         *(struct IRdsDWMDirectDriverIO **)(v6 + 40),
         (struct IRdsDWMAuxRedirection *)((*(_QWORD *)(v6 + 56) + 56LL)
                                        & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(v6 + 56) >> 64)),
         a2,
         &v11);
  if ( v7 >= 0 )
  {
    v9 = v11;
    v7 = (*(__int64 (__fastcall **)(__int64, struct RdpDWMDirectWindowContext *))(*(_QWORD *)(v6 + 8) + 8LL))(
           v6 + 8,
           v11);
    if ( v7 >= 0 )
    {
      v11 = 0;
LABEL_16:
      *a3 = v9;
    }
  }
LABEL_17:
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f950  mov     r11, rsp
0x18000f953  mov     [r11+8], rbx
0x18000f957  push    rbp
0x18000f958  push    rsi
0x18000f959  push    rdi
0x18000f95a  push    r14
0x18000f95c  push    r15
0x18000f95e  mov     rbp, rsp
0x18000f961  sub     rsp, 80h
0x18000f968  mov     [rbp+var_30], 0
0x18000f970  mov     r14, r8
0x18000f973  mov     rbx, rdx
0x18000f976  mov     r15, rcx
0x18000f979  test    r8, r8
0x18000f97c  jnz     short loc_18000F9F7
0x18000f97e  mov     eax, cs:dword_180044008
0x18000f984  mov     ebx, 80004003h
0x18000f989  cmp     eax, 2
0x18000f98c  jbe     loc_18000FB3B
0x18000f992  lea     rax, aGetwindowconte_0; "GetWindowContext"
0x18000f999  mov     dword ptr [rbp+arg_10], 1EAh
0x18000f9a0  mov     [rbp+var_28], rax
0x18000f9a4  lea     rdx, byte_18003B527
0x18000f9ab  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000f9b2  mov     dword ptr [rbp+arg_18], ebx
0x18000f9b5  mov     [rbp+var_20], rax
0x18000f9b9  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x18000f9c0  mov     [rbp+var_18], rax
0x18000f9c4  lea     rax, [rbp+var_28]
0x18000f9c8  mov     [r11-68h], rax
0x18000f9cc  lea     rax, [rbp+arg_10]
0x18000f9d0  mov     [r11-70h], rax
0x18000f9d4  lea     rax, [rbp+var_20]
0x18000f9d8  mov     [r11-78h], rax
0x18000f9dc  lea     rax, [rbp+arg_18]
0x18000f9e0  mov     [r11-80h], rax
0x18000f9e4  lea     rax, [rbp+var_18]
0x18000f9e8  mov     [rsp+80h+var_60], rax
0x18000f9ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f9f2  jmp     loc_18000FB3B
0x18000f9f7  test    rbx, rbx
0x18000f9fa  jnz     loc_18000FA91
0x18000fa00  mov     eax, cs:dword_180044008
0x18000fa06  mov     ebx, 8000FFFFh
0x18000fa0b  cmp     eax, 2
0x18000fa0e  jbe     loc_18000FB3B
0x18000fa14  lea     rax, aGetwindowconte; "GetWindowContext called with NULL hwnd."
0x18000fa1b  mov     dword ptr [rbp+arg_10], 1EBh
0x18000fa22  mov     [rbp+var_18], rax
0x18000fa26  lea     rdx, word_18003B4DA
0x18000fa2d  lea     rax, aGetwindowconte_0; "GetWindowContext"
0x18000fa34  mov     dword ptr [rbp+arg_18], ebx
0x18000fa37  mov     [rbp+var_20], rax
0x18000fa3b  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000fa42  mov     [rbp+var_28], rax
0x18000fa46  lea     rax, aErrorCondition; "Error condition failed"
0x18000fa4d  mov     [rbp+var_10], rax
0x18000fa51  lea     rax, [rbp+var_18]
0x18000fa55  mov     [rsp+80h+var_38], rax
0x18000fa5a  lea     rax, [rbp+var_20]
0x18000fa5e  mov     [rsp+80h+var_40], rax
0x18000fa63  lea     rax, [rbp+arg_10]
0x18000fa67  mov     [rsp+80h+var_48], rax
0x18000fa6c  lea     rax, [rbp+var_28]
0x18000fa70  mov     [rsp+80h+var_50], rax
0x18000fa75  lea     rax, [rbp+arg_18]
0x18000fa79  mov     [rsp+80h+var_58], rax
0x18000fa7e  lea     rax, [rbp+var_10]
0x18000fa82  mov     [rsp+80h+var_60], rax
0x18000fa87  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000fa8c  jmp     loc_18000FB3B
0x18000fa91  cmp     dword ptr [rcx+1Ch], 0
0x18000fa95  jbe     short loc_18000FAB3
0x18000fa97  mov     rdx, [r15+10h]
0x18000fa9b  xor     ecx, ecx
0x18000fa9d  mov     rsi, [rdx+rcx*8]
0x18000faa1  cmp     rbx, [rsi+40h]
0x18000faa5  jz      loc_18000FB5D
0x18000faab  inc     ecx
0x18000faad  cmp     ecx, [r15+1Ch]
0x18000fab1  jb      short loc_18000FA9D
0x18000fab3  mov     eax, cs:dword_180044008
0x18000fab9  cmp     eax, 5
0x18000fabc  jbe     short loc_18000FAEB
0x18000fabe  lea     rax, aRenderingConte; "Rendering context not found - creating "...
0x18000fac5  mov     [rbp+arg_10], rbx
0x18000fac9  mov     [rbp+arg_18], rax
0x18000facd  lea     rdx, byte_18003B4AF
0x18000fad4  lea     rax, [rbp+arg_10]
0x18000fad8  mov     [rsp+80h+var_58], rax
0x18000fadd  lea     rax, [rbp+arg_18]
0x18000fae1  mov     [rsp+80h+var_60], rax
0x18000fae6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000faeb  mov     rax, [r15+38h]
0x18000faef  lea     r9, [rbp+var_30]; struct RdpDWMDirectWindowContext **
0x18000faf3  mov     r8, rbx; HWND
0x18000faf6  lea     rcx, [rax+38h]
0x18000fafa  neg     rax
0x18000fafd  sbb     rdx, rdx
0x18000fb00  and     rdx, rcx; struct IRdsDWMAuxRedirection *
0x18000fb03  mov     rcx, [r15+28h]; struct IRdsDWMDirectDriverIO *
0x18000fb07  call    ?CreateInstance@RdpDWMDirectWindowContext@@SAJPEAUIRdsDWMDirectDriverIO@@PEAUIRdsDWMAuxRedirection@@PEAUHWND__@@PEAPEAV1@@Z; RdpDWMDirectWindowContext::CreateInstance(IRdsDWMDirectDriverIO *,IRdsDWMAuxRedirection *,HWND__ *,RdpDWMDirectWindowContext * *)
0x18000fb0c  mov     ebx, eax
0x18000fb0e  test    eax, eax
0x18000fb10  js      short loc_18000FB3B
0x18000fb12  mov     rax, [r15+8]
0x18000fb16  lea     rcx, [r15+8]
0x18000fb1a  mov     rsi, [rbp+var_30]
0x18000fb1e  mov     rdx, rsi
0x18000fb21  mov     rax, [rax+8]
0x18000fb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb2a  mov     ebx, eax
0x18000fb2c  test    eax, eax
0x18000fb2e  js      short loc_18000FB3B
0x18000fb30  mov     [rbp+var_30], 0
0x18000fb38  mov     [r14], rsi
0x18000fb3b  lea     rcx, [rbp+var_30]
0x18000fb3f  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x18000fb44  mov     eax, ebx
0x18000fb46  mov     rbx, [rsp+80h+arg_0]
0x18000fb4e  add     rsp, 80h
0x18000fb55  pop     r15
0x18000fb57  pop     r14
0x18000fb59  pop     rdi
0x18000fb5a  pop     rsi
0x18000fb5b  pop     rbp
0x18000fb5c  retn
0x18000fb5d  mov     rcx, [rsi+20h]
0x18000fb61  mov     rax, [rcx]
0x18000fb64  mov     rax, [rax+8]
0x18000fb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6d  xor     ebx, ebx
0x18000fb6f  jmp     short loc_18000FB38
```
