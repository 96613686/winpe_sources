# RdpRemoteAppAuxRedirectionHandler::OnCompositionWindowDpi(HWND__ *,uint)

- ea: `0x180017ed0`
- end: `0x180018012`
- name: `?OnCompositionWindowDpi@RdpRemoteAppAuxRedirectionHandler@@UEAAJPEAUHWND__@@I@Z`
- size: `322`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *__hidden this, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001188`
- `0x180001724`
- `0x180017ed0`
- `0x1800188bc`
- `0x180019340`
- `0x180019ccc`

## string_xrefs

- `0x180017fb8`: `Failed to send protocol error to client`
- `0x180017f01`: `OnCompositionWindowDpi`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::OnCompositionWindowDpi(
        RdpRemoteAppAuxRedirectionHandler *this,
        HWND a2,
        unsigned int a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  const char *v12; // [rsp+50h] [rbp-20h] BYREF
  const char *v13; // [rsp+58h] [rbp-18h] BYREF
  const char *v14; // [rsp+60h] [rbp-10h] BYREF
  const char *v15; // [rsp+68h] [rbp-8h] BYREF
  int v16; // [rsp+90h] [rbp+20h] BYREF
  const char *v17; // [rsp+A8h] [rbp+38h] BYREF

  v5 = RdpRemoteAppAuxRedirectionHandler::SendCompositionWindowDpi(
         (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
         a2,
         a3);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v13 = "OnCompositionWindowDpi";
      v12 = "Failed to send window dpi message to client";
      v16 = 519;
      v14 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v15 = "Error HResult failed";
      LODWORD(v17) = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (__int64)&word_18003DEE6,
        v6,
        v7,
        (const unsigned __int16 **)&v15,
        (__int64)&v17,
        (const unsigned __int16 **)&v14,
        (__int64)&v16,
        (const unsigned __int16 **)&v13,
        (const unsigned __int16 **)&v12);
    }
    RDSDWMDirectTraceLogging::LogVAILModeError(
      (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 48),
      (struct _GUID *)&stru_180033AB8,
      (unsigned __int16 *)(unsigned int)v5);
    v8 = RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(
           (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
           -1071243242);
    if ( v8 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v16 = v8;
      v17 = "OnCompositionWindowDpi";
      v15 = "Failed to send protocol error to client";
      v14 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&word_18003DE96,
        v9,
        v10,
        (const unsigned __int16 **)&v14,
        (const unsigned __int16 **)&v15,
        (__int64)&v16,
        (const unsigned __int16 **)&v17);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017ed0  mov     [rsp-18h+arg_8], rbx
0x180017ed5  mov     [rsp-18h+arg_10], rsi
0x180017eda  push    rbp
0x180017edb  push    rdi
0x180017edc  push    r14
0x180017ede  mov     rbp, rsp
0x180017ee1  sub     rsp, 70h
0x180017ee5  mov     rdi, rcx
0x180017ee8  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180017eec  call    ?SendCompositionWindowDpi@RdpRemoteAppAuxRedirectionHandler@@IEAAJPEAUHWND__@@I@Z; RdpRemoteAppAuxRedirectionHandler::SendCompositionWindowDpi(HWND__ *,uint)
0x180017ef1  mov     ebx, eax
0x180017ef3  test    eax, eax
0x180017ef5  jns     loc_180017FFB
0x180017efb  mov     edx, cs:dword_180044008
0x180017f01  lea     r14, aOncompositionw_0; "OnCompositionWindowDpi"
0x180017f08  cmp     edx, 2
0x180017f0b  jbe     short loc_180017F7E
0x180017f0d  lea     rax, aFailedToSendWi; "Failed to send window dpi message to cl"...
0x180017f14  mov     [rbp+var_18], r14
0x180017f18  mov     [rbp+var_20], rax
0x180017f1c  lea     rdx, word_18003DEE6
0x180017f23  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180017f2a  mov     [rbp+arg_0], 207h
0x180017f31  mov     [rbp+var_10], rax
0x180017f35  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180017f3c  mov     [rbp+var_8], rax
0x180017f40  lea     rax, [rbp+var_20]
0x180017f44  mov     [rsp+70h+var_28], rax
0x180017f49  lea     rax, [rbp+var_18]
0x180017f4d  mov     [rsp+70h+var_30], rax
0x180017f52  lea     rax, [rbp+arg_0]
0x180017f56  mov     [rsp+70h+var_38], rax
0x180017f5b  lea     rax, [rbp+var_10]
0x180017f5f  mov     [rsp+70h+var_40], rax
0x180017f64  lea     rax, [rbp+arg_18]
0x180017f68  mov     [rsp+70h+var_48], rax
0x180017f6d  lea     rax, [rbp+var_8]
0x180017f71  mov     [rsp+70h+var_50], rax
0x180017f76  mov     dword ptr [rbp+arg_18], ebx
0x180017f79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180017f7e  lea     rcx, [rdi+30h]; this
0x180017f82  mov     r8d, ebx; unsigned __int16 *
0x180017f85  lea     rdx, stru_180033AB8; struct _GUID *
0x180017f8c  call    ?LogVAILModeError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogVAILModeError(_GUID *,ushort *,long)
0x180017f91  mov     edx, 0C0262016h; int
0x180017f96  lea     rcx, [rdi-38h]; this
0x180017f9a  call    ?SendErrorPdu@RdpRemoteAppAuxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(long)
0x180017f9f  test    eax, eax
0x180017fa1  jns     short loc_180017FFB
0x180017fa3  mov     ecx, cs:dword_180044008
0x180017fa9  cmp     ecx, 3
0x180017fac  jbe     short loc_180017FFB
0x180017fae  mov     [rbp+arg_0], eax
0x180017fb1  lea     rdx, word_18003DE96
0x180017fb8  lea     rax, aFailedToSendPr; "Failed to send protocol error to client"
0x180017fbf  mov     [rbp+arg_18], r14
0x180017fc3  mov     [rbp+var_8], rax
0x180017fc7  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180017fce  mov     [rbp+var_10], rax
0x180017fd2  lea     rax, [rbp+arg_18]
0x180017fd6  mov     [rsp+70h+var_38], rax
0x180017fdb  lea     rax, [rbp+arg_0]
0x180017fdf  mov     [rsp+70h+var_40], rax
0x180017fe4  lea     rax, [rbp+var_8]
0x180017fe8  mov     [rsp+70h+var_48], rax
0x180017fed  lea     rax, [rbp+var_10]
0x180017ff1  mov     [rsp+70h+var_50], rax
0x180017ff6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180017ffb  lea     r11, [rsp+70h+var_s0]
0x180018000  mov     eax, ebx
0x180018002  mov     rbx, [r11+28h]
0x180018006  mov     rsi, [r11+30h]
0x18001800a  mov     rsp, r11
0x18001800d  pop     r14
0x18001800f  pop     rdi
0x180018010  pop     rbp
0x180018011  retn
```
