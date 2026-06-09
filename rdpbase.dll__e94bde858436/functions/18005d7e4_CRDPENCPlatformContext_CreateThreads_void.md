# CRDPENCPlatformContext::CreateThreads(void)

- ea: `0x18005d7e4`
- end: `0x18005ddf6`
- name: `?CreateThreads@CRDPENCPlatformContext@@IEAAJXZ`
- size: `1554`
- prototype: `__int64 __fastcall(CRDPENCPlatformContext *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800e1888`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180005090`
- `0x180019a80`
- `0x180019ab0`
- `0x18005d7e4`
- `0x180162010`

## string_xrefs

- `0x18005d895`: `ITSPlatform::CreateThread failed`
- `0x18005d826`: `STA threads already created`
- `0x18005d93b`: `ITSThread::BindThread failed`
- `0x18005d8a7`: `CreateThreads`
- `0x18005d94d`: `CreateThreads`
- `0x18005d9e1`: `CreateThreads`
- `0x18005da78`: `CreateThreads`
- `0x18005db1b`: `CreateThreads`
- `0x18005dbb2`: `CreateThreads`
- `0x18005dc9a`: `CreateThreads`
- `0x18005da66`: `Failed to start the STA thread`
- `0x18005d9cf`: `Failed to create the STA thread`
- `0x18005dba0`: `Failed to start the Worker thread`
- `0x18005db09`: `Failed to create the Worker thread`
- `0x18005dd50`: `Failed to set Worker thread watchdog`
- `0x18005dcc1`: `Failed to set STA thread watchdog`

## pseudocode

```c
__int64 __fastcall CRDPENCPlatformContext::CreateThreads(CRDPENCPlatformContext *this, __int64 a2, __int64 a3, int a4)
{
  bool v4; // zf
  int v6; // ebx
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(__int64, void (__fastcall *)(void *), CRDPENCPlatformContext *, __int64 **); // rax
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  char *v12; // rdx
  const char **v13; // rax
  __int64 **v14; // rdi
  __int64 **v15; // r15
  __int64 *v16; // rdi
  __int64 v17; // rbx
  unsigned int v18; // eax
  int v19; // eax
  int v20; // r8d
  int v21; // r9d
  __int64 *v22; // rdi
  __int64 v23; // rbx
  unsigned int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  const char **v29; // [rsp+30h] [rbp-40h]
  const char **v30; // [rsp+40h] [rbp-30h]
  const char **v31; // [rsp+48h] [rbp-28h]
  const char *v32; // [rsp+50h] [rbp-20h] BYREF
  const char *v33; // [rsp+58h] [rbp-18h] BYREF
  const char *v34; // [rsp+60h] [rbp-10h] BYREF
  const char *v35; // [rsp+68h] [rbp-8h] BYREF
  const char *v36; // [rsp+B0h] [rbp+40h] BYREF
  const char *v37; // [rsp+B8h] [rbp+48h] BYREF
  __int64 *v38; // [rsp+C0h] [rbp+50h] BYREF
  __int64 *v39; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *((_DWORD *)this + 40) == 0;
  v38 = 0;
  v39 = 0;
  if ( v4 )
  {
    v6 = 1;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v36 = "STA threads already created";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&dword_1801BDDEC,
        0,
        a4,
        (__int64)&v36);
    }
    goto LABEL_39;
  }
  v7 = *((_QWORD *)this + 8);
  v8 = *(__int64 (__fastcall **)(__int64, void (__fastcall *)(void *), CRDPENCPlatformContext *, __int64 **))(*(_QWORD *)v7 + 56LL);
  if ( *((_DWORD *)this + 46) )
  {
    v6 = v8(v7, 0, 0, &v38);
    if ( v6 < 0 )
    {
      v11 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_35:
        if ( v38 )
          (*(void (__fastcall **)(__int64 *, _QWORD))(*v38 + 56))(v38, 0);
        if ( v39 )
          (*(void (__fastcall **)(__int64 *, _QWORD))(*v39 + 56))(v39, 0);
        goto LABEL_39;
      }
      LODWORD(v36) = 425;
      v32 = "ITSPlatform::CreateThread failed";
      v33 = "CreateThreads";
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = (char *)&word_1801BDD4E;
      v35 = "Error HResult failed";
      v31 = &v32;
      v30 = &v33;
      v29 = &v34;
      v13 = &v35;
LABEL_8:
      LODWORD(v37) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (_DWORD)v12,
        v9,
        v10,
        (__int64)v13,
        (__int64)&v37,
        (__int64)v29,
        (__int64)&v36,
        (__int64)v30,
        (__int64)v31);
      goto LABEL_35;
    }
    v6 = (*(__int64 (__fastcall **)(__int64 *))(*v38 + 40))(v38);
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 428;
      v35 = "ITSThread::BindThread failed";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = byte_1801BDD9D;
      v32 = "Error HResult failed";
      v31 = &v35;
      v30 = &v34;
      v29 = &v33;
      v13 = &v32;
      goto LABEL_8;
    }
  }
  else
  {
    v6 = v8(v7, CRDPENCPlatformContext::STATIC_STAThreadProc, this, &v38);
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 439;
      v35 = "Failed to create the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = &byte_1801BDCFF;
      v32 = "Error HResult failed";
      v31 = &v35;
      v30 = &v34;
      v29 = &v33;
      v13 = &v32;
      goto LABEL_8;
    }
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v38 + 32))(v38, 0);
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 442;
      v35 = "Failed to start the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = byte_1801BDC61;
      v32 = "Error HResult failed";
      v31 = &v35;
      v30 = &v34;
      v29 = &v33;
      v13 = &v32;
      goto LABEL_8;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(void *), CRDPENCPlatformContext *, __int64 **))(**((_QWORD **)this + 8) + 56LL))(
         *((_QWORD *)this + 8),
         CRDPENCPlatformContext::STATIC_STAThreadProc,
         this,
         &v39);
  if ( v6 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 453;
    v35 = "Failed to create the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = (char *)qword_1801BDCB0;
    v32 = "Error HResult failed";
    v31 = &v35;
    v30 = &v34;
    v29 = &v33;
    v13 = &v32;
    goto LABEL_8;
  }
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v39 + 32))(v39, 0);
  if ( v6 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 456;
    v35 = "Failed to start the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = byte_1801BDBD5;
    v32 = "Error HResult failed";
    v31 = &v35;
    v30 = &v34;
    v29 = &v33;
    v13 = &v32;
    goto LABEL_8;
  }
  v14 = (__int64 **)((char *)this + 72);
  if ( v38 != *((__int64 **)this + 9) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 72);
    *v14 = v38;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
  }
  v15 = (__int64 **)((char *)this + 80);
  if ( v39 != *((__int64 **)this + 10) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 80);
    *v15 = v39;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
  }
  v16 = *v14;
  v17 = *v16;
  v18 = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 24))(v16);
  v19 = (*(__int64 (__fastcall **)(__int64 *, void (__fastcall *)(void *), void (__fastcall *)(void *), _QWORD, int, _DWORD))(v17 + 200))(
          v16,
          CRDPENCPlatformContext::STAThreadStuckWatchdogReport,
          CRDPENCPlatformContext::STAThreadRecoveredWatchdogReport,
          v18,
          180000,
          0);
  if ( v19 < 0 && (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v36) = v19;
    v37 = "CreateThreads";
    v35 = "Failed to set STA thread watchdog";
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)&dword_1801BDC24,
      v20,
      v21,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&v36,
      (__int64)&v37);
  }
  v22 = *v15;
  v23 = **v15;
  v24 = (*(__int64 (__fastcall **)(__int64 *))(v23 + 24))(*v15);
  v6 = (*(__int64 (__fastcall **)(__int64 *, void (__fastcall *)(void *), void (__fastcall *)(void *), _QWORD, int, _DWORD))(v23 + 200))(
         v22,
         CRDPENCPlatformContext::WorkerThreadStuckWatchdogReport,
         CRDPENCPlatformContext::WorkerThreadRecoveredWatchdogReport,
         v24,
         180000,
         0);
  if ( v6 < 0 && (unsigned int)CallbackContext > 3 )
  {
    v37 = "CreateThreads";
    v35 = "Failed to set Worker thread watchdog";
    LODWORD(v36) = v6;
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v25,
      (unsigned int)byte_1801BDB5B,
      v26,
      v27,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&v36,
      (__int64)&v37);
  }
  *((_DWORD *)this + 40) = 0;
  if ( v6 < 0 )
    goto LABEL_35;
LABEL_39:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v39);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v38);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005d7e4  push    rbp
0x18005d7e6  push    rbx
0x18005d7e7  push    rsi
0x18005d7e8  push    rdi
0x18005d7e9  push    r13
0x18005d7eb  push    r14
0x18005d7ed  push    r15
0x18005d7ef  mov     rbp, rsp
0x18005d7f2  sub     rsp, 70h
0x18005d7f6  cmp     dword ptr [rcx+0A0h], 0
0x18005d7fd  mov     r14, rcx
0x18005d800  mov     [rbp+arg_10], 0
0x18005d808  mov     [rbp+arg_18], 0
0x18005d810  jnz     short loc_18005D855
0x18005d812  mov     eax, cs:CallbackContext
0x18005d818  mov     ebx, 1
0x18005d81d  cmp     eax, 3
0x18005d820  jbe     loc_18005DDD3
0x18005d826  lea     rax, aStaThreadsAlre; "STA threads already created"
0x18005d82d  xor     r8d, r8d
0x18005d830  mov     [rbp+arg_0], rax
0x18005d834  lea     rdx, dword_1801BDDEC
0x18005d83b  lea     rax, [rbp+arg_0]
0x18005d83f  lea     rcx, CallbackContext
0x18005d846  mov     [rsp+70h+var_50], rax
0x18005d84b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005d850  jmp     loc_18005DDD3
0x18005d855  cmp     dword ptr [r14+0B8h], 0
0x18005d85d  lea     r9, [rbp+arg_10]
0x18005d861  mov     rcx, [rcx+40h]
0x18005d865  mov     rax, [rcx]
0x18005d868  mov     rax, [rax+38h]
0x18005d86c  jz      loc_18005D9AB
0x18005d872  xor     r8d, r8d
0x18005d875  xor     edx, edx
0x18005d877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d87c  mov     ebx, eax
0x18005d87e  test    eax, eax
0x18005d880  jns     loc_18005D912
0x18005d886  mov     ecx, cs:CallbackContext
0x18005d88c  cmp     ecx, 2
0x18005d88f  jbe     loc_18005DDA5
0x18005d895  lea     rax, aItsplatformCre; "ITSPlatform::CreateThread failed"
0x18005d89c  mov     dword ptr [rbp+arg_0], 1A9h
0x18005d8a3  mov     [rbp+var_20], rax
0x18005d8a7  lea     rsi, aCreatethreads; "CreateThreads"
0x18005d8ae  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005d8b5  mov     [rbp+var_18], rsi
0x18005d8b9  mov     [rbp+var_10], rax
0x18005d8bd  lea     rdx, word_1801BDD4E
0x18005d8c4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005d8cb  mov     [rbp+var_8], rax
0x18005d8cf  lea     rax, [rbp+var_20]
0x18005d8d3  mov     [rsp+70h+var_28], rax
0x18005d8d8  lea     rax, [rbp+var_18]
0x18005d8dc  mov     [rsp+70h+var_30], rax
0x18005d8e1  lea     rax, [rbp+arg_0]
0x18005d8e5  mov     [rsp+70h+var_38], rax
0x18005d8ea  lea     rax, [rbp+var_10]
0x18005d8ee  mov     [rsp+70h+var_40], rax
0x18005d8f3  lea     rax, [rbp+arg_8]
0x18005d8f7  mov     [rsp+70h+var_48], rax
0x18005d8fc  lea     rax, [rbp+var_8]
0x18005d900  mov     [rsp+70h+var_50], rax
0x18005d905  mov     dword ptr [rbp+arg_8], ebx
0x18005d908  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005d90d  jmp     loc_18005DDA5
0x18005d912  mov     rcx, [rbp+arg_10]
0x18005d916  mov     rax, [rcx]
0x18005d919  mov     rax, [rax+28h]
0x18005d91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d922  mov     ebx, eax
0x18005d924  test    eax, eax
0x18005d926  jns     loc_18005DAD6
0x18005d92c  mov     eax, cs:CallbackContext
0x18005d932  cmp     eax, 2
0x18005d935  jbe     loc_18005DDA5
0x18005d93b  lea     rax, aItsthreadBindt; "ITSThread::BindThread failed"
0x18005d942  mov     dword ptr [rbp+arg_0], 1ACh
0x18005d949  mov     [rbp+var_8], rax
0x18005d94d  lea     rsi, aCreatethreads; "CreateThreads"
0x18005d954  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005d95b  mov     [rbp+var_10], rsi
0x18005d95f  mov     [rbp+var_18], rax
0x18005d963  lea     rdx, byte_1801BDD9D
0x18005d96a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005d971  mov     [rbp+var_20], rax
0x18005d975  lea     rax, [rbp+var_8]
0x18005d979  mov     [rsp+70h+var_28], rax
0x18005d97e  lea     rax, [rbp+var_10]
0x18005d982  mov     [rsp+70h+var_30], rax
0x18005d987  lea     rax, [rbp+arg_0]
0x18005d98b  mov     [rsp+70h+var_38], rax
0x18005d990  lea     rax, [rbp+var_18]
0x18005d994  mov     [rsp+70h+var_40], rax
0x18005d999  lea     rax, [rbp+arg_8]
0x18005d99d  mov     [rsp+70h+var_48], rax
0x18005d9a2  lea     rax, [rbp+var_20]
0x18005d9a6  jmp     loc_18005D900
0x18005d9ab  mov     r8, r14
0x18005d9ae  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x18005d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9ba  mov     ebx, eax
0x18005d9bc  test    eax, eax
0x18005d9be  jns     short loc_18005DA3F
0x18005d9c0  mov     eax, cs:CallbackContext
0x18005d9c6  cmp     eax, 2
0x18005d9c9  jbe     loc_18005DDA5
0x18005d9cf  lea     rax, aFailedToCreate_61; "Failed to create the STA thread"
0x18005d9d6  mov     dword ptr [rbp+arg_0], 1B7h
0x18005d9dd  mov     [rbp+var_8], rax
0x18005d9e1  lea     rsi, aCreatethreads; "CreateThreads"
0x18005d9e8  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005d9ef  mov     [rbp+var_10], rsi
0x18005d9f3  mov     [rbp+var_18], rax
0x18005d9f7  lea     rdx, byte_1801BDCFF
0x18005d9fe  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005da05  mov     [rbp+var_20], rax
0x18005da09  lea     rax, [rbp+var_8]
0x18005da0d  mov     [rsp+70h+var_28], rax
0x18005da12  lea     rax, [rbp+var_10]
0x18005da16  mov     [rsp+70h+var_30], rax
0x18005da1b  lea     rax, [rbp+arg_0]
0x18005da1f  mov     [rsp+70h+var_38], rax
0x18005da24  lea     rax, [rbp+var_18]
0x18005da28  mov     [rsp+70h+var_40], rax
0x18005da2d  lea     rax, [rbp+arg_8]
0x18005da31  mov     [rsp+70h+var_48], rax
0x18005da36  lea     rax, [rbp+var_20]
0x18005da3a  jmp     loc_18005D900
0x18005da3f  mov     rcx, [rbp+arg_10]
0x18005da43  xor     edx, edx
0x18005da45  mov     rax, [rcx]
0x18005da48  mov     rax, [rax+20h]
0x18005da4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da51  mov     ebx, eax
0x18005da53  test    eax, eax
0x18005da55  jns     short loc_18005DAD6
0x18005da57  mov     eax, cs:CallbackContext
0x18005da5d  cmp     eax, 2
0x18005da60  jbe     loc_18005DDA5
0x18005da66  lea     rax, aFailedToStartT_6; "Failed to start the STA thread"
0x18005da6d  mov     dword ptr [rbp+arg_0], 1BAh
0x18005da74  mov     [rbp+var_8], rax
0x18005da78  lea     rsi, aCreatethreads; "CreateThreads"
0x18005da7f  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005da86  mov     [rbp+var_10], rsi
0x18005da8a  mov     [rbp+var_18], rax
0x18005da8e  lea     rdx, byte_1801BDC61
0x18005da95  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005da9c  mov     [rbp+var_20], rax
0x18005daa0  lea     rax, [rbp+var_8]
0x18005daa4  mov     [rsp+70h+var_28], rax
0x18005daa9  lea     rax, [rbp+var_10]
0x18005daad  mov     [rsp+70h+var_30], rax
0x18005dab2  lea     rax, [rbp+arg_0]
0x18005dab6  mov     [rsp+70h+var_38], rax
0x18005dabb  lea     rax, [rbp+var_18]
0x18005dabf  mov     [rsp+70h+var_40], rax
0x18005dac4  lea     rax, [rbp+arg_8]
0x18005dac8  mov     [rsp+70h+var_48], rax
0x18005dacd  lea     rax, [rbp+var_20]
0x18005dad1  jmp     loc_18005D900
0x18005dad6  mov     rcx, [r14+40h]
0x18005dada  lea     r9, [rbp+arg_18]
0x18005dade  mov     r8, r14
0x18005dae1  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x18005dae8  mov     rax, [rcx]
0x18005daeb  mov     rax, [rax+38h]
0x18005daef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daf4  mov     ebx, eax
0x18005daf6  test    eax, eax
0x18005daf8  jns     short loc_18005DB79
0x18005dafa  mov     eax, cs:CallbackContext
0x18005db00  cmp     eax, 2
0x18005db03  jbe     loc_18005DDA5
0x18005db09  lea     rax, aFailedToCreate_101; "Failed to create the Worker thread"
0x18005db10  mov     dword ptr [rbp+arg_0], 1C5h
0x18005db17  mov     [rbp+var_8], rax
0x18005db1b  lea     rsi, aCreatethreads; "CreateThreads"
0x18005db22  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005db29  mov     [rbp+var_10], rsi
0x18005db2d  mov     [rbp+var_18], rax
0x18005db31  lea     rdx, qword_1801BDCB0
0x18005db38  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005db3f  mov     [rbp+var_20], rax
0x18005db43  lea     rax, [rbp+var_8]
0x18005db47  mov     [rsp+70h+var_28], rax
0x18005db4c  lea     rax, [rbp+var_10]
0x18005db50  mov     [rsp+70h+var_30], rax
0x18005db55  lea     rax, [rbp+arg_0]
0x18005db59  mov     [rsp+70h+var_38], rax
0x18005db5e  lea     rax, [rbp+var_18]
0x18005db62  mov     [rsp+70h+var_40], rax
0x18005db67  lea     rax, [rbp+arg_8]
0x18005db6b  mov     [rsp+70h+var_48], rax
0x18005db70  lea     rax, [rbp+var_20]
0x18005db74  jmp     loc_18005D900
0x18005db79  mov     rcx, [rbp+arg_18]
0x18005db7d  xor     edx, edx
0x18005db7f  mov     rax, [rcx]
0x18005db82  mov     rax, [rax+20h]
0x18005db86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db8b  mov     ebx, eax
0x18005db8d  test    eax, eax
0x18005db8f  jns     short loc_18005DC10
0x18005db91  mov     eax, cs:CallbackContext
0x18005db97  cmp     eax, 2
0x18005db9a  jbe     loc_18005DDA5
0x18005dba0  lea     rax, aFailedToStartT_8; "Failed to start the Worker thread"
0x18005dba7  mov     dword ptr [rbp+arg_0], 1C8h
0x18005dbae  mov     [rbp+var_8], rax
0x18005dbb2  lea     rsi, aCreatethreads; "CreateThreads"
0x18005dbb9  lea     rax, aOnecoreTermsrv_61; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18005dbc0  mov     [rbp+var_10], rsi
0x18005dbc4  mov     [rbp+var_18], rax
0x18005dbc8  lea     rdx, byte_1801BDBD5
0x18005dbcf  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005dbd6  mov     [rbp+var_20], rax
0x18005dbda  lea     rax, [rbp+var_8]
0x18005dbde  mov     [rsp+70h+var_28], rax
0x18005dbe3  lea     rax, [rbp+var_10]
0x18005dbe7  mov     [rsp+70h+var_30], rax
0x18005dbec  lea     rax, [rbp+arg_0]
0x18005dbf0  mov     [rsp+70h+var_38], rax
0x18005dbf5  lea     rax, [rbp+var_18]
0x18005dbf9  mov     [rsp+70h+var_40], rax
0x18005dbfe  lea     rax, [rbp+arg_8]
0x18005dc02  mov     [rsp+70h+var_48], rax
0x18005dc07  lea     rax, [rbp+var_20]
0x18005dc0b  jmp     loc_18005D900
0x18005dc10  lea     rdi, [r14+48h]
0x18005dc14  mov     rax, [rdi]
0x18005dc17  cmp     [rbp+arg_10], rax
0x18005dc1b  jz      short loc_18005DC34
0x18005dc1d  mov     rcx, rdi; void *
0x18005dc20  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18005dc25  mov     rax, [rbp+arg_10]
0x18005dc29  mov     rcx, rdi
0x18005dc2c  mov     [rdi], rax
0x18005dc2f  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18005dc34  lea     r15, [r14+50h]
0x18005dc38  mov     rax, [r15]
0x18005dc3b  cmp     [rbp+arg_18], rax
0x18005dc3f  jz      short loc_18005DC58
0x18005dc41  mov     rcx, r15; void *
0x18005dc44  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18005dc49  mov     rax, [rbp+arg_18]
0x18005dc4d  mov     rcx, r15
0x18005dc50  mov     [r15], rax
0x18005dc53  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18005dc58  mov     rdi, [rdi]
0x18005dc5b  mov     rcx, rdi
0x18005dc5e  mov     rbx, [rdi]
0x18005dc61  mov     rax, [rbx+18h]
0x18005dc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc6a  mov     r9d, eax
0x18005dc6d  lea     r8, ?STAThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadRecoveredWatchdogReport(void *)
0x18005dc74  mov     rax, [rbx+0C8h]
0x18005dc7b  lea     rdx, ?STAThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadStuckWatchdogReport(void *)
0x18005dc82  mov     dword ptr [rsp+70h+var_48], 0
0x18005dc8a  mov     rcx, rdi
0x18005dc8d  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x18005dc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc9a  lea     rsi, aCreatethreads; "CreateThreads"
0x18005dca1  lea     r13, aHresultFailedB; "HResult failed but continue"
0x18005dca8  test    eax, eax
0x18005dcaa  jns     short loc_18005DCFD
0x18005dcac  mov     ecx, cs:CallbackContext
0x18005dcb2  cmp     ecx, 3
0x18005dcb5  jbe     short loc_18005DCFD
0x18005dcb7  mov     dword ptr [rbp+arg_0], eax
0x18005dcba  lea     rdx, dword_1801BDC24
0x18005dcc1  lea     rax, aFailedToSetSta; "Failed to set STA thread watchdog"
0x18005dcc8  mov     [rbp+arg_8], rsi
0x18005dccc  mov     [rbp+var_8], rax
0x18005dcd0  lea     rax, [rbp+arg_8]
0x18005dcd4  mov     [rsp+70h+var_38], rax
0x18005dcd9  lea     rax, [rbp+arg_0]
0x18005dcdd  mov     [rsp+70h+var_40], rax
0x18005dce2  lea     rax, [rbp+var_8]
0x18005dce6  mov     [rsp+70h+var_48], rax
0x18005dceb  lea     rax, [rbp+var_10]
0x18005dcef  mov     [rsp+70h+var_50], rax
0x18005dcf4  mov     [rbp+var_10], r13
0x18005dcf8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005dcfd  mov     rdi, [r15]
0x18005dd00  mov     rcx, rdi
0x18005dd03  mov     rbx, [rdi]
0x18005dd06  mov     rax, [rbx+18h]
0x18005dd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd0f  mov     r9d, eax
0x18005dd12  lea     r8, ?WorkerThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadRecoveredWatchdogReport(void *)
0x18005dd19  mov     rax, [rbx+0C8h]
0x18005dd20  lea     rdx, ?WorkerThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadStuckWatchdogReport(void *)
0x18005dd27  mov     dword ptr [rsp+70h+var_48], 0
0x18005dd2f  mov     rcx, rdi
0x18005dd32  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x18005dd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd3f  mov     ebx, eax
  ... truncated ...
```
