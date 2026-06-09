# RdpRemoteAppGfxRedirectionHandler::OnCompositionSurfaceCreated(HWND__ *,void *)

- ea: `0x1800149e0`
- end: `0x180014bf2`
- name: `?OnCompositionSurfaceCreated@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHWND__@@PEAX@Z`
- size: `530`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *this, HWND, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001188`
- `0x180001724`
- `0x1800149e0`
- `0x180016700`
- `0x180016bdc`
- `0x180019ccc`
- `0x180019d58`

## import_xrefs

- `GDI32!D3DKMTVailPromoteCompositionSurface` at `0x180014a0d`
- `GDI32!D3DKMTVailPromoteCompositionSurface` at `0x180014a0d`

## string_xrefs

- `0x180014b83`: `Failed to send protocol error to client`
- `0x180014a27`: `OnCompositionSurfaceCreated`
- `0x180014ad0`: `OnCompositionSurfaceCreated`
- `0x180014adc`: `Failed to send composition surface handle to client`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnCompositionSurfaceCreated(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        void *a3)
{
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int CompositionSurfacePdu; // ebx
  RdpRemoteAppGfxRedirectionHandler *v10; // r14
  unsigned __int16 *v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+50h] [rbp-30h] BYREF
  void *v18; // [rsp+58h] [rbp-28h] BYREF
  const char *v19; // [rsp+60h] [rbp-20h] BYREF
  const char *v20; // [rsp+68h] [rbp-18h] BYREF
  const char *v21; // [rsp+70h] [rbp-10h] BYREF
  const char *v22; // [rsp+78h] [rbp-8h] BYREF
  int v23; // [rsp+B8h] [rbp+38h] BYREF

  v18 = 0;
  v5 = D3DKMTVailPromoteCompositionSurface(a3, &v18);
  CompositionSurfacePdu = v5 | 0x10000000;
  if ( v5 >= 0 )
  {
    v10 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48);
    CompositionSurfacePdu = RdpRemoteAppGfxRedirectionHandler::SendCreateCompositionSurfacePdu(
                              (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48),
                              a2,
                              v18);
    if ( (CompositionSurfacePdu & 0x80000000) == 0 )
    {
      RDSDWMDirectTraceLogging::LogVAILModeState(
        (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 120),
        (struct _GUID *)&stru_180033120,
        v11);
      return CompositionSurfacePdu;
    }
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v21 = "OnCompositionSurfaceCreated";
      v22 = "Failed to send composition surface handle to client";
      v23 = 1087;
      v20 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v19 = "Error HResult failed";
      v17 = CompositionSurfacePdu;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&dword_18003C5A4,
        (__int64)v11,
        v12,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        (const unsigned __int16 **)&v20,
        (__int64)&v23,
        (const unsigned __int16 **)&v21,
        (const unsigned __int16 **)&v22);
    }
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = "OnCompositionSurfaceCreated";
      v19 = "Failed to add dirty rectange to bounds accumulator";
      v23 = 1081;
      v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v22 = "Error HResult failed";
      v17 = v5 | 0x10000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (__int64)&word_18003C606,
        v7,
        v8,
        (const unsigned __int16 **)&v22,
        (__int64)&v17,
        (const unsigned __int16 **)&v21,
        (__int64)&v23,
        (const unsigned __int16 **)&v20,
        (const unsigned __int16 **)&v19);
    }
    v10 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48);
  }
  RDSDWMDirectTraceLogging::LogVAILModeError(
    (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 120),
    (struct _GUID *)&stru_180033120,
    (unsigned __int16 *)CompositionSurfacePdu);
  v13 = RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(v10, CompositionSurfacePdu);
  if ( v13 < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v23 = v13;
    v22 = "OnCompositionSurfaceCreated";
    v21 = "Failed to send protocol error to client";
    v20 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_18003C554,
      v14,
      v15,
      (const unsigned __int16 **)&v20,
      (const unsigned __int16 **)&v21,
      (__int64)&v23,
      (const unsigned __int16 **)&v22);
  }
  return CompositionSurfacePdu;
}

```

## disassembly

```asm
0x1800149e0  mov     [rsp-18h+arg_0], rbx
0x1800149e5  mov     [rsp-18h+arg_8], rsi
0x1800149ea  push    rbp
0x1800149eb  push    rdi
0x1800149ec  push    r14
0x1800149ee  mov     rbp, rsp
0x1800149f1  sub     rsp, 80h
0x1800149f8  mov     rsi, rdx
0x1800149fb  mov     [rbp+var_28], 0
0x180014a03  mov     rdi, rcx
0x180014a06  lea     rdx, [rbp+var_28]
0x180014a0a  mov     rcx, r8
0x180014a0d  call    cs:__imp_D3DKMTVailPromoteCompositionSurface
0x180014a13  mov     ebx, eax
0x180014a15  or      ebx, 10000000h
0x180014a1b  jge     loc_180014AAD
0x180014a21  mov     eax, cs:dword_180044008
0x180014a27  lea     rsi, aOncompositions; "OnCompositionSurfaceCreated"
0x180014a2e  cmp     eax, 2
0x180014a31  jbe     short loc_180014AA4
0x180014a33  lea     rax, aFailedToAddDir; "Failed to add dirty rectange to bounds "...
0x180014a3a  mov     [rbp+var_18], rsi
0x180014a3e  mov     [rbp+var_20], rax
0x180014a42  lea     rdx, word_18003C606
0x180014a49  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014a50  mov     [rbp+arg_18], 439h
0x180014a57  mov     [rbp+var_10], rax
0x180014a5b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180014a62  mov     [rbp+var_8], rax
0x180014a66  lea     rax, [rbp+var_20]
0x180014a6a  mov     [rsp+80h+var_38], rax
0x180014a6f  lea     rax, [rbp+var_18]
0x180014a73  mov     [rsp+80h+var_40], rax
0x180014a78  lea     rax, [rbp+arg_18]
0x180014a7c  mov     [rsp+80h+var_48], rax
0x180014a81  lea     rax, [rbp+var_10]
0x180014a85  mov     [rsp+80h+var_50], rax
0x180014a8a  lea     rax, [rbp+var_30]
0x180014a8e  mov     [rsp+80h+var_58], rax
0x180014a93  lea     rax, [rbp+var_8]
0x180014a97  mov     [rsp+80h+var_60], rax
0x180014a9c  mov     [rbp+var_30], ebx
0x180014a9f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014aa4  lea     r14, [rdi-30h]
0x180014aa8  jmp     loc_180014B4D
0x180014aad  mov     r8, [rbp+var_28]; void *
0x180014ab1  lea     r14, [rdi-30h]
0x180014ab5  mov     rcx, r14; this
0x180014ab8  mov     rdx, rsi; HWND
0x180014abb  call    ?SendCreateCompositionSurfacePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@PEAX@Z; RdpRemoteAppGfxRedirectionHandler::SendCreateCompositionSurfacePdu(HWND__ *,void *)
0x180014ac0  mov     ebx, eax
0x180014ac2  test    eax, eax
0x180014ac4  jns     loc_180014BC8
0x180014aca  mov     ecx, cs:dword_180044008
0x180014ad0  lea     rsi, aOncompositions; "OnCompositionSurfaceCreated"
0x180014ad7  cmp     ecx, 2
0x180014ada  jbe     short loc_180014B4D
0x180014adc  lea     rax, aFailedToSendCo; "Failed to send composition surface hand"...
0x180014ae3  mov     [rbp+var_10], rsi
0x180014ae7  mov     [rbp+var_8], rax
0x180014aeb  lea     rdx, dword_18003C5A4
0x180014af2  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014af9  mov     [rbp+arg_18], 43Fh
0x180014b00  mov     [rbp+var_18], rax
0x180014b04  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180014b0b  mov     [rbp+var_20], rax
0x180014b0f  lea     rax, [rbp+var_8]
0x180014b13  mov     [rsp+80h+var_38], rax
0x180014b18  lea     rax, [rbp+var_10]
0x180014b1c  mov     [rsp+80h+var_40], rax
0x180014b21  lea     rax, [rbp+arg_18]
0x180014b25  mov     [rsp+80h+var_48], rax
0x180014b2a  lea     rax, [rbp+var_18]
0x180014b2e  mov     [rsp+80h+var_50], rax
0x180014b33  lea     rax, [rbp+var_30]
0x180014b37  mov     [rsp+80h+var_58], rax
0x180014b3c  lea     rax, [rbp+var_20]
0x180014b40  mov     [rsp+80h+var_60], rax
0x180014b45  mov     [rbp+var_30], ebx
0x180014b48  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014b4d  lea     rcx, [rdi+78h]; this
0x180014b51  mov     r8d, ebx; unsigned __int16 *
0x180014b54  lea     rdx, stru_180033120; struct _GUID *
0x180014b5b  call    ?LogVAILModeError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogVAILModeError(_GUID *,ushort *,long)
0x180014b60  mov     edx, ebx; int
0x180014b62  mov     rcx, r14; this
0x180014b65  call    ?SendErrorPdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(long)
0x180014b6a  test    eax, eax
0x180014b6c  jns     short loc_180014BD8
0x180014b6e  mov     ecx, cs:dword_180044008
0x180014b74  cmp     ecx, 3
0x180014b77  jbe     short loc_180014BD8
0x180014b79  mov     [rbp+arg_18], eax
0x180014b7c  lea     rdx, dword_18003C554
0x180014b83  lea     rax, aFailedToSendPr; "Failed to send protocol error to client"
0x180014b8a  mov     [rbp+var_8], rsi
0x180014b8e  mov     [rbp+var_10], rax
0x180014b92  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180014b99  mov     [rbp+var_18], rax
0x180014b9d  lea     rax, [rbp+var_8]
0x180014ba1  mov     [rsp+80h+var_48], rax
0x180014ba6  lea     rax, [rbp+arg_18]
0x180014baa  mov     [rsp+80h+var_50], rax
0x180014baf  lea     rax, [rbp+var_10]
0x180014bb3  mov     [rsp+80h+var_58], rax
0x180014bb8  lea     rax, [rbp+var_18]
0x180014bbc  mov     [rsp+80h+var_60], rax
0x180014bc1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180014bc6  jmp     short loc_180014BD8
0x180014bc8  lea     rcx, [rdi+78h]; this
0x180014bcc  lea     rdx, stru_180033120; struct _GUID *
0x180014bd3  call    ?LogVAILModeState@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogVAILModeState(_GUID *,ushort *)
0x180014bd8  lea     r11, [rsp+80h+var_s0]
0x180014be0  mov     eax, ebx
0x180014be2  mov     rbx, [r11+20h]
0x180014be6  mov     rsi, [r11+28h]
0x180014bea  mov     rsp, r11
0x180014bed  pop     r14
0x180014bef  pop     rdi
0x180014bf0  pop     rbp
0x180014bf1  retn
```
