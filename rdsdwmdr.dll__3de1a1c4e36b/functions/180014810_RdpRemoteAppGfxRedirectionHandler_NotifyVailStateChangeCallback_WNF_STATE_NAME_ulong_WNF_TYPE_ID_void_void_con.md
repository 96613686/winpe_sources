# RdpRemoteAppGfxRedirectionHandler::NotifyVailStateChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180014810`
- end: `0x1800148bf`
- name: `?NotifyVailStateChangeCallback@RdpRemoteAppGfxRedirectionHandler@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `175`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, RdpRemoteAppGfxRedirectionHandler *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001724`
- `0x180014810`
- `0x180016bdc`

## string_xrefs

- `0x18001483f`: `Failed to send protocol error to client`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::NotifyVailStateChangeCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        RdpRemoteAppGfxRedirectionHandler *a4)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  int v8; // [rsp+50h] [rbp-30h] BYREF
  const char *v9; // [rsp+58h] [rbp-28h] BYREF
  const char *v10; // [rsp+60h] [rbp-20h] BYREF
  const char *v11; // [rsp+68h] [rbp-18h] BYREF
  const char *v12; // [rsp+70h] [rbp-10h] BYREF
  int v13; // [rsp+A8h] [rbp+28h] BYREF

  v4 = RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(a4, -1071243247);
  if ( v4 < 0 && (unsigned int)dword_180044008 > 2 )
  {
    v8 = v4;
    v9 = "Failed to send protocol error to client";
    v12 = "Error HResult failed";
    v10 = "NotifyVailStateChangeCallback";
    v13 = 1609;
    v11 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (__int64)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp",
      (__int64)&byte_18003B977,
      v5,
      v6,
      (const unsigned __int16 **)&v12,
      (__int64)&v8,
      (const unsigned __int16 **)&v11,
      (__int64)&v13,
      (const unsigned __int16 **)&v10,
      (const unsigned __int16 **)&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180014810  push    rbp
0x180014812  mov     rbp, rsp
0x180014815  sub     rsp, 80h
0x18001481c  mov     edx, 0C0262011h; int
0x180014821  mov     rcx, r9; this
0x180014824  call    ?SendErrorPdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(long)
0x180014829  test    eax, eax
0x18001482b  jns     loc_1800148B4
0x180014831  mov     ecx, cs:dword_180044008
0x180014837  cmp     ecx, 2
0x18001483a  jbe     short loc_1800148B4
0x18001483c  mov     [rbp+var_30], eax
0x18001483f  lea     rcx, aFailedToSendPr; "Failed to send protocol error to client"
0x180014846  mov     [rbp+var_28], rcx
0x18001484a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180014851  mov     [rbp+var_10], rax
0x180014855  lea     rcx, aNotifyvailstat; "NotifyVailStateChangeCallback"
0x18001485c  lea     rax, [rbp+var_28]
0x180014860  mov     [rbp+var_20], rcx
0x180014864  mov     [rsp+80h+var_38], rax
0x180014869  lea     rcx, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014870  lea     rax, [rbp+var_20]
0x180014874  mov     [rbp+arg_18], 649h
0x18001487b  mov     [rsp+80h+var_40], rax
0x180014880  lea     rdx, byte_18003B977
0x180014887  lea     rax, [rbp+arg_18]
0x18001488b  mov     [rbp+var_18], rcx
0x18001488f  mov     [rsp+80h+var_48], rax
0x180014894  lea     rax, [rbp+var_18]
0x180014898  mov     [rsp+80h+var_50], rax
0x18001489d  lea     rax, [rbp+var_30]
0x1800148a1  mov     [rsp+80h+var_58], rax
0x1800148a6  lea     rax, [rbp+var_10]
0x1800148aa  mov     [rsp+80h+var_60], rax
0x1800148af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800148b4  xor     eax, eax
0x1800148b6  add     rsp, 80h
0x1800148bd  pop     rbp
0x1800148be  retn
```
