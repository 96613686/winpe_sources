# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)

- ea: `0x180019df0`
- end: `0x180019ea8`
- name: `?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ`
- size: `184`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e8a0`
- `0x180011b48`
- `0x180011d40`
- `0x1800123a0`
- `0x180012430`
- `0x180012950`
- `0x180013264`
- `0x180013878`
- `0x18001a228`
- `0x18001a700`
- `0x18001ab50`
- `0x180020850`
- `0x180020930`
- `0x180020a08`
- `0x180020b44`
- `0x180021a40`
- `0x180021a50`

## callees

- `0x180001008`
- `0x18000b07c`
- `0x180019df0`
- `0x18007d7a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019e15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019e15`

## string_xrefs

- `0x180019e4a`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019e36`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::unlock`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(
        __int64 a1)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v6; // [rsp+50h] [rbp+8h] BYREF
  const char *v7; // [rsp+58h] [rbp+10h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF
  const char *v9; // [rsp+68h] [rbp+20h] BYREF

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *(_BYTE *)(a1 + 144) = 0;
  if ( !SetEvent(*(HANDLE *)(a1 + 136)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v2, v3);
  result = (unsigned int)dword_1800C1058;
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v7 = "UserModeLockEvent unlocked";
    v8 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::unlock";
    v6 = 257;
    v9 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
             (unsigned int)&dword_1800C1058,
             (unsigned int)&byte_1800AC9BF,
             v2,
             (_DWORD)v3,
             (__int64)&v9,
             (__int64)&v6,
             (__int64)&v8,
             (__int64)&v7);
  }
  return result;
}

```

## disassembly

```asm
0x180019df0  push    rbx
0x180019df2  sub     rsp, 40h
0x180019df6  mov     rbx, rcx
0x180019df9  cmp     byte ptr [rcx+90h], 0
0x180019e00  jnz     short loc_180019E07
0x180019e02  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019e07  mov     byte ptr [rbx+90h], 0
0x180019e0e  mov     rcx, [rbx+88h]; hEvent
0x180019e15  call    cs:__imp_SetEvent
0x180019e1b  test    eax, eax
0x180019e1d  jz      short loc_180019E98
0x180019e1f  mov     eax, cs:dword_1800C1058
0x180019e25  cmp     eax, 5
0x180019e28  jbe     short loc_180019E92
0x180019e2a  lea     rax, aUsermodelockev_1; "UserModeLockEvent unlocked"
0x180019e31  mov     [rsp+48h+arg_8], rax
0x180019e36  lea     rax, aRdpAvencUmrdpC_9; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180019e3d  mov     [rsp+48h+arg_10], rax
0x180019e42  mov     [rsp+48h+arg_0], 101h
0x180019e4a  lea     rax, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019e51  mov     [rsp+48h+arg_18], rax
0x180019e56  lea     rax, [rsp+48h+arg_8]
0x180019e5b  mov     [rsp+48h+var_10], rax
0x180019e60  lea     rax, [rsp+48h+arg_10]
0x180019e65  mov     [rsp+48h+var_18], rax
0x180019e6a  lea     rax, [rsp+48h+arg_0]
0x180019e6f  mov     [rsp+48h+var_20], rax
0x180019e74  lea     rax, [rsp+48h+arg_18]
0x180019e79  mov     [rsp+48h+var_28], rax
0x180019e7e  lea     rdx, byte_1800AC9BF
0x180019e85  lea     rcx, dword_1800C1058
0x180019e8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180019e91  nop
0x180019e92  add     rsp, 40h
0x180019e96  pop     rbx
0x180019e97  retn
0x180019e98  mov     rcx, [rsp+48h]; this
0x180019e9d  mov     edx, 0A01h; void *
0x180019ea2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
