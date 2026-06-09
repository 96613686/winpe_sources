# RdpRemoteAppGfxRedirectionHandler::OnSharedMemorySectionCreated(uint,uint,long)

- ea: `0x180015a60`
- end: `0x180015b92`
- name: `?OnSharedMemorySectionCreated@RdpRemoteAppGfxRedirectionHandler@@QEAAXIIJ@Z`
- size: `306`
- prototype: `void __fastcall(RdpRemoteAppGfxRedirectionHandler *this, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013210`

## callees

- `0x180001724`
- `0x180015a60`
- `0x180016bdc`
- `0x180019b70`

## string_xrefs

- `0x180015b0b`: `Failed to send protocol error to client`
- `0x180015b21`: `OnSharedMemorySectionCreated`

## pseudocode

```c
void __fastcall RdpRemoteAppGfxRedirectionHandler::OnSharedMemorySectionCreated(
        RdpRemoteAppGfxRedirectionHandler *this,
        int a2,
        unsigned int a3,
        int a4)
{
  int v6; // eax
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // [rsp+50h] [rbp-20h] BYREF
  const char *v11; // [rsp+58h] [rbp-18h] BYREF
  const char *v12; // [rsp+60h] [rbp-10h] BYREF
  const char *v13; // [rsp+68h] [rbp-8h] BYREF
  int v14; // [rsp+88h] [rbp+18h] BYREF
  int v15; // [rsp+98h] [rbp+28h] BYREF

  v14 = a2;
  if ( a4 < 0 )
  {
    RDSDWMDirectTraceLogging::LogSharedMemoryCreationFailure(
      (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 168),
      (struct _GUID *)(unsigned int)a4,
      a3);
    v7 = RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(this, a4);
    if ( v7 < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v15 = v7;
      v10 = "Failed to send protocol error to client";
      v13 = "Error HResult failed";
      v11 = "OnSharedMemorySectionCreated";
      v14 = 373;
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (__int64)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp",
        (__int64)word_18003D39A,
        v8,
        v9,
        (const unsigned __int16 **)&v13,
        (__int64)&v15,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        (const unsigned __int16 **)&v11,
        (const unsigned __int16 **)&v10);
    }
  }
  else
  {
    v6 = *((_DWORD *)this + 76);
    *((float *)this + 72) = (float)((float)((float)v6 * *((float *)this + 72)) + (float)(int)a3) / (float)(v6 + 1);
    if ( (unsigned __int64)a3 > *((_QWORD *)this + 37) )
      *((_QWORD *)this + 37) = a3;
    *((_DWORD *)this + 76) = v6 + 1;
  }
}

```

## disassembly

```asm
0x180015a60  mov     [rsp-8+arg_0], rbx
0x180015a65  mov     [rsp-8+arg_10], rdi
0x180015a6a  mov     [rsp-8+arg_8], edx
0x180015a6e  push    rbp
0x180015a6f  mov     rbp, rsp
0x180015a72  sub     rsp, 70h
0x180015a76  mov     edi, r9d
0x180015a79  mov     rbx, rcx
0x180015a7c  test    r9d, r9d
0x180015a7f  js      short loc_180015ADD
0x180015a81  mov     eax, [rcx+130h]
0x180015a87  xorps   xmm2, xmm2
0x180015a8a  xorps   xmm0, xmm0
0x180015a8d  xorps   xmm1, xmm1
0x180015a90  cvtsi2ss xmm2, rax
0x180015a95  lea     ecx, [rax+1]
0x180015a98  mov     eax, r8d
0x180015a9b  cvtsi2ss xmm0, rax
0x180015aa0  mov     eax, ecx
0x180015aa2  mulss   xmm2, dword ptr [rbx+120h]
0x180015aaa  cvtsi2ss xmm1, rax
0x180015aaf  mov     eax, r8d
0x180015ab2  addss   xmm2, xmm0
0x180015ab6  divss   xmm2, xmm1
0x180015aba  movss   dword ptr [rbx+120h], xmm2
0x180015ac2  cmp     rax, [rbx+128h]
0x180015ac9  jbe     short loc_180015AD2
0x180015acb  mov     [rbx+128h], rax
0x180015ad2  mov     [rbx+130h], ecx
0x180015ad8  jmp     loc_180015B80
0x180015add  add     rcx, 0A8h; this
0x180015ae4  mov     edx, edi; struct _GUID *
0x180015ae6  call    ?LogSharedMemoryCreationFailure@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@J@Z; RDSDWMDirectTraceLogging::LogSharedMemoryCreationFailure(_GUID *,long)
0x180015aeb  mov     edx, edi; int
0x180015aed  mov     rcx, rbx; this
0x180015af0  call    ?SendErrorPdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJJ@Z; RdpRemoteAppGfxRedirectionHandler::SendErrorPdu(long)
0x180015af5  test    eax, eax
0x180015af7  jns     loc_180015B80
0x180015afd  mov     ecx, cs:dword_180044008
0x180015b03  cmp     ecx, 2
0x180015b06  jbe     short loc_180015B80
0x180015b08  mov     [rbp+arg_18], eax
0x180015b0b  lea     rcx, aFailedToSendPr; "Failed to send protocol error to client"
0x180015b12  mov     [rbp+var_20], rcx
0x180015b16  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180015b1d  mov     [rbp+var_8], rax
0x180015b21  lea     rcx, aOnsharedmemory; "OnSharedMemorySectionCreated"
0x180015b28  lea     rax, [rbp+var_20]
0x180015b2c  mov     [rbp+var_18], rcx
0x180015b30  mov     [rsp+70h+var_28], rax
0x180015b35  lea     rcx, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015b3c  lea     rax, [rbp+var_18]
0x180015b40  mov     [rbp+arg_8], 175h
0x180015b47  mov     [rsp+70h+var_30], rax
0x180015b4c  lea     rdx, word_18003D39A
0x180015b53  lea     rax, [rbp+arg_8]
0x180015b57  mov     [rbp+var_10], rcx
0x180015b5b  mov     [rsp+70h+var_38], rax
0x180015b60  lea     rax, [rbp+var_10]
0x180015b64  mov     [rsp+70h+var_40], rax
0x180015b69  lea     rax, [rbp+arg_18]
0x180015b6d  mov     [rsp+70h+var_48], rax
0x180015b72  lea     rax, [rbp+var_8]
0x180015b76  mov     [rsp+70h+var_50], rax
0x180015b7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180015b80  lea     r11, [rsp+70h+var_s0]
0x180015b85  mov     rbx, [r11+10h]
0x180015b89  mov     rdi, [r11+20h]
0x180015b8d  mov     rsp, r11
0x180015b90  pop     rbp
0x180015b91  retn
```
