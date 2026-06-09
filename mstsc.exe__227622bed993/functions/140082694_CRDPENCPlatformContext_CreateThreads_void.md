# CRDPENCPlatformContext::CreateThreads(void)

- ea: `0x140082694`
- end: `0x140082ca3`
- name: `?CreateThreads@CRDPENCPlatformContext@@IEAAJXZ`
- size: `1551`
- prototype: `__int64 __fastcall(CRDPENCPlatformContext *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140084df8`

## callees

- `0x140001010`
- `0x1400025a8`
- `0x1400026b0`
- `0x14000dcac`
- `0x14003c0f0`
- `0x140082694`
- `0x140112010`

## string_xrefs

- `0x140082754`: `CreateThreads`
- `0x1400827fa`: `CreateThreads`
- `0x14008288e`: `CreateThreads`
- `0x140082925`: `CreateThreads`
- `0x1400829c8`: `CreateThreads`
- `0x140082a5f`: `CreateThreads`
- `0x140082b47`: `CreateThreads`
- `0x1400827e8`: `ITSThread::BindThread failed`
- `0x14008287c`: `Failed to create the STA thread`
- `0x140082913`: `Failed to start the STA thread`
- `0x1400826d6`: `STA threads already created`
- `0x140082742`: `ITSPlatform::CreateThread failed`
- `0x1400829b6`: `Failed to create the Worker thread`
- `0x140082a4d`: `Failed to start the Worker thread`
- `0x140082b6e`: `Failed to set STA thread watchdog`
- `0x140082bfd`: `Failed to set Worker thread watchdog`

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
    if ( (unsigned int)dword_140150118 > 3 )
    {
      v36 = "STA threads already created";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140150118,
        (unsigned int)&byte_140140A8F,
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
      v11 = dword_140150118;
      if ( (unsigned int)dword_140150118 <= 2 )
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
      v12 = (__int16 *)qword_140140A40;
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
      if ( (unsigned int)dword_140150118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 428;
      v35 = "ITSThread::BindThread failed";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = (__int16 *)&dword_140140BDC;
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
      if ( (unsigned int)dword_140150118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 439;
      v35 = "Failed to create the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = (__int16 *)byte_140140B8D;
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
      if ( (unsigned int)dword_140150118 <= 2 )
        goto LABEL_35;
      LODWORD(v36) = 442;
      v35 = "Failed to start the STA thread";
      v34 = "CreateThreads";
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
      v12 = &word_140140B3E;
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
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 453;
    v35 = "Failed to create the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = (__int16 *)byte_1401408FD;
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
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_35;
    LODWORD(v36) = 456;
    v35 = "Failed to start the Worker thread";
    v34 = "CreateThreads";
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\encctxinfoimpl.cpp";
    v12 = &word_1401408AE;
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
  if ( v19 < 0 && (unsigned int)dword_140150118 > 3 )
  {
    LODWORD(v36) = v19;
    v37 = "CreateThreads";
    v35 = "Failed to set STA thread watchdog";
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_140150118,
      (unsigned int)byte_140140871,
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
  if ( v6 < 0 && (unsigned int)dword_140150118 > 3 )
  {
    v37 = "CreateThreads";
    v35 = "Failed to set Worker thread watchdog";
    LODWORD(v36) = v6;
    v34 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v25,
      (unsigned int)byte_140140A03,
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
0x140082694  push    rbp
0x140082696  push    rbx
0x140082697  push    rsi
0x140082698  push    rdi
0x140082699  push    r13
0x14008269b  push    r14
0x14008269d  push    r15
0x14008269f  mov     rbp, rsp
0x1400826a2  sub     rsp, 70h
0x1400826a6  cmp     dword ptr [rcx+0A0h], 0
0x1400826ad  mov     r14, rcx
0x1400826b0  mov     [rbp+arg_10], 0
0x1400826b8  mov     [rbp+arg_18], 0
0x1400826c0  jnz     short loc_140082702
0x1400826c2  mov     eax, cs:dword_140150118
0x1400826c8  mov     ebx, 1
0x1400826cd  cmp     eax, 3
0x1400826d0  jbe     loc_140082C80
0x1400826d6  lea     rax, aStaThreadsAlre; "STA threads already created"
0x1400826dd  mov     [rbp+arg_0], rax
0x1400826e1  lea     rdx, byte_140140A8F
0x1400826e8  lea     rax, [rbp+arg_0]
0x1400826ec  lea     rcx, dword_140150118
0x1400826f3  mov     [rsp+70h+var_50], rax
0x1400826f8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400826fd  jmp     loc_140082C80
0x140082702  cmp     dword ptr [r14+0B8h], 0
0x14008270a  lea     r9, [rbp+arg_10]
0x14008270e  mov     rcx, [rcx+40h]
0x140082712  mov     rax, [rcx]
0x140082715  mov     rax, [rax+38h]
0x140082719  jz      loc_140082858
0x14008271f  xor     r8d, r8d
0x140082722  xor     edx, edx
0x140082724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082729  mov     ebx, eax
0x14008272b  test    eax, eax
0x14008272d  jns     loc_1400827BF
0x140082733  mov     ecx, cs:dword_140150118
0x140082739  cmp     ecx, 2
0x14008273c  jbe     loc_140082C52
0x140082742  lea     rax, aItsplatformCre; "ITSPlatform::CreateThread failed"
0x140082749  mov     dword ptr [rbp+arg_0], 1A9h
0x140082750  mov     [rbp+var_20], rax
0x140082754  lea     rsi, aCreatethreads; "CreateThreads"
0x14008275b  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140082762  mov     [rbp+var_18], rsi
0x140082766  mov     [rbp+var_10], rax
0x14008276a  lea     rdx, qword_140140A40
0x140082771  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140082778  mov     [rbp+var_8], rax
0x14008277c  lea     rax, [rbp+var_20]
0x140082780  mov     [rsp+70h+var_28], rax
0x140082785  lea     rax, [rbp+var_18]
0x140082789  mov     [rsp+70h+var_30], rax
0x14008278e  lea     rax, [rbp+arg_0]
0x140082792  mov     [rsp+70h+var_38], rax
0x140082797  lea     rax, [rbp+var_10]
0x14008279b  mov     [rsp+70h+var_40], rax
0x1400827a0  lea     rax, [rbp+arg_8]
0x1400827a4  mov     [rsp+70h+var_48], rax
0x1400827a9  lea     rax, [rbp+var_8]
0x1400827ad  mov     [rsp+70h+var_50], rax
0x1400827b2  mov     dword ptr [rbp+arg_8], ebx
0x1400827b5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1400827ba  jmp     loc_140082C52
0x1400827bf  mov     rcx, [rbp+arg_10]
0x1400827c3  mov     rax, [rcx]
0x1400827c6  mov     rax, [rax+28h]
0x1400827ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400827cf  mov     ebx, eax
0x1400827d1  test    eax, eax
0x1400827d3  jns     loc_140082983
0x1400827d9  mov     eax, cs:dword_140150118
0x1400827df  cmp     eax, 2
0x1400827e2  jbe     loc_140082C52
0x1400827e8  lea     rax, aItsthreadBindt; "ITSThread::BindThread failed"
0x1400827ef  mov     dword ptr [rbp+arg_0], 1ACh
0x1400827f6  mov     [rbp+var_8], rax
0x1400827fa  lea     rsi, aCreatethreads; "CreateThreads"
0x140082801  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140082808  mov     [rbp+var_10], rsi
0x14008280c  mov     [rbp+var_18], rax
0x140082810  lea     rdx, dword_140140BDC
0x140082817  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14008281e  mov     [rbp+var_20], rax
0x140082822  lea     rax, [rbp+var_8]
0x140082826  mov     [rsp+70h+var_28], rax
0x14008282b  lea     rax, [rbp+var_10]
0x14008282f  mov     [rsp+70h+var_30], rax
0x140082834  lea     rax, [rbp+arg_0]
0x140082838  mov     [rsp+70h+var_38], rax
0x14008283d  lea     rax, [rbp+var_18]
0x140082841  mov     [rsp+70h+var_40], rax
0x140082846  lea     rax, [rbp+arg_8]
0x14008284a  mov     [rsp+70h+var_48], rax
0x14008284f  lea     rax, [rbp+var_20]
0x140082853  jmp     loc_1400827AD
0x140082858  mov     r8, r14
0x14008285b  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x140082862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082867  mov     ebx, eax
0x140082869  test    eax, eax
0x14008286b  jns     short loc_1400828EC
0x14008286d  mov     eax, cs:dword_140150118
0x140082873  cmp     eax, 2
0x140082876  jbe     loc_140082C52
0x14008287c  lea     rax, aFailedToCreate_35; "Failed to create the STA thread"
0x140082883  mov     dword ptr [rbp+arg_0], 1B7h
0x14008288a  mov     [rbp+var_8], rax
0x14008288e  lea     rsi, aCreatethreads; "CreateThreads"
0x140082895  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14008289c  mov     [rbp+var_10], rsi
0x1400828a0  mov     [rbp+var_18], rax
0x1400828a4  lea     rdx, byte_140140B8D
0x1400828ab  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1400828b2  mov     [rbp+var_20], rax
0x1400828b6  lea     rax, [rbp+var_8]
0x1400828ba  mov     [rsp+70h+var_28], rax
0x1400828bf  lea     rax, [rbp+var_10]
0x1400828c3  mov     [rsp+70h+var_30], rax
0x1400828c8  lea     rax, [rbp+arg_0]
0x1400828cc  mov     [rsp+70h+var_38], rax
0x1400828d1  lea     rax, [rbp+var_18]
0x1400828d5  mov     [rsp+70h+var_40], rax
0x1400828da  lea     rax, [rbp+arg_8]
0x1400828de  mov     [rsp+70h+var_48], rax
0x1400828e3  lea     rax, [rbp+var_20]
0x1400828e7  jmp     loc_1400827AD
0x1400828ec  mov     rcx, [rbp+arg_10]
0x1400828f0  xor     edx, edx
0x1400828f2  mov     rax, [rcx]
0x1400828f5  mov     rax, [rax+20h]
0x1400828f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400828fe  mov     ebx, eax
0x140082900  test    eax, eax
0x140082902  jns     short loc_140082983
0x140082904  mov     eax, cs:dword_140150118
0x14008290a  cmp     eax, 2
0x14008290d  jbe     loc_140082C52
0x140082913  lea     rax, aFailedToStartT_2; "Failed to start the STA thread"
0x14008291a  mov     dword ptr [rbp+arg_0], 1BAh
0x140082921  mov     [rbp+var_8], rax
0x140082925  lea     rsi, aCreatethreads; "CreateThreads"
0x14008292c  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140082933  mov     [rbp+var_10], rsi
0x140082937  mov     [rbp+var_18], rax
0x14008293b  lea     rdx, word_140140B3E
0x140082942  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140082949  mov     [rbp+var_20], rax
0x14008294d  lea     rax, [rbp+var_8]
0x140082951  mov     [rsp+70h+var_28], rax
0x140082956  lea     rax, [rbp+var_10]
0x14008295a  mov     [rsp+70h+var_30], rax
0x14008295f  lea     rax, [rbp+arg_0]
0x140082963  mov     [rsp+70h+var_38], rax
0x140082968  lea     rax, [rbp+var_18]
0x14008296c  mov     [rsp+70h+var_40], rax
0x140082971  lea     rax, [rbp+arg_8]
0x140082975  mov     [rsp+70h+var_48], rax
0x14008297a  lea     rax, [rbp+var_20]
0x14008297e  jmp     loc_1400827AD
0x140082983  mov     rcx, [r14+40h]
0x140082987  lea     r9, [rbp+arg_18]
0x14008298b  mov     r8, r14
0x14008298e  lea     rdx, ?STATIC_STAThreadProc@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STATIC_STAThreadProc(void *)
0x140082995  mov     rax, [rcx]
0x140082998  mov     rax, [rax+38h]
0x14008299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400829a1  mov     ebx, eax
0x1400829a3  test    eax, eax
0x1400829a5  jns     short loc_140082A26
0x1400829a7  mov     eax, cs:dword_140150118
0x1400829ad  cmp     eax, 2
0x1400829b0  jbe     loc_140082C52
0x1400829b6  lea     rax, aFailedToCreate_60; "Failed to create the Worker thread"
0x1400829bd  mov     dword ptr [rbp+arg_0], 1C5h
0x1400829c4  mov     [rbp+var_8], rax
0x1400829c8  lea     rsi, aCreatethreads; "CreateThreads"
0x1400829cf  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400829d6  mov     [rbp+var_10], rsi
0x1400829da  mov     [rbp+var_18], rax
0x1400829de  lea     rdx, byte_1401408FD
0x1400829e5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1400829ec  mov     [rbp+var_20], rax
0x1400829f0  lea     rax, [rbp+var_8]
0x1400829f4  mov     [rsp+70h+var_28], rax
0x1400829f9  lea     rax, [rbp+var_10]
0x1400829fd  mov     [rsp+70h+var_30], rax
0x140082a02  lea     rax, [rbp+arg_0]
0x140082a06  mov     [rsp+70h+var_38], rax
0x140082a0b  lea     rax, [rbp+var_18]
0x140082a0f  mov     [rsp+70h+var_40], rax
0x140082a14  lea     rax, [rbp+arg_8]
0x140082a18  mov     [rsp+70h+var_48], rax
0x140082a1d  lea     rax, [rbp+var_20]
0x140082a21  jmp     loc_1400827AD
0x140082a26  mov     rcx, [rbp+arg_18]
0x140082a2a  xor     edx, edx
0x140082a2c  mov     rax, [rcx]
0x140082a2f  mov     rax, [rax+20h]
0x140082a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082a38  mov     ebx, eax
0x140082a3a  test    eax, eax
0x140082a3c  jns     short loc_140082ABD
0x140082a3e  mov     eax, cs:dword_140150118
0x140082a44  cmp     eax, 2
0x140082a47  jbe     loc_140082C52
0x140082a4d  lea     rax, aFailedToStartT_3; "Failed to start the Worker thread"
0x140082a54  mov     dword ptr [rbp+arg_0], 1C8h
0x140082a5b  mov     [rbp+var_8], rax
0x140082a5f  lea     rsi, aCreatethreads; "CreateThreads"
0x140082a66  lea     rax, aOnecoreTermsrv_19; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140082a6d  mov     [rbp+var_10], rsi
0x140082a71  mov     [rbp+var_18], rax
0x140082a75  lea     rdx, word_1401408AE
0x140082a7c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x140082a83  mov     [rbp+var_20], rax
0x140082a87  lea     rax, [rbp+var_8]
0x140082a8b  mov     [rsp+70h+var_28], rax
0x140082a90  lea     rax, [rbp+var_10]
0x140082a94  mov     [rsp+70h+var_30], rax
0x140082a99  lea     rax, [rbp+arg_0]
0x140082a9d  mov     [rsp+70h+var_38], rax
0x140082aa2  lea     rax, [rbp+var_18]
0x140082aa6  mov     [rsp+70h+var_40], rax
0x140082aab  lea     rax, [rbp+arg_8]
0x140082aaf  mov     [rsp+70h+var_48], rax
0x140082ab4  lea     rax, [rbp+var_20]
0x140082ab8  jmp     loc_1400827AD
0x140082abd  lea     rdi, [r14+48h]
0x140082ac1  mov     rax, [rdi]
0x140082ac4  cmp     [rbp+arg_10], rax
0x140082ac8  jz      short loc_140082AE1
0x140082aca  mov     rcx, rdi
0x140082acd  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140082ad2  mov     rax, [rbp+arg_10]
0x140082ad6  mov     rcx, rdi
0x140082ad9  mov     [rdi], rax
0x140082adc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140082ae1  lea     r15, [r14+50h]
0x140082ae5  mov     rax, [r15]
0x140082ae8  cmp     [rbp+arg_18], rax
0x140082aec  jz      short loc_140082B05
0x140082aee  mov     rcx, r15
0x140082af1  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140082af6  mov     rax, [rbp+arg_18]
0x140082afa  mov     rcx, r15
0x140082afd  mov     [r15], rax
0x140082b00  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140082b05  mov     rdi, [rdi]
0x140082b08  mov     rcx, rdi
0x140082b0b  mov     rbx, [rdi]
0x140082b0e  mov     rax, [rbx+18h]
0x140082b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082b17  mov     r9d, eax
0x140082b1a  lea     r8, ?STAThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadRecoveredWatchdogReport(void *)
0x140082b21  mov     rax, [rbx+0C8h]
0x140082b28  lea     rdx, ?STAThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::STAThreadStuckWatchdogReport(void *)
0x140082b2f  mov     dword ptr [rsp+70h+var_48], 0
0x140082b37  mov     rcx, rdi
0x140082b3a  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x140082b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082b47  lea     rsi, aCreatethreads; "CreateThreads"
0x140082b4e  lea     r13, aHresultFailedB; "HResult failed but continue"
0x140082b55  test    eax, eax
0x140082b57  jns     short loc_140082BAA
0x140082b59  mov     ecx, cs:dword_140150118
0x140082b5f  cmp     ecx, 3
0x140082b62  jbe     short loc_140082BAA
0x140082b64  mov     dword ptr [rbp+arg_0], eax
0x140082b67  lea     rdx, byte_140140871
0x140082b6e  lea     rax, aFailedToSetSta; "Failed to set STA thread watchdog"
0x140082b75  mov     [rbp+arg_8], rsi
0x140082b79  mov     [rbp+var_8], rax
0x140082b7d  lea     rax, [rbp+arg_8]
0x140082b81  mov     [rsp+70h+var_38], rax
0x140082b86  lea     rax, [rbp+arg_0]
0x140082b8a  mov     [rsp+70h+var_40], rax
0x140082b8f  lea     rax, [rbp+var_8]
0x140082b93  mov     [rsp+70h+var_48], rax
0x140082b98  lea     rax, [rbp+var_10]
0x140082b9c  mov     [rsp+70h+var_50], rax
0x140082ba1  mov     [rbp+var_10], r13
0x140082ba5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140082baa  mov     rdi, [r15]
0x140082bad  mov     rcx, rdi
0x140082bb0  mov     rbx, [rdi]
0x140082bb3  mov     rax, [rbx+18h]
0x140082bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082bbc  mov     r9d, eax
0x140082bbf  lea     r8, ?WorkerThreadRecoveredWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadRecoveredWatchdogReport(void *)
0x140082bc6  mov     rax, [rbx+0C8h]
0x140082bcd  lea     rdx, ?WorkerThreadStuckWatchdogReport@CRDPENCPlatformContext@@KAXPEAX@Z; CRDPENCPlatformContext::WorkerThreadStuckWatchdogReport(void *)
0x140082bd4  mov     dword ptr [rsp+70h+var_48], 0
0x140082bdc  mov     rcx, rdi
0x140082bdf  mov     dword ptr [rsp+70h+var_50], 2BF20h
0x140082be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140082bec  mov     ebx, eax
0x140082bee  test    eax, eax
  ... truncated ...
```
