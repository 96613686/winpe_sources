# CRDPENCPlatformContext::CreateThreads(void)

- ea: `0x140084804`
- end: `0x140084e13`
- name: `?CreateThreads@CRDPENCPlatformContext@@IEAAJXZ`
- size: `1551`
- prototype: `__int64 __fastcall(CRDPENCPlatformContext *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140086f68`

## callees

- `0x140001010`
- `0x1400025a8`
- `0x1400026b0`
- `0x14000dcac`
- `0x14003e0b4`
- `0x140084804`
- `0x140114010`

## string_xrefs

- `0x1400848c4`: `CreateThreads`
- `0x14008496a`: `CreateThreads`
- `0x1400849fe`: `CreateThreads`
- `0x140084a95`: `CreateThreads`
- `0x140084b38`: `CreateThreads`
- `0x140084bcf`: `CreateThreads`
- `0x140084cb7`: `CreateThreads`
- `0x140084958`: `ITSThread::BindThread failed`
- `0x1400849ec`: `Failed to create the STA thread`
- `0x140084a83`: `Failed to start the STA thread`
- `0x140084846`: `STA threads already created`
- `0x1400848b2`: `ITSPlatform::CreateThread failed`
- `0x140084b26`: `Failed to create the Worker thread`
- `0x140084bbd`: `Failed to start the Worker thread`
- `0x140084cde`: `Failed to set STA thread watchdog`
- `0x140084d6d`: `Failed to set Worker thread watchdog`

## pseudocode

```c
__int64 __fastcall CRDPENCPlatformContext::CreateThreads(CRDPENCPlatformContext *this, __int64 a2, int a3, int a4)
{
  bool v4; // zf
  int v6; // ebx
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(__int64, void (__fastcall *)(void *), CRDPENCPlatformContext *, __int64 **); // rax
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  __int16 *v12; // rdx
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
    if ( (unsigned int)dword_140152118 > 3 )
    {
      v36 = "STA threads already created";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140152118,
        (unsigned int)&byte_140142BC7,
        a3,
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
      v11 = dword_140152118;
      if ( (unsigned int)dword_140152118 <= 2 )
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
      v12 = (__int16 *)&dword_140142D14;
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
      if ( (unsigned int)dword_140152118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 428;
      v35 = "ITSThread::BindThread failed";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = (__int16 *)byte_140142CC5;
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
      if ( (unsigned int)dword_140152118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 439;
      v35 = "Failed to create the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = &word_140142C76;
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
      if ( (unsigned int)dword_140152118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 442;
      v35 = "Failed to start the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = (__int16 *)&dword_140142A84;
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 453;
    v35 = "Failed to create the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = (__int16 *)byte_140142A35;
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 456;
    v35 = "Failed to start the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = &word_1401429E6;
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
  if ( v19 < 0 && (unsigned int)dword_140152118 > 3 )
  {
    LODWORD(v36) = v19;
    v37 = "CreateThreads";
    v35 = "Failed to set STA thread watchdog";
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_140152118,
      (unsigned int)byte_1401429A9,
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
  if ( v6 < 0 && (unsigned int)dword_140152118 > 3 )
  {
    v37 = "CreateThreads";
    v35 = "Failed to set Worker thread watchdog";
    LODWORD(v36) = v6;
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v25,
      (unsigned int)word_140142B8A,
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
0x140084804  push    rbp
0x140084806  push    rbx
0x140084807  push    rsi
0x140084808  push    rdi
0x140084809  push    r13
0x14008480b  push    r14
0x14008480d  push    r15
0x14008480f  mov     rbp, rsp
0x140084812  sub     rsp, 70h
0x140084816  cmp     dword ptr [rcx+0A0h], 0
0x14008481d  mov     r14, rcx
0x140084820  mov     [rbp+arg_10], 0
0x140084828  mov     [rbp+arg_18], 0
0x140084830  jnz     short loc_140084872
0x140084832  mov     eax, cs:dword_140152118
0x140084838  mov     ebx, 1
0x14008483d  cmp     eax, 3
0x140084840  jbe     loc_140084DF0
0x140084846  lea     rax, aStaThreadsAlre; "STA threads already created"
0x14008484d  mov     [rbp+arg_0], rax
0x140084851  lea     rdx, byte_140142BC7
0x140084858  lea     rax, [rbp+arg_0]
0x14008485c  lea     rcx, dword_140152118
0x140084863  mov     [rsp+70h+var_50], rax
0x140084868  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14008486d  jmp     loc_140084DF0
0x140084872  cmp     dword ptr [r14+0B8h], 0
0x14008487a  lea     r9, [rbp+arg_10]
0x14008487e  mov     rcx, [rcx+40h]
0x140084882  mov     rax, [rcx]
0x140084885  mov     rax, [rax+38h]
0x140084889  jz      loc_1400849C8
0x14008488f  xor     r8d, r8d
0x140084892  xor     edx, edx
0x140084894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084899  mov     ebx, eax
0x14008489b  test    eax, eax
0x14008489d  jns     loc_14008492F
0x1400848a3  mov     ecx, cs:dword_140152118
0x1400848a9  cmp     ecx, 2
0x1400848ac  jbe     loc_140084DC2
0x1400848b2  lea     rax, aItsplatformCre; "ITSPlatform::CreateThread failed"
0x1400848b9  mov     dword ptr [rbp+arg_0], 1A9h
0x1400848c0  mov     [rbp+var_20], rax
0x1400848c4  lea     rsi, aCreatethreads; "CreateThreads"
0x1400848cb  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400848d2  mov     [rbp+var_18], rsi
0x1400848d6  mov     [rbp+var_10], rax
0x1400848da  lea     rdx, dword_140142D14
0x1400848e1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1400848e8  mov     [rbp+var_8], rax
0x1400848ec  lea     rax, [rbp+var_20]
0x1400848f0  mov     [rsp+70h+var_28], rax
0x1400848f5  lea     rax, [rbp+var_18]
0x1400848f9  mov     [rsp+70h+var_30], rax
0x1400848fe  lea     rax, [rbp+arg_0]
0x140084902  mov     [rsp+70h+var_38], rax
0x140084907  lea     rax, [rbp+var_10]
0x14008490b  mov     [rsp+70h+var_40], rax
0x140084910  lea     rax, [rbp+arg_8]
0x140084914  mov     [rsp+70h+var_48], rax
0x140084919  lea     rax, [rbp+var_8]
0x14008491d  mov     [rsp+70h+var_50], rax
0x140084922  mov     dword ptr [rbp+arg_8], ebx
0x140084925  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14008492a  jmp     loc_140084DC2
0x14008492f  mov     rcx, [rbp+arg_10]
0x140084933  mov     rax, [rcx]
0x140084936  mov     rax, [rax+28h]
0x14008493a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008493f  mov     ebx, eax
0x140084941  test    eax, eax
0x140084943  jns     loc_140084AF3
0x140084949  mov     eax, cs:dword_140152118
0x14008494f  cmp     eax, 2
0x140084952  jbe     loc_140084DC2
0x140084958  lea     rax, aItsthreadBindt; "ITSThread::BindThread failed"
0x14008495f  mov     dword ptr [rbp+arg_0], 1ACh
0x140084966  mov     [rbp+var_8], rax
0x14008496a  lea     rsi, aCreatethreads; "CreateThreads"
0x140084971  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140084978  mov     [rbp+var_10], rsi
0x14008497c  mov     [rbp+var_18], rax
0x140084980  lea     rdx, byte_140142CC5
0x140084987  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14008498e  mov     [rbp+var_20], rax
0x140084992  lea     rax, [rbp+var_8]
0x140084996  mov     [rsp+70h+var_28], rax
0x14008499b  lea     rax, [rbp+var_10]
0x14008499f  mov     [rsp+70h+var_30], rax
0x1400849a4  lea     rax, [rbp+arg_0]
0x1400849a8  mov     [rsp+70h+var_38], rax
0x1400849ad  lea     rax, [rbp+var_18]
0x1400849b1  mov     [rsp+70h+var_40], rax
0x1400849b6  lea     rax, [rbp+arg_8]
0x1400849ba  mov     [rsp+70h+var_48], rax
0x1400849bf  lea     rax, [rbp+var_20]
0x1400849c3  jmp     loc_14008491D
0x1400849c8  mov     r8, r14
0x1400849cb  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x1400849d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400849d7  mov     ebx, eax
0x1400849d9  test    eax, eax
0x1400849db  jns     short loc_140084A5C
0x1400849dd  mov     eax, cs:dword_140152118
0x1400849e3  cmp     eax, 2
0x1400849e6  jbe     loc_140084DC2
0x1400849ec  lea     rax, aFailedToCreate_35; "Failed to create the STA thread"
0x1400849f3  mov     dword ptr [rbp+arg_0], 1B7h
0x1400849fa  mov     [rbp+var_8], rax
0x1400849fe  lea     rsi, aCreatethreads; "CreateThreads"
0x140084a05  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140084a0c  mov     [rbp+var_10], rsi
0x140084a10  mov     [rbp+var_18], rax
0x140084a14  lea     rdx, word_140142C76
0x140084a1b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140084a22  mov     [rbp+var_20], rax
0x140084a26  lea     rax, [rbp+var_8]
0x140084a2a  mov     [rsp+70h+var_28], rax
0x140084a2f  lea     rax, [rbp+var_10]
0x140084a33  mov     [rsp+70h+var_30], rax
0x140084a38  lea     rax, [rbp+arg_0]
0x140084a3c  mov     [rsp+70h+var_38], rax
0x140084a41  lea     rax, [rbp+var_18]
0x140084a45  mov     [rsp+70h+var_40], rax
0x140084a4a  lea     rax, [rbp+arg_8]
0x140084a4e  mov     [rsp+70h+var_48], rax
0x140084a53  lea     rax, [rbp+var_20]
0x140084a57  jmp     loc_14008491D
0x140084a5c  mov     rcx, [rbp+arg_10]
0x140084a60  xor     edx, edx
0x140084a62  mov     rax, [rcx]
0x140084a65  mov     rax, [rax+20h]
0x140084a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084a6e  mov     ebx, eax
0x140084a70  test    eax, eax
0x140084a72  jns     short loc_140084AF3
0x140084a74  mov     eax, cs:dword_140152118
0x140084a7a  cmp     eax, 2
0x140084a7d  jbe     loc_140084DC2
0x140084a83  lea     rax, aFailedToStartT_2; "Failed to start the STA thread"
0x140084a8a  mov     dword ptr [rbp+arg_0], 1BAh
0x140084a91  mov     [rbp+var_8], rax
0x140084a95  lea     rsi, aCreatethreads; "CreateThreads"
0x140084a9c  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140084aa3  mov     [rbp+var_10], rsi
0x140084aa7  mov     [rbp+var_18], rax
0x140084aab  lea     rdx, dword_140142A84
0x140084ab2  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140084ab9  mov     [rbp+var_20], rax
0x140084abd  lea     rax, [rbp+var_8]
0x140084ac1  mov     [rsp+70h+var_28], rax
0x140084ac6  lea     rax, [rbp+var_10]
0x140084aca  mov     [rsp+70h+var_30], rax
0x140084acf  lea     rax, [rbp+arg_0]
0x140084ad3  mov     [rsp+70h+var_38], rax
0x140084ad8  lea     rax, [rbp+var_18]
0x140084adc  mov     [rsp+70h+var_40], rax
0x140084ae1  lea     rax, [rbp+arg_8]
0x140084ae5  mov     [rsp+70h+var_48], rax
0x140084aea  lea     rax, [rbp+var_20]
0x140084aee  jmp     loc_14008491D
0x140084af3  mov     rcx, [r14+40h]
0x140084af7  lea     r9, [rbp+arg_18]
0x140084afb  mov     r8, r14
0x140084afe  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x140084b05  mov     rax, [rcx]
0x140084b08  mov     rax, [rax+38h]
0x140084b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084b11  mov     ebx, eax
0x140084b13  test    eax, eax
0x140084b15  jns     short loc_140084B96
0x140084b17  mov     eax, cs:dword_140152118
0x140084b1d  cmp     eax, 2
0x140084b20  jbe     loc_140084DC2
0x140084b26  lea     rax, aFailedToCreate_60; "Failed to create the Worker thread"
0x140084b2d  mov     dword ptr [rbp+arg_0], 1C5h
0x140084b34  mov     [rbp+var_8], rax
0x140084b38  lea     rsi, aCreatethreads; "CreateThreads"
0x140084b3f  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140084b46  mov     [rbp+var_10], rsi
0x140084b4a  mov     [rbp+var_18], rax
0x140084b4e  lea     rdx, byte_140142A35
0x140084b55  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140084b5c  mov     [rbp+var_20], rax
0x140084b60  lea     rax, [rbp+var_8]
0x140084b64  mov     [rsp+70h+var_28], rax
0x140084b69  lea     rax, [rbp+var_10]
0x140084b6d  mov     [rsp+70h+var_30], rax
0x140084b72  lea     rax, [rbp+arg_0]
0x140084b76  mov     [rsp+70h+var_38], rax
0x140084b7b  lea     rax, [rbp+var_18]
0x140084b7f  mov     [rsp+70h+var_40], rax
0x140084b84  lea     rax, [rbp+arg_8]
0x140084b88  mov     [rsp+70h+var_48], rax
0x140084b8d  lea     rax, [rbp+var_20]
0x140084b91  jmp     loc_14008491D
0x140084b96  mov     rcx, [rbp+arg_18]
0x140084b9a  xor     edx, edx
0x140084b9c  mov     rax, [rcx]
0x140084b9f  mov     rax, [rax+20h]
0x140084ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084ba8  mov     ebx, eax
0x140084baa  test    eax, eax
0x140084bac  jns     short loc_140084C2D
0x140084bae  mov     eax, cs:dword_140152118
0x140084bb4  cmp     eax, 2
0x140084bb7  jbe     loc_140084DC2
0x140084bbd  lea     rax, aFailedToStartT_3; "Failed to start the Worker thread"
0x140084bc4  mov     dword ptr [rbp+arg_0], 1C8h
0x140084bcb  mov     [rbp+var_8], rax
0x140084bcf  lea     rsi, aCreatethreads; "CreateThreads"
0x140084bd6  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140084bdd  mov     [rbp+var_10], rsi
0x140084be1  mov     [rbp+var_18], rax
0x140084be5  lea     rdx, word_1401429E6
0x140084bec  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140084bf3  mov     [rbp+var_20], rax
0x140084bf7  lea     rax, [rbp+var_8]
0x140084bfb  mov     [rsp+70h+var_28], rax
0x140084c00  lea     rax, [rbp+var_10]
0x140084c04  mov     [rsp+70h+var_30], rax
0x140084c09  lea     rax, [rbp+arg_0]
0x140084c0d  mov     [rsp+70h+var_38], rax
0x140084c12  lea     rax, [rbp+var_18]
0x140084c16  mov     [rsp+70h+var_40], rax
0x140084c1b  lea     rax, [rbp+arg_8]
0x140084c1f  mov     [rsp+70h+var_48], rax
0x140084c24  lea     rax, [rbp+var_20]
0x140084c28  jmp     loc_14008491D
0x140084c2d  lea     rdi, [r14+48h]
0x140084c31  mov     rax, [rdi]
0x140084c34  cmp     [rbp+arg_10], rax
0x140084c38  jz      short loc_140084C51
0x140084c3a  mov     rcx, rdi
0x140084c3d  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140084c42  mov     rax, [rbp+arg_10]
0x140084c46  mov     rcx, rdi
0x140084c49  mov     [rdi], rax
0x140084c4c  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140084c51  lea     r15, [r14+50h]
0x140084c55  mov     rax, [r15]
0x140084c58  cmp     [rbp+arg_18], rax
0x140084c5c  jz      short loc_140084C75
0x140084c5e  mov     rcx, r15
0x140084c61  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140084c66  mov     rax, [rbp+arg_18]
0x140084c6a  mov     rcx, r15
0x140084c6d  mov     [r15], rax
0x140084c70  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140084c75  mov     rdi, [rdi]
0x140084c78  mov     rcx, rdi
0x140084c7b  mov     rbx, [rdi]
0x140084c7e  mov     rax, [rbx+18h]
0x140084c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084c87  mov     r9d, eax
0x140084c8a  lea     r8, ?STAThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadRecoveredWatchdogReport(void *)
0x140084c91  mov     rax, [rbx+0C8h]
0x140084c98  lea     rdx, ?STAThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadStuckWatchdogReport(void *)
0x140084c9f  mov     dword ptr [rsp+70h+var_48], 0
0x140084ca7  mov     rcx, rdi
0x140084caa  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x140084cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084cb7  lea     rsi, aCreatethreads; "CreateThreads"
0x140084cbe  lea     r13, aHresultFailedB; "HResult failed but continue"
0x140084cc5  test    eax, eax
0x140084cc7  jns     short loc_140084D1A
0x140084cc9  mov     ecx, cs:dword_140152118
0x140084ccf  cmp     ecx, 3
0x140084cd2  jbe     short loc_140084D1A
0x140084cd4  mov     dword ptr [rbp+arg_0], eax
0x140084cd7  lea     rdx, byte_1401429A9
0x140084cde  lea     rax, aFailedToSetSta; "Failed to set STA thread watchdog"
0x140084ce5  mov     [rbp+arg_8], rsi
0x140084ce9  mov     [rbp+var_8], rax
0x140084ced  lea     rax, [rbp+arg_8]
0x140084cf1  mov     [rsp+70h+var_38], rax
0x140084cf6  lea     rax, [rbp+arg_0]
0x140084cfa  mov     [rsp+70h+var_40], rax
0x140084cff  lea     rax, [rbp+var_8]
0x140084d03  mov     [rsp+70h+var_48], rax
0x140084d08  lea     rax, [rbp+var_10]
0x140084d0c  mov     [rsp+70h+var_50], rax
0x140084d11  mov     [rbp+var_10], r13
0x140084d15  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140084d1a  mov     rdi, [r15]
0x140084d1d  mov     rcx, rdi
0x140084d20  mov     rbx, [rdi]
0x140084d23  mov     rax, [rbx+18h]
0x140084d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084d2c  mov     r9d, eax
0x140084d2f  lea     r8, ?WorkerThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadRecoveredWatchdogReport(void *)
0x140084d36  mov     rax, [rbx+0C8h]
0x140084d3d  lea     rdx, ?WorkerThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadStuckWatchdogReport(void *)
0x140084d44  mov     dword ptr [rsp+70h+var_48], 0
0x140084d4c  mov     rcx, rdi
0x140084d4f  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x140084d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084d5c  mov     ebx, eax
0x140084d5e  test    eax, eax
  ... truncated ...
```
