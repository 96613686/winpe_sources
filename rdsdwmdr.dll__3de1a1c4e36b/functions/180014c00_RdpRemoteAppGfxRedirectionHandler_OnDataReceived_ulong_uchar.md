# RdpRemoteAppGfxRedirectionHandler::OnDataReceived(ulong,uchar *)

- ea: `0x180014c00`
- end: `0x180015209`
- name: `?OnDataReceived@RdpRemoteAppGfxRedirectionHandler@@UEAAJKPEAE@Z`
- size: `1545`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *this, unsigned int, unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x1800130c0`
- `0x180013850`
- `0x180013c44`
- `0x180013da4`
- `0x180013e58`
- `0x180014c00`
- `0x180019ae4`

## string_xrefs

- `0x180014eeb`: `Unexpected Caps PDU type. Caps already received`
- `0x18001515d`: `Unexpected Caps PDU type. Caps already received`
- `0x180014f68`: `GraphicsUpdateAckReceived`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnDataReceived(
        RdpRemoteAppGfxRedirectionHandler *this,
        unsigned int a2,
        unsigned __int8 *a3,
        __int64 a4)
{
  wchar_t *v4; // r14
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int16 *v10; // rdx
  const char **v11; // rax
  unsigned int v12; // edx
  __int64 v13; // rcx
  int updated; // eax
  __int64 v15; // r8
  const char **v17; // [rsp+30h] [rbp-40h]
  const char **v18; // [rsp+40h] [rbp-30h]
  const char **v19; // [rsp+48h] [rbp-28h]
  const char *v20; // [rsp+50h] [rbp-20h] BYREF
  const char *v21; // [rsp+58h] [rbp-18h] BYREF
  const char *v22; // [rsp+60h] [rbp-10h] BYREF
  const char *v23; // [rsp+68h] [rbp-8h] BYREF
  int v24; // [rsp+B0h] [rbp+40h] BYREF
  const char *v25; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (wchar_t *)&stru_180032B98;
  if ( !a3 )
  {
    v8 = -2147467261;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = 547;
      v20 = "OnDataReceived";
      LODWORD(v25) = -2147467261;
      v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v22 = "Unexpected NULL object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)this,
        (__int64)&word_18003D1F6,
        0,
        a4,
        (const unsigned __int16 **)&v22,
        (__int64)&v25,
        (const unsigned __int16 **)&v21,
        (__int64)&v24,
        (const unsigned __int16 **)&v20);
    }
    goto LABEL_39;
  }
  if ( a2 < 8 )
  {
    v9 = 2147500037LL;
    v8 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = 548;
      v22 = "Malformed PDU received from server";
      v10 = (__int16 *)&dword_18003D194;
      v21 = "OnDataReceived";
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v23 = "Error condition failed";
      v19 = &v22;
      v18 = &v21;
      v17 = &v20;
      v11 = &v23;
LABEL_7:
      LODWORD(v25) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (__int64)v10,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)v11,
        (__int64)&v25,
        (const unsigned __int16 **)v17,
        (__int64)&v24,
        (const unsigned __int16 **)v18,
        (const unsigned __int16 **)v19);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  v12 = *((_DWORD *)a3 + 1);
  if ( a2 < v12 )
  {
    v9 = 2147500037LL;
    v8 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = 551;
      v23 = "PDU length is greater than buffer size";
      v10 = word_18003D132;
      v22 = "OnDataReceived";
      v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v20 = "Error condition failed";
      v19 = &v23;
      v18 = &v22;
      v17 = &v21;
      v11 = &v20;
      goto LABEL_7;
    }
LABEL_39:
    RDSDWMDirectTraceLogging::LogError(
      (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 112),
      (struct _GUID *)v4,
      (unsigned __int16 *)v8,
      a4);
    RdpRemoteAppGfxRedirectionHandler::CleanupSessionObjects((RdpRemoteAppGfxRedirectionHandler *)((char *)this - 56));
    return v8;
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    v4 = L"CapsReceived";
    if ( v12 < 0xA )
    {
      v9 = 2147500037LL;
      v8 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v24 = 566;
        v23 = "Unexpected PDU length";
        v10 = (__int16 *)&unk_18003D0D0;
        v22 = "OnDataReceived";
        v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v20 = "Error condition failed";
        v19 = &v23;
        v18 = &v22;
        v17 = &v21;
        v11 = &v20;
        goto LABEL_7;
      }
      goto LABEL_39;
    }
    if ( *((_DWORD *)this + 22) )
    {
      v9 = 2147942413LL;
      v8 = -2147024883;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v24 = 568;
        v23 = "Unexpected Caps PDU type. Caps already received";
        v10 = &word_18003D06E;
        v22 = "OnDataReceived";
        v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v20 = "Error condition failed";
        v19 = &v23;
        v18 = &v22;
        v17 = &v21;
        v11 = &v20;
        goto LABEL_7;
      }
      goto LABEL_39;
    }
    updated = RdpRemoteAppGfxRedirectionHandler::HandleCapsPdu(
                (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 56),
                (struct _RDPXREMOTEAPPGFXREDIRECTION_LEGACY_CAPS_PDU *const)a3);
  }
  else
  {
    v13 = (unsigned int)(*(_DWORD *)a3 - 3);
    if ( *(_DWORD *)a3 == 3 )
    {
      v4 = L"GraphicsUpdateAckReceived";
      if ( v12 < 0x10 )
      {
        v9 = 2147500037LL;
        v8 = -2147467259;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v24 = 603;
          v23 = "Unexpected PDU length";
          v10 = (__int16 *)&unk_18003CF48;
          v22 = "OnDataReceived";
          v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v20 = "Error condition failed";
          v19 = &v23;
          v18 = &v22;
          v17 = &v21;
          v11 = &v20;
          goto LABEL_7;
        }
        goto LABEL_39;
      }
      v8 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized((RdpRemoteAppGfxRedirectionHandler *)((char *)this - 56));
      if ( (v8 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v24 = 606;
          v23 = "Channel not initialized. caps not received";
          LODWORD(v25) = v8;
          v22 = "OnDataReceived";
          v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v20 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)dword_180044008,
            (__int64)&word_18003CEE6,
            v15,
            a4,
            (const unsigned __int16 **)&v20,
            (__int64)&v25,
            (const unsigned __int16 **)&v21,
            (__int64)&v24,
            (const unsigned __int16 **)&v22,
            (const unsigned __int16 **)&v23);
        }
        goto LABEL_39;
      }
      updated = RdpRemoteAppGfxRedirectionHandler::HandleGraphicsUpdateAckPdu(
                  (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 56),
                  (struct _RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU *const)a3,
                  v15,
                  a4);
    }
    else
    {
      if ( *(_DWORD *)a3 != 8 )
      {
        v8 = 0;
        if ( (unsigned int)dword_180044008 > 3 )
        {
          v24 = *(_DWORD *)a3;
          v25 = "Unknown PDU type %d";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (__int64)&byte_18003CE9F,
            (__int64)a3,
            a4,
            (const unsigned __int16 **)&v25,
            (__int64)&v24);
        }
        return v8;
      }
      v4 = L"CapsAdvertiseReceived";
      if ( v12 < 8 )
      {
        v9 = 2147500037LL;
        v8 = -2147467259;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v24 = 585;
          v23 = "Unexpected PDU length";
          v10 = (__int16 *)&dword_18003D00C;
          v22 = "OnDataReceived";
          v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v20 = "Error condition failed";
          v19 = &v23;
          v18 = &v22;
          v17 = &v21;
          v11 = &v20;
          goto LABEL_7;
        }
        goto LABEL_39;
      }
      if ( *((_DWORD *)this + 22) )
      {
        v9 = 2147942413LL;
        v8 = -2147024883;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v24 = 587;
          v23 = "Unexpected Caps PDU type. Caps already received";
          v10 = word_18003CFAA;
          v22 = "OnDataReceived";
          v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v20 = "Error condition failed";
          v19 = &v23;
          v18 = &v22;
          v17 = &v21;
          v11 = &v20;
          goto LABEL_7;
        }
        goto LABEL_39;
      }
      updated = RdpRemoteAppGfxRedirectionHandler::HandleCapsAdvertisePdu(
                  (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 56),
                  (struct _RDPXREMOTEAPPGFXREDIRECTION_CAPS_ADVERTISE_PDU *const)a3);
    }
  }
  v8 = updated;
  if ( updated < 0 )
    goto LABEL_39;
  return v8;
}

```

## disassembly

```asm
0x180014c00  mov     r11, rsp
0x180014c03  mov     [r11+8], rbx
0x180014c07  push    rbp
0x180014c08  push    rsi
0x180014c09  push    rdi
0x180014c0a  push    r14
0x180014c0c  push    r15
0x180014c0e  mov     rbp, rsp
0x180014c11  sub     rsp, 70h
0x180014c15  lea     r14, stru_180032B98
0x180014c1c  mov     rdi, r8
0x180014c1f  mov     eax, edx
0x180014c21  mov     rsi, rcx
0x180014c24  test    r8, r8
0x180014c27  jnz     short loc_180014CA1
0x180014c29  mov     eax, cs:dword_180044008
0x180014c2f  mov     ebx, 80004003h
0x180014c34  cmp     eax, 2
0x180014c37  jbe     loc_1800151DB
0x180014c3d  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014c44  mov     [rbp+arg_10], 223h
0x180014c4b  mov     [rbp+var_20], rax
0x180014c4f  lea     rdx, word_18003D1F6
0x180014c56  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014c5d  mov     dword ptr [rbp+arg_18], ebx
0x180014c60  mov     [rbp+var_18], rax
0x180014c64  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180014c6b  mov     [rbp+var_10], rax
0x180014c6f  lea     rax, [rbp+var_20]
0x180014c73  mov     [r11-58h], rax
0x180014c77  lea     rax, [rbp+arg_10]
0x180014c7b  mov     [r11-60h], rax
0x180014c7f  lea     rax, [rbp+var_18]
0x180014c83  mov     [r11-68h], rax
0x180014c87  lea     rax, [rbp+arg_18]
0x180014c8b  mov     [r11-70h], rax
0x180014c8f  lea     rax, [rbp+var_10]
0x180014c93  mov     [r11-78h], rax
0x180014c97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180014c9c  jmp     loc_1800151DB
0x180014ca1  cmp     eax, 8
0x180014ca4  jnb     loc_180014D3D
0x180014caa  mov     eax, cs:dword_180044008
0x180014cb0  mov     ecx, 80004005h
0x180014cb5  mov     ebx, ecx
0x180014cb7  cmp     eax, 2
0x180014cba  jbe     loc_1800151DB
0x180014cc0  lea     rax, aMalformedPduRe; "Malformed PDU received from server"
0x180014cc7  mov     [rbp+arg_10], 224h
0x180014cce  mov     [rbp+var_10], rax
0x180014cd2  lea     rdx, dword_18003D194
0x180014cd9  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014ce0  mov     [rbp+var_18], rax
0x180014ce4  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014ceb  mov     [rbp+var_20], rax
0x180014cef  lea     rax, aErrorCondition; "Error condition failed"
0x180014cf6  mov     [rbp+var_8], rax
0x180014cfa  lea     rax, [rbp+var_10]
0x180014cfe  mov     [rsp+70h+var_28], rax
0x180014d03  lea     rax, [rbp+var_18]
0x180014d07  mov     [rsp+70h+var_30], rax
0x180014d0c  lea     rax, [rbp+arg_10]
0x180014d10  mov     [rsp+70h+var_38], rax
0x180014d15  lea     rax, [rbp+var_20]
0x180014d19  mov     [rsp+70h+var_40], rax
0x180014d1e  lea     rax, [rbp+arg_18]
0x180014d22  mov     [rsp+70h+var_48], rax
0x180014d27  lea     rax, [rbp+var_8]
0x180014d2b  mov     dword ptr [rbp+arg_18], ecx
0x180014d2e  mov     [rsp+70h+var_50], rax
0x180014d33  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014d38  jmp     loc_1800151DB
0x180014d3d  mov     edx, [r8+4]
0x180014d41  cmp     eax, edx
0x180014d43  jnb     loc_180014DCF
0x180014d49  mov     eax, cs:dword_180044008
0x180014d4f  mov     ecx, 80004005h
0x180014d54  mov     ebx, ecx
0x180014d56  cmp     eax, 2
0x180014d59  jbe     loc_1800151DB
0x180014d5f  lea     rax, aPduLengthIsGre; "PDU length is greater than buffer size"
0x180014d66  mov     [rbp+arg_10], 227h
0x180014d6d  mov     [rbp+var_8], rax
0x180014d71  lea     rdx, word_18003D132
0x180014d78  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014d7f  mov     [rbp+var_10], rax
0x180014d83  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014d8a  mov     [rbp+var_18], rax
0x180014d8e  lea     rax, aErrorCondition; "Error condition failed"
0x180014d95  mov     [rbp+var_20], rax
0x180014d99  lea     rax, [rbp+var_8]
0x180014d9d  mov     [rsp+70h+var_28], rax
0x180014da2  lea     rax, [rbp+var_10]
0x180014da6  mov     [rsp+70h+var_30], rax
0x180014dab  lea     rax, [rbp+arg_10]
0x180014daf  mov     [rsp+70h+var_38], rax
0x180014db4  lea     rax, [rbp+var_18]
0x180014db8  mov     [rsp+70h+var_40], rax
0x180014dbd  lea     rax, [rbp+arg_18]
0x180014dc1  mov     [rsp+70h+var_48], rax
0x180014dc6  lea     rax, [rbp+var_20]
0x180014dca  jmp     loc_180014D2B
0x180014dcf  mov     ecx, [r8]
0x180014dd2  sub     ecx, 1
0x180014dd5  jz      loc_1800150A4
0x180014ddb  sub     ecx, 2
0x180014dde  jz      loc_180014F68
0x180014de4  cmp     ecx, 5
0x180014de7  jz      short loc_180014E2E
0x180014de9  mov     eax, cs:dword_180044008
0x180014def  xor     ebx, ebx
0x180014df1  cmp     eax, 3
0x180014df4  jbe     loc_1800151F3
0x180014dfa  mov     eax, [r8]
0x180014dfd  lea     rdx, byte_18003CE9F
0x180014e04  mov     [rbp+arg_10], eax
0x180014e07  lea     rax, aUnknownPduType_0; "Unknown PDU type %d"
0x180014e0e  mov     [rbp+arg_18], rax
0x180014e12  lea     rax, [rbp+arg_10]
0x180014e16  mov     [rsp+70h+var_48], rax
0x180014e1b  lea     rax, [rbp+arg_18]
0x180014e1f  mov     [rsp+70h+var_50], rax
0x180014e24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180014e29  jmp     loc_1800151F3
0x180014e2e  lea     r14, aCapsadvertiser; "CapsAdvertiseReceived"
0x180014e35  cmp     edx, 8
0x180014e38  jnb     loc_180014EC4
0x180014e3e  mov     eax, cs:dword_180044008
0x180014e44  mov     ecx, 80004005h
0x180014e49  mov     ebx, ecx
0x180014e4b  cmp     eax, 2
0x180014e4e  jbe     loc_1800151DB
0x180014e54  lea     rax, aUnexpectedPduL; "Unexpected PDU length"
0x180014e5b  mov     [rbp+arg_10], 249h
0x180014e62  mov     [rbp+var_8], rax
0x180014e66  lea     rdx, dword_18003D00C
0x180014e6d  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014e74  mov     [rbp+var_10], rax
0x180014e78  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014e7f  mov     [rbp+var_18], rax
0x180014e83  lea     rax, aErrorCondition; "Error condition failed"
0x180014e8a  mov     [rbp+var_20], rax
0x180014e8e  lea     rax, [rbp+var_8]
0x180014e92  mov     [rsp+70h+var_28], rax
0x180014e97  lea     rax, [rbp+var_10]
0x180014e9b  mov     [rsp+70h+var_30], rax
0x180014ea0  lea     rax, [rbp+arg_10]
0x180014ea4  mov     [rsp+70h+var_38], rax
0x180014ea9  lea     rax, [rbp+var_18]
0x180014ead  mov     [rsp+70h+var_40], rax
0x180014eb2  lea     rax, [rbp+arg_18]
0x180014eb6  mov     [rsp+70h+var_48], rax
0x180014ebb  lea     rax, [rbp+var_20]
0x180014ebf  jmp     loc_180014D2B
0x180014ec4  lea     rcx, [rsi-38h]; this
0x180014ec8  cmp     dword ptr [rcx+90h], 0
0x180014ecf  jz      loc_180014F5B
0x180014ed5  mov     eax, cs:dword_180044008
0x180014edb  mov     ecx, 8007000Dh
0x180014ee0  mov     ebx, ecx
0x180014ee2  cmp     eax, 2
0x180014ee5  jbe     loc_1800151DB
0x180014eeb  lea     rax, aUnexpectedCaps; "Unexpected Caps PDU type. Caps already "...
0x180014ef2  mov     [rbp+arg_10], 24Bh
0x180014ef9  mov     [rbp+var_8], rax
0x180014efd  lea     rdx, word_18003CFAA
0x180014f04  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014f0b  mov     [rbp+var_10], rax
0x180014f0f  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014f16  mov     [rbp+var_18], rax
0x180014f1a  lea     rax, aErrorCondition; "Error condition failed"
0x180014f21  mov     [rbp+var_20], rax
0x180014f25  lea     rax, [rbp+var_8]
0x180014f29  mov     [rsp+70h+var_28], rax
0x180014f2e  lea     rax, [rbp+var_10]
0x180014f32  mov     [rsp+70h+var_30], rax
0x180014f37  lea     rax, [rbp+arg_10]
0x180014f3b  mov     [rsp+70h+var_38], rax
0x180014f40  lea     rax, [rbp+var_18]
0x180014f44  mov     [rsp+70h+var_40], rax
0x180014f49  lea     rax, [rbp+arg_18]
0x180014f4d  mov     [rsp+70h+var_48], rax
0x180014f52  lea     rax, [rbp+var_20]
0x180014f56  jmp     loc_180014D2B
0x180014f5b  mov     rdx, rdi; struct _RDPXREMOTEAPPGFXREDIRECTION_CAPS_ADVERTISE_PDU *
0x180014f5e  call    ?HandleCapsAdvertisePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJQEAU_RDPXREMOTEAPPGFXREDIRECTION_CAPS_ADVERTISE_PDU@@@Z; RdpRemoteAppGfxRedirectionHandler::HandleCapsAdvertisePdu(_RDPXREMOTEAPPGFXREDIRECTION_CAPS_ADVERTISE_PDU * const)
0x180014f63  jmp     loc_1800151D5
0x180014f68  lea     r14, aGraphicsupdate; "GraphicsUpdateAckReceived"
0x180014f6f  cmp     edx, 10h
0x180014f72  jnb     loc_180014FFE
0x180014f78  mov     eax, cs:dword_180044008
0x180014f7e  mov     ecx, 80004005h
0x180014f83  mov     ebx, ecx
0x180014f85  cmp     eax, 2
0x180014f88  jbe     loc_1800151DB
0x180014f8e  lea     rax, aUnexpectedPduL; "Unexpected PDU length"
0x180014f95  mov     [rbp+arg_10], 25Bh
0x180014f9c  mov     [rbp+var_8], rax
0x180014fa0  lea     rdx, unk_18003CF48
0x180014fa7  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180014fae  mov     [rbp+var_10], rax
0x180014fb2  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014fb9  mov     [rbp+var_18], rax
0x180014fbd  lea     rax, aErrorCondition; "Error condition failed"
0x180014fc4  mov     [rbp+var_20], rax
0x180014fc8  lea     rax, [rbp+var_8]
0x180014fcc  mov     [rsp+70h+var_28], rax
0x180014fd1  lea     rax, [rbp+var_10]
0x180014fd5  mov     [rsp+70h+var_30], rax
0x180014fda  lea     rax, [rbp+arg_10]
0x180014fde  mov     [rsp+70h+var_38], rax
0x180014fe3  lea     rax, [rbp+var_18]
0x180014fe7  mov     [rsp+70h+var_40], rax
0x180014fec  lea     rax, [rbp+arg_18]
0x180014ff0  mov     [rsp+70h+var_48], rax
0x180014ff5  lea     rax, [rbp+var_20]
0x180014ff9  jmp     loc_180014D2B
0x180014ffe  lea     rcx, [rsi-38h]; this
0x180015002  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x180015007  mov     ebx, eax
0x180015009  test    eax, eax
0x18001500b  jns     loc_180015093
0x180015011  mov     ecx, cs:dword_180044008
0x180015017  cmp     ecx, 2
0x18001501a  jbe     loc_1800151DB
0x180015020  lea     rax, aChannelNotInit_4; "Channel not initialized. caps not recei"...
0x180015027  mov     [rbp+arg_10], 25Eh
0x18001502e  mov     [rbp+var_8], rax
0x180015032  lea     rdx, word_18003CEE6
0x180015039  lea     rax, aOndatareceived_0; "OnDataReceived"
0x180015040  mov     dword ptr [rbp+arg_18], ebx
0x180015043  mov     [rbp+var_10], rax
0x180015047  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001504e  mov     [rbp+var_18], rax
0x180015052  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015059  mov     [rbp+var_20], rax
0x18001505d  lea     rax, [rbp+var_8]
0x180015061  mov     [rsp+70h+var_28], rax
0x180015066  lea     rax, [rbp+var_10]
0x18001506a  mov     [rsp+70h+var_30], rax
0x18001506f  lea     rax, [rbp+arg_10]
0x180015073  mov     [rsp+70h+var_38], rax
0x180015078  lea     rax, [rbp+var_18]
0x18001507c  mov     [rsp+70h+var_40], rax
0x180015081  lea     rax, [rbp+arg_18]
0x180015085  mov     [rsp+70h+var_48], rax
0x18001508a  lea     rax, [rbp+var_20]
0x18001508e  jmp     loc_180014D2E
0x180015093  mov     rdx, rdi; struct _RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU *
0x180015096  lea     rcx, [rsi-38h]; this
0x18001509a  call    ?HandleGraphicsUpdateAckPdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJQEAU_RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU@@@Z; RdpRemoteAppGfxRedirectionHandler::HandleGraphicsUpdateAckPdu(_RDPXREMOTEAPPGFXREDIRECTION_GRAPHICS_UPDATE_ACK_PDU * const)
0x18001509f  jmp     loc_1800151D5
0x1800150a4  lea     r14, aCapsreceived; "CapsReceived"
0x1800150ab  cmp     edx, 0Ah
0x1800150ae  jnb     loc_18001513A
0x1800150b4  mov     eax, cs:dword_180044008
0x1800150ba  mov     ecx, 80004005h
0x1800150bf  mov     ebx, ecx
0x1800150c1  cmp     eax, 2
0x1800150c4  jbe     loc_1800151DB
0x1800150ca  lea     rax, aUnexpectedPduL; "Unexpected PDU length"
0x1800150d1  mov     [rbp+arg_10], 236h
0x1800150d8  mov     [rbp+var_8], rax
0x1800150dc  lea     rdx, unk_18003D0D0
0x1800150e3  lea     rax, aOndatareceived_0; "OnDataReceived"
0x1800150ea  mov     [rbp+var_10], rax
0x1800150ee  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800150f5  mov     [rbp+var_18], rax
0x1800150f9  lea     rax, aErrorCondition; "Error condition failed"
0x180015100  mov     [rbp+var_20], rax
0x180015104  lea     rax, [rbp+var_8]
0x180015108  mov     [rsp+70h+var_28], rax
0x18001510d  lea     rax, [rbp+var_10]
0x180015111  mov     [rsp+70h+var_30], rax
0x180015116  lea     rax, [rbp+arg_10]
0x18001511a  mov     [rsp+70h+var_38], rax
0x18001511f  lea     rax, [rbp+var_18]
0x180015123  mov     [rsp+70h+var_40], rax
0x180015128  lea     rax, [rbp+arg_18]
0x18001512c  mov     [rsp+70h+var_48], rax
0x180015131  lea     rax, [rbp+var_20]
0x180015135  jmp     loc_180014D2B
0x18001513a  lea     rcx, [rsi-38h]; this
0x18001513e  cmp     dword ptr [rcx+90h], 0
0x180015145  jz      loc_1800151CD
0x18001514b  mov     eax, cs:dword_180044008
0x180015151  mov     ecx, 8007000Dh
0x180015156  mov     ebx, ecx
0x180015158  cmp     eax, 2
0x18001515b  jbe     short loc_1800151DB
0x18001515d  lea     rax, aUnexpectedCaps; "Unexpected Caps PDU type. Caps already "...
0x180015164  mov     [rbp+arg_10], 238h
0x18001516b  mov     [rbp+var_8], rax
0x18001516f  lea     rdx, word_18003D06E
0x180015176  lea     rax, aOndatareceived_0; "OnDataReceived"
0x18001517d  mov     [rbp+var_10], rax
0x180015181  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015188  mov     [rbp+var_18], rax
0x18001518c  lea     rax, aErrorCondition; "Error condition failed"
0x180015193  mov     [rbp+var_20], rax
  ... truncated ...
```
