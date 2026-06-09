# RdpRemoteAppAuxRedirectionHandler::OnDestroyVailSuperWetInk(HWND__ *)

- ea: `0x180018520`
- end: `0x180018651`
- name: `?OnDestroyVailSuperWetInk@RdpRemoteAppAuxRedirectionHandler@@UEAAJPEAUHWND__@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001188`
- `0x180001724`
- `0x180018520`
- `0x180018e70`
- `0x180019340`
- `0x180019ccc`

## string_xrefs

- `0x180018601`: `Failed to send protocol error to client`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::OnDestroyVailSuperWetInk(
        RdpRemoteAppAuxRedirectionHandler *this,
        HWND a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v13[2]; // [rsp+60h] [rbp-10h] BYREF
  int v14; // [rsp+A0h] [rbp+30h] BYREF
  const char *v15; // [rsp+B0h] [rbp+40h] BYREF
  const char *v16; // [rsp+B8h] [rbp+48h] BYREF

  v4 = RdpRemoteAppAuxRedirectionHandler::SendDestroyVailSuperWetInk(
         (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
         a2);
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v11 = "OnDestroyVailSuperWetInk";
      v16 = "Failed to send destroy vail super wet ink message to client";
      v14 = 488;
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v13[0] = (const unsigned __int16 *)"Error HResult failed";
      LODWORD(v15) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (__int64)&unk_18003DF98,
        v5,
        v6,
        v13,
        (__int64)&v15,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        (const unsigned __int16 **)&v11,
        (const unsigned __int16 **)&v16);
    }
    RDSDWMDirectTraceLogging::LogVAILModeError(
      (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 48),
      (struct _GUID *)&stru_180033A38,
      (unsigned __int16 *)(unsigned int)v4);
    v7 = RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(
           (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
           -1071243243);
    if ( v7 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v14 = v7;
      v15 = "OnDestroyVailSuperWetInk";
      v16 = "Failed to send protocol error to client";
      v13[0] = (const unsigned __int16 *)"HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&unk_18003DF48,
        v8,
        v9,
        v13,
        (const unsigned __int16 **)&v16,
        (__int64)&v14,
        (const unsigned __int16 **)&v15);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018520  push    rbp
0x180018522  push    rbx
0x180018523  push    rsi
0x180018524  push    rdi
0x180018525  push    r14
0x180018527  mov     rbp, rsp
0x18001852a  sub     rsp, 70h
0x18001852e  mov     rdi, rcx
0x180018531  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180018535  call    ?SendDestroyVailSuperWetInk@RdpRemoteAppAuxRedirectionHandler@@IEAAJPEAUHWND__@@@Z; RdpRemoteAppAuxRedirectionHandler::SendDestroyVailSuperWetInk(HWND__ *)
0x18001853a  mov     ebx, eax
0x18001853c  test    eax, eax
0x18001853e  jns     loc_180018644
0x180018544  mov     edx, cs:dword_180044008
0x18001854a  lea     r14, aOndestroyvails; "OnDestroyVailSuperWetInk"
0x180018551  cmp     edx, 2
0x180018554  jbe     short loc_1800185C7
0x180018556  lea     rax, aFailedToSendDe_1; "Failed to send destroy vail super wet i"...
0x18001855d  mov     [rbp+var_20], r14
0x180018561  mov     [rbp+arg_18], rax
0x180018565  lea     rdx, unk_18003DF98
0x18001856c  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180018573  mov     [rbp+arg_0], 1E8h
0x18001857a  mov     [rbp+var_18], rax
0x18001857e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180018585  mov     [rbp+var_10], rax
0x180018589  lea     rax, [rbp+arg_18]
0x18001858d  mov     [rsp+70h+var_28], rax
0x180018592  lea     rax, [rbp+var_20]
0x180018596  mov     [rsp+70h+var_30], rax
0x18001859b  lea     rax, [rbp+arg_0]
0x18001859f  mov     [rsp+70h+var_38], rax
0x1800185a4  lea     rax, [rbp+var_18]
0x1800185a8  mov     [rsp+70h+var_40], rax
0x1800185ad  lea     rax, [rbp+arg_10]
0x1800185b1  mov     [rsp+70h+var_48], rax
0x1800185b6  lea     rax, [rbp+var_10]
0x1800185ba  mov     [rsp+70h+var_50], rax
0x1800185bf  mov     dword ptr [rbp+arg_10], ebx
0x1800185c2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800185c7  lea     rcx, [rdi+30h]; this
0x1800185cb  mov     r8d, ebx; unsigned __int16 *
0x1800185ce  lea     rdx, stru_180033A38; struct _GUID *
0x1800185d5  call    ?LogVAILModeError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogVAILModeError(_GUID *,ushort *,long)
0x1800185da  mov     edx, 0C0262015h; int
0x1800185df  lea     rcx, [rdi-38h]; this
0x1800185e3  call    ?SendErrorPdu@RdpRemoteAppAuxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(long)
0x1800185e8  test    eax, eax
0x1800185ea  jns     short loc_180018644
0x1800185ec  mov     ecx, cs:dword_180044008
0x1800185f2  cmp     ecx, 3
0x1800185f5  jbe     short loc_180018644
0x1800185f7  mov     [rbp+arg_0], eax
0x1800185fa  lea     rdx, unk_18003DF48
0x180018601  lea     rax, aFailedToSendPr; "Failed to send protocol error to client"
0x180018608  mov     [rbp+arg_10], r14
0x18001860c  mov     [rbp+arg_18], rax
0x180018610  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180018617  mov     [rbp+var_10], rax
0x18001861b  lea     rax, [rbp+arg_10]
0x18001861f  mov     [rsp+70h+var_38], rax
0x180018624  lea     rax, [rbp+arg_0]
0x180018628  mov     [rsp+70h+var_40], rax
0x18001862d  lea     rax, [rbp+arg_18]
0x180018631  mov     [rsp+70h+var_48], rax
0x180018636  lea     rax, [rbp+var_10]
0x18001863a  mov     [rsp+70h+var_50], rax
0x18001863f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018644  mov     eax, ebx
0x180018646  add     rsp, 70h
0x18001864a  pop     r14
0x18001864c  pop     rdi
0x18001864d  pop     rsi
0x18001864e  pop     rbx
0x18001864f  pop     rbp
0x180018650  retn
```
