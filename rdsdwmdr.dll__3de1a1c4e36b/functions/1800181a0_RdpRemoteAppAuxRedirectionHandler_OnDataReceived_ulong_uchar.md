# RdpRemoteAppAuxRedirectionHandler::OnDataReceived(ulong,uchar *)

- ea: `0x1800181a0`
- end: `0x180018514`
- name: `?OnDataReceived@RdpRemoteAppAuxRedirectionHandler@@UEAAJKPEAE@Z`
- size: `884`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *this, unsigned int, unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180017598`
- `0x180017b80`
- `0x1800181a0`
- `0x180019710`

## string_xrefs

- `0x180018469`: `Unexpected Caps PDU type. Caps already received`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::OnDataReceived(
        RdpRemoteAppAuxRedirectionHandler *this,
        unsigned int a2,
        unsigned __int8 *a3,
        __int64 a4)
{
  struct _GUID *v4; // rsi
  unsigned int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  RdpRemoteAppAuxRedirectionHandler *v9; // rcx
  const char **v11; // [rsp+30h] [rbp-40h]
  const char **v12; // [rsp+40h] [rbp-30h]
  const char **v13; // [rsp+48h] [rbp-28h]
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  const char *v15; // [rsp+58h] [rbp-18h] BYREF
  const char *v16; // [rsp+60h] [rbp-10h] BYREF
  const char *v17; // [rsp+68h] [rbp-8h] BYREF
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  const char *v19; // [rsp+A8h] [rbp+38h] BYREF

  v4 = (struct _GUID *)&stru_180032B98;
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = 324;
      v14 = "OnDataReceived";
      LODWORD(v19) = -2147467261;
      v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v16 = "Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)this,
        (__int64)&dword_18003E32C,
        0,
        a4,
        (const unsigned __int16 **)&v16,
        (__int64)&v19,
        (const unsigned __int16 **)&v15,
        (__int64)&v18,
        (const unsigned __int16 **)&v14);
    }
    goto LABEL_22;
  }
  if ( a2 < 8 )
  {
    v6 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = 325;
      v16 = "Malformed PDU received from server";
      v7 = word_18003E2CA;
      v15 = "OnDataReceived";
      v14 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v17 = "Error condition failed";
      v13 = &v16;
      v12 = &v15;
      v11 = &v14;
      v8 = &v17;
LABEL_7:
      LODWORD(v19) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        2147500037LL,
        (__int64)v7,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)v8,
        (__int64)&v19,
        (const unsigned __int16 **)v11,
        (__int64)&v18,
        (const unsigned __int16 **)v12,
        (const unsigned __int16 **)v13);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  if ( a2 < *((_DWORD *)a3 + 1) )
  {
    v6 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v18 = 328;
      v17 = "PDU length is greater than buffer size";
      v7 = (__int16 *)&unk_18003E268;
      v16 = "OnDataReceived";
      v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v14 = "Error condition failed";
      v13 = &v17;
      v12 = &v16;
      v11 = &v15;
      v8 = &v14;
      goto LABEL_7;
    }
LABEL_22:
    RDSDWMDirectTraceLogging::LogAuxError(
      (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 56),
      v4,
      (unsigned __int16 *)v6,
      a4);
    RdpRemoteAppAuxRedirectionHandler::CleanupSessionObjects((RdpRemoteAppAuxRedirectionHandler *)((char *)this - 48));
    return v6;
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    v4 = (struct _GUID *)L"CapsReceived";
    if ( *((_DWORD *)a3 + 1) < 0xAu )
    {
      v6 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 343;
        v17 = "Unexpected PDU length";
        v7 = &word_18003E206;
        v16 = "OnDataReceived";
        v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v14 = "Error condition failed";
        v13 = &v17;
        v12 = &v16;
        v11 = &v15;
        v8 = &v14;
        goto LABEL_7;
      }
      goto LABEL_22;
    }
    v9 = (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 48);
    if ( *((_DWORD *)v9 + 24) )
    {
      v6 = -2147024883;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v18 = 345;
        v17 = "Unexpected Caps PDU type. Caps already received";
        LODWORD(v19) = -2147024883;
        v16 = "OnDataReceived";
        v15 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
        v14 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (__int64)v9,
          (__int64)&dword_18003E1A4,
          (__int64)a3,
          a4,
          (const unsigned __int16 **)&v14,
          (__int64)&v19,
          (const unsigned __int16 **)&v15,
          (__int64)&v18,
          (const unsigned __int16 **)&v16,
          (const unsigned __int16 **)&v17);
      }
      goto LABEL_22;
    }
    v6 = RdpRemoteAppAuxRedirectionHandler::HandleCapsPdu(v9, (struct _RDPXREMOTEAPPAUXREDIRECTION_CAPS_PDU *const)a3);
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_22;
  }
  else
  {
    v6 = 0;
    if ( (unsigned int)dword_180044008 > 3 )
    {
      v18 = *(_DWORD *)a3;
      v19 = "Unknown PDU type";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)this,
        (__int64)byte_18003E15D,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v19,
        (__int64)&v18);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800181a0  mov     r11, rsp
0x1800181a3  mov     [r11+8], rbx
0x1800181a7  push    rbp
0x1800181a8  push    rsi
0x1800181a9  push    rdi
0x1800181aa  mov     rbp, rsp
0x1800181ad  sub     rsp, 70h
0x1800181b1  lea     rsi, stru_180032B98
0x1800181b8  mov     rdi, rcx
0x1800181bb  test    r8, r8
0x1800181be  jnz     short loc_180018238
0x1800181c0  mov     eax, cs:dword_180044008
0x1800181c6  mov     ebx, 80004003h
0x1800181cb  cmp     eax, 2
0x1800181ce  jbe     loc_1800184EA
0x1800181d4  lea     rax, aOndatareceived_0; "OnDataReceived"
0x1800181db  mov     [rbp+arg_10], 144h
0x1800181e2  mov     [rbp+var_20], rax
0x1800181e6  lea     rdx, dword_18003E32C
0x1800181ed  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800181f4  mov     dword ptr [rbp+arg_18], ebx
0x1800181f7  mov     [rbp+var_18], rax
0x1800181fb  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180018202  mov     [rbp+var_10], rax
0x180018206  lea     rax, [rbp+var_20]
0x18001820a  mov     [r11-48h], rax
0x18001820e  lea     rax, [rbp+arg_10]
0x180018212  mov     [r11-50h], rax
0x180018216  lea     rax, [rbp+var_18]
0x18001821a  mov     [r11-58h], rax
0x18001821e  lea     rax, [rbp+arg_18]
0x180018222  mov     [r11-60h], rax
0x180018226  lea     rax, [rbp+var_10]
0x18001822a  mov     [r11-68h], rax
0x18001822e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018233  jmp     loc_1800184EA
0x180018238  cmp     edx, 8
0x18001823b  jnb     loc_1800182D4
0x180018241  mov     eax, cs:dword_180044008
0x180018247  mov     ecx, 80004005h
0x18001824c  mov     ebx, ecx
0x18001824e  cmp     eax, 2
0x180018251  jbe     loc_1800184EA
0x180018257  lea     rax, aMalformedPduRe; "Malformed PDU received from server"
0x18001825e  mov     [rbp+arg_10], 145h
0x180018265  mov     [rbp+var_10], rax
0x180018269  lea     rdx, word_18003E2CA
0x180018270  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180018277  mov     [rbp+var_18], rax
0x18001827b  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018282  mov     [rbp+var_20], rax
0x180018286  lea     rax, aErrorCondition; "Error condition failed"
0x18001828d  mov     [rbp+var_8], rax
0x180018291  lea     rax, [rbp+var_10]
0x180018295  mov     [rsp+70h+var_28], rax
0x18001829a  lea     rax, [rbp+var_18]
0x18001829e  mov     [rsp+70h+var_30], rax
0x1800182a3  lea     rax, [rbp+arg_10]
0x1800182a7  mov     [rsp+70h+var_38], rax
0x1800182ac  lea     rax, [rbp+var_20]
0x1800182b0  mov     [rsp+70h+var_40], rax
0x1800182b5  lea     rax, [rbp+arg_18]
0x1800182b9  mov     [rsp+70h+var_48], rax
0x1800182be  lea     rax, [rbp+var_8]
0x1800182c2  mov     dword ptr [rbp+arg_18], ecx
0x1800182c5  mov     [rsp+70h+var_50], rax
0x1800182ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800182cf  jmp     loc_1800184EA
0x1800182d4  cmp     edx, [r8+4]
0x1800182d8  jnb     loc_180018364
0x1800182de  mov     eax, cs:dword_180044008
0x1800182e4  mov     ecx, 80004005h
0x1800182e9  mov     ebx, ecx
0x1800182eb  cmp     eax, 2
0x1800182ee  jbe     loc_1800184EA
0x1800182f4  lea     rax, aPduLengthIsGre; "PDU length is greater than buffer size"
0x1800182fb  mov     [rbp+arg_10], 148h
0x180018302  mov     [rbp+var_8], rax
0x180018306  lea     rdx, unk_18003E268
0x18001830d  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180018314  mov     [rbp+var_10], rax
0x180018318  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001831f  mov     [rbp+var_18], rax
0x180018323  lea     rax, aErrorCondition; "Error condition failed"
0x18001832a  mov     [rbp+var_20], rax
0x18001832e  lea     rax, [rbp+var_8]
0x180018332  mov     [rsp+70h+var_28], rax
0x180018337  lea     rax, [rbp+var_10]
0x18001833b  mov     [rsp+70h+var_30], rax
0x180018340  lea     rax, [rbp+arg_10]
0x180018344  mov     [rsp+70h+var_38], rax
0x180018349  lea     rax, [rbp+var_18]
0x18001834d  mov     [rsp+70h+var_40], rax
0x180018352  lea     rax, [rbp+arg_18]
0x180018356  mov     [rsp+70h+var_48], rax
0x18001835b  lea     rax, [rbp+var_20]
0x18001835f  jmp     loc_1800182C2
0x180018364  cmp     dword ptr [r8], 1
0x180018368  jz      short loc_1800183AF
0x18001836a  mov     eax, cs:dword_180044008
0x180018370  xor     ebx, ebx
0x180018372  cmp     eax, 3
0x180018375  jbe     loc_180018502
0x18001837b  mov     eax, [r8]
0x18001837e  lea     rdx, byte_18003E15D
0x180018385  mov     [rbp+arg_10], eax
0x180018388  lea     rax, aUnknownPduType; "Unknown PDU type"
0x18001838f  mov     [rbp+arg_18], rax
0x180018393  lea     rax, [rbp+arg_10]
0x180018397  mov     [rsp+70h+var_48], rax
0x18001839c  lea     rax, [rbp+arg_18]
0x1800183a0  mov     [rsp+70h+var_50], rax
0x1800183a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800183aa  jmp     loc_180018502
0x1800183af  cmp     dword ptr [r8+4], 0Ah
0x1800183b4  lea     rsi, aCapsreceived; "CapsReceived"
0x1800183bb  jnb     loc_180018447
0x1800183c1  mov     eax, cs:dword_180044008
0x1800183c7  mov     ecx, 80004005h
0x1800183cc  mov     ebx, ecx
0x1800183ce  cmp     eax, 2
0x1800183d1  jbe     loc_1800184EA
0x1800183d7  lea     rax, aUnexpectedPduL; "Unexpected PDU length"
0x1800183de  mov     [rbp+arg_10], 157h
0x1800183e5  mov     [rbp+var_8], rax
0x1800183e9  lea     rdx, word_18003E206
0x1800183f0  lea     rax, aOndatareceived_0; "OnDataReceived"
0x1800183f7  mov     [rbp+var_10], rax
0x1800183fb  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018402  mov     [rbp+var_18], rax
0x180018406  lea     rax, aErrorCondition; "Error condition failed"
0x18001840d  mov     [rbp+var_20], rax
0x180018411  lea     rax, [rbp+var_8]
0x180018415  mov     [rsp+70h+var_28], rax
0x18001841a  lea     rax, [rbp+var_10]
0x18001841e  mov     [rsp+70h+var_30], rax
0x180018423  lea     rax, [rbp+arg_10]
0x180018427  mov     [rsp+70h+var_38], rax
0x18001842c  lea     rax, [rbp+var_18]
0x180018430  mov     [rsp+70h+var_40], rax
0x180018435  lea     rax, [rbp+arg_18]
0x180018439  mov     [rsp+70h+var_48], rax
0x18001843e  lea     rax, [rbp+var_20]
0x180018442  jmp     loc_1800182C2
0x180018447  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x18001844b  cmp     dword ptr [rcx+60h], 0
0x18001844f  jz      loc_1800184DC
0x180018455  mov     eax, cs:dword_180044008
0x18001845b  mov     ebx, 8007000Dh
0x180018460  cmp     eax, 2
0x180018463  jbe     loc_1800184EA
0x180018469  lea     rax, aUnexpectedCaps; "Unexpected Caps PDU type. Caps already "...
0x180018470  mov     [rbp+arg_10], 159h
0x180018477  mov     [rbp+var_8], rax
0x18001847b  lea     rdx, dword_18003E1A4
0x180018482  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180018489  mov     dword ptr [rbp+arg_18], ebx
0x18001848c  mov     [rbp+var_10], rax
0x180018490  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018497  mov     [rbp+var_18], rax
0x18001849b  lea     rax, aErrorCondition; "Error condition failed"
0x1800184a2  mov     [rbp+var_20], rax
0x1800184a6  lea     rax, [rbp+var_8]
0x1800184aa  mov     [rsp+70h+var_28], rax
0x1800184af  lea     rax, [rbp+var_10]
0x1800184b3  mov     [rsp+70h+var_30], rax
0x1800184b8  lea     rax, [rbp+arg_10]
0x1800184bc  mov     [rsp+70h+var_38], rax
0x1800184c1  lea     rax, [rbp+var_18]
0x1800184c5  mov     [rsp+70h+var_40], rax
0x1800184ca  lea     rax, [rbp+arg_18]
0x1800184ce  mov     [rsp+70h+var_48], rax
0x1800184d3  lea     rax, [rbp+var_20]
0x1800184d7  jmp     loc_1800182C5
0x1800184dc  mov     rdx, r8; struct _RDPXREMOTEAPPAUXREDIRECTION_CAPS_PDU *
0x1800184df  call    ?HandleCapsPdu@RdpRemoteAppAuxRedirectionHandler@@IEAAJQEAU_RDPXREMOTEAPPAUXREDIRECTION_CAPS_PDU@@@Z; RdpRemoteAppAuxRedirectionHandler::HandleCapsPdu(_RDPXREMOTEAPPAUXREDIRECTION_CAPS_PDU * const)
0x1800184e4  mov     ebx, eax
0x1800184e6  test    eax, eax
0x1800184e8  jns     short loc_180018502
0x1800184ea  lea     rcx, [rdi+38h]; this
0x1800184ee  mov     r8d, ebx; unsigned __int16 *
0x1800184f1  mov     rdx, rsi; struct _GUID *
0x1800184f4  call    ?LogAuxError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogAuxError(_GUID *,ushort *,long)
0x1800184f9  lea     rcx, [rdi-30h]; this
0x1800184fd  call    ?CleanupSessionObjects@RdpRemoteAppAuxRedirectionHandler@@IEAAXXZ; RdpRemoteAppAuxRedirectionHandler::CleanupSessionObjects(void)
0x180018502  mov     eax, ebx
0x180018504  mov     rbx, [rsp+70h+arg_0]
0x18001850c  add     rsp, 70h
0x180018510  pop     rdi
0x180018511  pop     rsi
0x180018512  pop     rbp
0x180018513  retn
```
