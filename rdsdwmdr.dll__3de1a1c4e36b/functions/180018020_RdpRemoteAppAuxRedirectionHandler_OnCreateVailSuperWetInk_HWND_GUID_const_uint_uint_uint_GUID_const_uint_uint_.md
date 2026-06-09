# RdpRemoteAppAuxRedirectionHandler::OnCreateVailSuperWetInk(HWND__ *,_GUID const &,uint,uint,uint,_GUID const &,uint,uint,uint)

- ea: `0x180018020`
- end: `0x180018194`
- name: `?OnCreateVailSuperWetInk@RdpRemoteAppAuxRedirectionHandler@@UEAAJPEAUHWND__@@AEBU_GUID@@III1III@Z`
- size: `372`
- prototype: `__int64 __fastcall(RdpRemoteAppAuxRedirectionHandler *__hidden this, HWND, const struct _GUID *, unsigned int, unsigned int, unsigned int, const struct _GUID *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001188`
- `0x180001724`
- `0x180018020`
- `0x180018b2c`
- `0x180019340`
- `0x180019ccc`

## string_xrefs

- `0x180018137`: `Failed to send protocol error to client`
- `0x18001808c`: `Failed to send create vail super wet ink message to client`
- `0x180018080`: `OnCreateVailSuperWetInk`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::OnCreateVailSuperWetInk(
        RdpRemoteAppAuxRedirectionHandler *this,
        HWND a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        const struct _GUID *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10)
{
  int VailSuperWetInk; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  const unsigned __int16 *v22[2]; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+20h] BYREF

  VailSuperWetInk = RdpRemoteAppAuxRedirectionHandler::SendCreateVailSuperWetInk(
                      (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
                      a2,
                      a3,
                      a4,
                      a5,
                      a6,
                      a7,
                      a8,
                      a9,
                      a10);
  if ( VailSuperWetInk < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = "OnCreateVailSuperWetInk";
      v19 = "Failed to send create vail super wet ink message to client";
      v23 = 459;
      v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappauxredirection.cpp";
      v22[0] = (const unsigned __int16 *)"Error HResult failed";
      v18 = VailSuperWetInk;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)word_18003E04A,
        v12,
        v13,
        v22,
        (__int64)&v18,
        (const unsigned __int16 **)&v21,
        (__int64)&v23,
        (const unsigned __int16 **)&v20,
        (const unsigned __int16 **)&v19);
    }
    RDSDWMDirectTraceLogging::LogVAILModeError(
      (RdpRemoteAppAuxRedirectionHandler *)((char *)this + 48),
      (struct _GUID *)&stru_1800339A0,
      (unsigned __int16 *)(unsigned int)VailSuperWetInk);
    v14 = RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(
            (RdpRemoteAppAuxRedirectionHandler *)((char *)this - 56),
            -1071243244);
    if ( v14 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v23 = v14;
      v22[0] = (const unsigned __int16 *)"OnCreateVailSuperWetInk";
      v21 = "Failed to send protocol error to client";
      v20 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)word_18003DFFA,
        v15,
        v16,
        (const unsigned __int16 **)&v20,
        (const unsigned __int16 **)&v21,
        (__int64)&v23,
        v22);
    }
  }
  return (unsigned int)VailSuperWetInk;
}

```

## disassembly

```asm
0x180018020  mov     [rsp-18h+arg_8], rbx
0x180018025  mov     [rsp-18h+arg_10], rsi
0x18001802a  push    rbp
0x18001802b  push    rdi
0x18001802c  push    r14
0x18001802e  mov     rbp, rsp
0x180018031  sub     rsp, 80h
0x180018038  mov     eax, [rbp+arg_48]
0x18001803b  mov     rdi, rcx
0x18001803e  mov     [rsp+80h+var_38], eax; unsigned int
0x180018042  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180018046  mov     eax, [rbp+arg_40]
0x180018049  mov     [rsp+80h+var_40], eax; unsigned int
0x18001804d  mov     eax, [rbp+arg_38]
0x180018050  mov     [rsp+80h+var_48], eax; unsigned int
0x180018054  mov     rax, [rbp+arg_30]
0x180018058  mov     [rsp+80h+var_50], rax; struct _GUID *
0x18001805d  mov     eax, [rbp+arg_28]
0x180018060  mov     [rsp+80h+var_58], eax; unsigned int
0x180018064  mov     eax, [rbp+arg_20]
0x180018067  mov     [rsp+80h+var_60], eax; unsigned int
0x18001806b  call    ?SendCreateVailSuperWetInk@RdpRemoteAppAuxRedirectionHandler@@IEAAJPEAUHWND__@@AEBU_GUID@@III1III@Z; RdpRemoteAppAuxRedirectionHandler::SendCreateVailSuperWetInk(HWND__ *,_GUID const &,uint,uint,uint,_GUID const &,uint,uint,uint)
0x180018070  mov     ebx, eax
0x180018072  test    eax, eax
0x180018074  jns     loc_18001817A
0x18001807a  mov     ecx, cs:dword_180044008
0x180018080  lea     r14, aOncreatevailsu; "OnCreateVailSuperWetInk"
0x180018087  cmp     ecx, 2
0x18001808a  jbe     short loc_1800180FD
0x18001808c  lea     rax, aFailedToSendCr_0; "Failed to send create vail super wet in"...
0x180018093  mov     [rbp+var_20], r14
0x180018097  mov     [rbp+var_28], rax
0x18001809b  lea     rdx, word_18003E04A
0x1800180a2  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800180a9  mov     [rbp+arg_0], 1CBh
0x1800180b0  mov     [rbp+var_18], rax
0x1800180b4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800180bb  mov     [rbp+var_10], rax
0x1800180bf  lea     rax, [rbp+var_28]
0x1800180c3  mov     qword ptr [rsp+80h+var_38], rax
0x1800180c8  lea     rax, [rbp+var_20]
0x1800180cc  mov     qword ptr [rsp+80h+var_40], rax
0x1800180d1  lea     rax, [rbp+arg_0]
0x1800180d5  mov     qword ptr [rsp+80h+var_48], rax
0x1800180da  lea     rax, [rbp+var_18]
0x1800180de  mov     [rsp+80h+var_50], rax
0x1800180e3  lea     rax, [rbp+var_30]
0x1800180e7  mov     qword ptr [rsp+80h+var_58], rax
0x1800180ec  lea     rax, [rbp+var_10]
0x1800180f0  mov     qword ptr [rsp+80h+var_60], rax
0x1800180f5  mov     [rbp+var_30], ebx
0x1800180f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800180fd  lea     rcx, [rdi+30h]; this
0x180018101  mov     r8d, ebx; unsigned __int16 *
0x180018104  lea     rdx, stru_1800339A0; struct _GUID *
0x18001810b  call    ?LogVAILModeError@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAGJ@Z; RDSDWMDirectTraceLogging::LogVAILModeError(_GUID *,ushort *,long)
0x180018110  mov     edx, 0C0262014h; int
0x180018115  lea     rcx, [rdi-38h]; this
0x180018119  call    ?SendErrorPdu@RdpRemoteAppAuxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppAuxRedirectionHandler::SendErrorPdu(long)
0x18001811e  test    eax, eax
0x180018120  jns     short loc_18001817A
0x180018122  mov     ecx, cs:dword_180044008
0x180018128  cmp     ecx, 3
0x18001812b  jbe     short loc_18001817A
0x18001812d  mov     [rbp+arg_0], eax
0x180018130  lea     rdx, word_18003DFFA
0x180018137  lea     rax, aFailedToSendPr; "Failed to send protocol error to client"
0x18001813e  mov     [rbp+var_10], r14
0x180018142  mov     [rbp+var_18], rax
0x180018146  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18001814d  mov     [rbp+var_20], rax
0x180018151  lea     rax, [rbp+var_10]
0x180018155  mov     qword ptr [rsp+80h+var_48], rax
0x18001815a  lea     rax, [rbp+arg_0]
0x18001815e  mov     [rsp+80h+var_50], rax
0x180018163  lea     rax, [rbp+var_18]
0x180018167  mov     qword ptr [rsp+80h+var_58], rax
0x18001816c  lea     rax, [rbp+var_20]
0x180018170  mov     qword ptr [rsp+80h+var_60], rax
0x180018175  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001817a  lea     r11, [rsp+80h+var_s0]
0x180018182  mov     eax, ebx
0x180018184  mov     rbx, [r11+28h]
0x180018188  mov     rsi, [r11+30h]
0x18001818c  mov     rsp, r11
0x18001818f  pop     r14
0x180018191  pop     rdi
0x180018192  pop     rbp
0x180018193  retn
```
