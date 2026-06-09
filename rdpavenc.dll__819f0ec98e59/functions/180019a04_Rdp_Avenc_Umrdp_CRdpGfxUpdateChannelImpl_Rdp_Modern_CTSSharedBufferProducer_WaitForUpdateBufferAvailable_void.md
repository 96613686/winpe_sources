# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)

- ea: `0x180019a04`
- end: `0x180019b7e`
- name: `?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ`
- size: `378`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800156dc`
- `0x1800158e4`
- `0x180015ad8`
- `0x180015cd8`
- `0x180015ec8`
- `0x1800160b8`
- `0x1800162b4`
- `0x1800164a0`
- `0x18001669c`
- `0x18001689c`
- `0x180016a9c`
- `0x180016c9c`

## callees

- `0x180001008`
- `0x1800080cc`
- `0x180019998`
- `0x1800199cc`
- `0x180019a04`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x180019a31`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WaitForMultipleObjects` at `0x180019a31`

## string_xrefs

- `0x180019a58`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019ada`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019b39`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019b5d`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180019a46`: `UpdateBufferEmptyEvent signaled!`
- `0x180019a5f`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable`
- `0x180019ae1`: `Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable`
- `0x180019ac8`: `UpdateBufferEmptyEvent timed out!`

## pseudocode

```c
char __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(
        __int64 a1)
{
  DWORD v1; // eax
  int v2; // r9d
  unsigned int v4; // eax
  char *v5; // [rsp+20h] [rbp-30h]
  const char *v6; // [rsp+28h] [rbp-28h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  int v9; // [rsp+60h] [rbp+10h] BYREF
  const char *v10; // [rsp+68h] [rbp+18h] BYREF
  const char *v11; // [rsp+70h] [rbp+20h] BYREF
  const char *v12; // [rsp+78h] [rbp+28h] BYREF

  Handles[0] = *(HANDLE *)(a1 + 128);
  Handles[1] = *(HANDLE *)(a1 + 120);
  v1 = WaitForMultipleObjects(2u, Handles, 0, 0x3E8u);
  if ( v1 )
  {
    if ( v1 == 1 )
    {
      v4 = wil::verify_hresult<long>(2147500036LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        (const char *)v4,
        (int)"Abort event was signaled!",
        v6);
    }
    if ( v1 != 258 )
    {
      LODWORD(v5) = v1;
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        "Wait failed 0x%x",
        v5);
    }
    if ( (unsigned int)dword_1800C1058 > 2 )
    {
      v9 = 364;
      v10 = "UpdateBufferEmptyEvent timed out!";
      v12 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
      v11 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800AC8D7,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        v2,
        (__int64)&v12,
        (__int64)&v9,
        (__int64)&v11,
        (__int64)&v10);
    }
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v9 = 355;
      v10 = "UpdateBufferEmptyEvent signaled!";
      v12 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp";
      v11 = "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<class Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800AC910,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        v2,
        (__int64)&v12,
        (__int64)&v9,
        (__int64)&v11,
        (__int64)&v10);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180019a04  push    rbp
0x180019a06  mov     rbp, rsp
0x180019a09  sub     rsp, 50h
0x180019a0d  mov     rax, [rcx+80h]
0x180019a14  lea     rdx, [rbp+Handles]; lpHandles
0x180019a18  xor     r8d, r8d; bWaitAll
0x180019a1b  mov     [rbp+Handles], rax
0x180019a1f  mov     rax, [rcx+78h]
0x180019a23  mov     r9d, 3E8h; dwMilliseconds
0x180019a29  mov     [rbp+var_8], rax
0x180019a2d  lea     ecx, [r8+2]; nCount
0x180019a31  call    cs:__imp_WaitForMultipleObjects
0x180019a37  test    eax, eax
0x180019a39  jnz     short loc_180019AAD
0x180019a3b  mov     eax, cs:dword_1800C1058
0x180019a41  cmp     eax, 5
0x180019a44  jbe     short loc_180019AA5
0x180019a46  lea     rax, aUpdatebufferem; "UpdateBufferEmptyEvent signaled!"
0x180019a4d  mov     [rbp+arg_0], 163h
0x180019a54  mov     [rbp+arg_8], rax
0x180019a58  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019a5f  lea     rax, aRdpAvencUmrdpC; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180019a66  mov     [rbp+arg_18], r8
0x180019a6a  mov     [rbp+arg_10], rax
0x180019a6e  lea     rdx, qword_1800AC910
0x180019a75  lea     rax, [rbp+arg_8]
0x180019a79  mov     [rsp+50h+var_18], rax
0x180019a7e  lea     rcx, dword_1800C1058
0x180019a85  lea     rax, [rbp+arg_10]
0x180019a89  mov     [rsp+50h+var_20], rax
0x180019a8e  lea     rax, [rbp+arg_0]
0x180019a92  mov     [rsp+50h+var_28], rax
0x180019a97  lea     rax, [rbp+arg_18]
0x180019a9b  mov     [rsp+50h+var_30], rax
0x180019aa0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180019aa5  mov     al, 1
0x180019aa7  add     rsp, 50h
0x180019aab  pop     rbp
0x180019aac  retn
0x180019aad  cmp     eax, 1
0x180019ab0  jz      loc_180019B4F
0x180019ab6  cmp     eax, 102h
0x180019abb  jnz     short loc_180019B2E
0x180019abd  mov     eax, cs:dword_1800C1058
0x180019ac3  cmp     eax, 2
0x180019ac6  jbe     short loc_180019B27
0x180019ac8  lea     rax, aUpdatebufferem_0; "UpdateBufferEmptyEvent timed out!"
0x180019acf  mov     [rbp+arg_0], 16Ch
0x180019ad6  mov     [rbp+arg_8], rax
0x180019ada  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019ae1  lea     rax, aRdpAvencUmrdpC; "Rdp::Avenc::Umrdp::CRdpGfxUpdateChannel"...
0x180019ae8  mov     [rbp+arg_18], r8
0x180019aec  mov     [rbp+arg_10], rax
0x180019af0  lea     rdx, byte_1800AC8D7
0x180019af7  lea     rax, [rbp+arg_8]
0x180019afb  mov     [rsp+50h+var_18], rax
0x180019b00  lea     rcx, dword_1800C1058
0x180019b07  lea     rax, [rbp+arg_10]
0x180019b0b  mov     [rsp+50h+var_20], rax
0x180019b10  lea     rax, [rbp+arg_0]
0x180019b14  mov     [rsp+50h+var_28], rax
0x180019b19  lea     rax, [rbp+arg_18]
0x180019b1d  mov     [rsp+50h+var_30], rax
0x180019b22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180019b27  xor     al, al
0x180019b29  jmp     loc_180019AA7
0x180019b2e  mov     rcx, [rbp+8]; this
0x180019b32  lea     r9, aWaitFailed0xX; "Wait failed 0x%x"
0x180019b39  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019b40  mov     dword ptr [rsp+50h+var_30], eax; char *
0x180019b44  mov     edx, 170h; void *
0x180019b49  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180019b4f  mov     ecx, 80004004h
0x180019b54  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180019b59  mov     rcx, [rbp+8]; this
0x180019b5d  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180019b64  mov     r9d, eax; char *
0x180019b67  mov     edx, 168h; void *
0x180019b6c  lea     rax, aAbortEventWasS; "Abort event was signaled!"
0x180019b73  mov     [rsp+50h+var_30], rax; int
0x180019b78  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
