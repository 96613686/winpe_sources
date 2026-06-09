# MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize(IMFByteStream *)

- ea: `0x18001c47c`
- end: `0x18001ca25`
- name: `?RuntimeClassInitialize@MkvMfSource@MkvMfSourceLib@@QEAAJPEAUIMFByteStream@@@Z`
- size: `1449`
- prototype: `int(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFByteStream *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000c440`

## callees

- `0x180002400`
- `0x180003344`
- `0x180009b04`
- `0x18000c4ec`
- `0x18000c9a0`
- `0x18000d554`
- `0x18000d6a4`
- `0x18000ddc0`
- `0x18000de00`
- `0x18001c47c`
- `0x180021b9c`
- `0x180045acc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c64b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c6ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c819`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c8d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c565`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c64b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c6ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c819`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c8d4`
- `MFPlat!MFLockWorkQueue` at `0x18001c8b0`
- `MFPlat!MFLockWorkQueue` at `0x18001c8b0`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18001c7f5`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18001c7f5`
- `MFPlat!MFCreateEventQueue` at `0x18001c627`
- `MFPlat!MFCreateEventQueue` at `0x18001c627`
- `ext-ms-mf-pal-l2-1-0!ShouldChangeSourceCachingBehavior` at `0x18001c99e`
- `ext-ms-mf-pal-l2-1-0!ShouldChangeSourceCachingBehavior` at `0x18001c99e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize(
        MkvMfSourceLib::MkvMfSource *this,
        struct IMFByteStream *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rax
  DWORD *v28; // rbx
  HRESULT v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  const char *v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  int v43; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v44[4]; // [rsp+34h] [rbp-94h] BYREF
  int v45; // [rsp+38h] [rbp-90h] BYREF
  unsigned int v46; // [rsp+3Ch] [rbp-8Ch]
  _QWORD v47[3]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v48[56]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v49[16]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v43 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v44,
    "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize",
    95);
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            v49);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v47[1] = this;
  v47[2] = &v43;
  if ( !a2 )
  {
    v43 = -2147467261;
    if ( !v7 )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v43 < 0 && *((_DWORD *)v11 + 499) != v43 )
        CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize", 96, v43);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v43);
    v12 = v43;
    goto LABEL_69;
  }
  Microsoft::WRL::Details::MakeAndInitialize<MkvSourceTelemetryLogger,MkvSourceTelemetryLogger,>((char *)this + 680);
  v43 = MFCreateEventQueue((IMFMediaEventQueue **)this + 18);
  if ( v43 < 0 )
  {
    v16 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( v43 < 0 && *((_DWORD *)v18 + 499) != v43 )
        CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize", 100, v43);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v19 = 16;
LABEL_67:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v43);
LABEL_68:
    v12 = v43;
LABEL_69:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
    return v12;
  }
  v43 = MkvReader::Init((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), a2);
  if ( v43 < 0 )
  {
    v23 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( v43 < 0 && *((_DWORD *)v25 + 499) != v43 )
        CallStackContext::TraceFailure(v25, "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize", 103, v43);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v19 = 17;
    goto LABEL_67;
  }
  v47[0] = 0;
  v26 = ((unsigned int (__fastcall *)(struct IMFByteStream *, _QWORD *))a2->lpVtbl->GetLength)(a2, v47) >> 31;
  *((_BYTE *)this + 593) = v26;
  try
  {
    v27 = MkvMfSourceLib::MkvMfSource::Command::Command(v48, 4, this);
    std::list<MkvMfSourceLib::MkvMfSource::Command>::_Emplace<MkvMfSourceLib::MkvMfSource::Command>(
      (char *)this + 664,
      *((_QWORD *)this + 83),
      v27);
    MkvMfSourceLib::MkvMfSource::Command::~Command((MkvMfSourceLib::MkvMfSource::Command *)v48);
    v28 = (DWORD *)((char *)this + 448);
    v29 = MFAllocateSerialWorkQueue(5u, (DWORD *)this + 112);
  }
  catch ( ... )
  {
    v46 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x72,
            (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
            v32);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
    return v46;
  }
  v43 = v29;
  if ( v29 < 0 )
  {
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( v43 < 0 && *((_DWORD *)v35 + 499) != v43 )
        CallStackContext::TraceFailure(v35, "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize", 116, v43);
    }
    if ( !g_wppLevels )
      goto LABEL_68;
    v19 = 18;
    goto LABEL_67;
  }
  if ( *v28 )
  {
    v43 = MFLockWorkQueue(*v28);
    if ( v43 < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( v43 < 0 && *((_DWORD *)v41 + 499) != v43 )
          CallStackContext::TraceFailure(v41, "MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize", 120, v43);
      }
      if ( !g_wppLevels )
        goto LABEL_68;
      v19 = 19;
      goto LABEL_67;
    }
  }
  v45 = 0;
  if ( (unsigned __int8)IsShouldChangeSourceCachingBehaviorPresent()
    && (unsigned int)ShouldChangeSourceCachingBehavior()
    && ((int (__fastcall *)(struct IMFByteStream *, int *))a2->lpVtbl->GetCapabilities)(a2, &v45) >= 0 )
  {
    *((_BYTE *)this + 656) = (v45 & 0x200) != 0;
  }
  *((_DWORD *)this + 130) = 1;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v44);
  return 0;
}

```

## disassembly

```asm
0x18001c47c  mov     [rsp+arg_10], rbx
0x18001c481  mov     [rsp+arg_18], rsi
0x18001c486  push    rdi
0x18001c487  push    r12
0x18001c489  push    r14
0x18001c48b  sub     rsp, 0B0h
0x18001c492  mov     rax, cs:__security_cookie
0x18001c499  xor     rax, rsp
0x18001c49c  mov     [rsp+0C8h+var_28], rax
0x18001c4a4  mov     r14, rdx
0x18001c4a7  mov     rsi, rcx
0x18001c4aa  mov     [rsp+0C8h+var_98], 0
0x18001c4b2  mov     r8d, 5Fh ; '_'; int
0x18001c4b8  lea     r12, aMkvmfsourcelib_78; "MkvMfSourceLib::MkvMfSource::RuntimeCla"...
0x18001c4bf  mov     rdx, r12; char *
0x18001c4c2  lea     rcx, [rsp+0C8h+var_94]; this
0x18001c4c7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001c4cc  nop
0x18001c4cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001c4d4  cmp     byte ptr [rcx+8], 0
0x18001c4d8  jz      short loc_18001C540
0x18001c4da  cmp     qword ptr [rsi+2B0h], 0
0x18001c4e2  jz      short loc_18001C540
0x18001c4e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c4e9  mov     rdi, rax
0x18001c4ec  mov     rdx, [rsi+2B0h]
0x18001c4f3  mov     rcx, [rdx]
0x18001c4f6  mov     rax, [rcx+128h]
0x18001c4fd  mov     rcx, rdx
0x18001c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c505  mov     ebx, eax
0x18001c507  mov     r8, [rsi+2B0h]
0x18001c50e  mov     rcx, [r8]
0x18001c511  mov     rax, [rcx+118h]
0x18001c518  lea     rdx, [rsp+0C8h+var_38]
0x18001c520  mov     rcx, r8
0x18001c523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c528  movups  xmm0, xmmword ptr [rax]
0x18001c52b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001c533  mov     [rdi+7E0h], ebx
0x18001c539  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c540  mov     [rsp+0C8h+var_80], rsi
0x18001c545  lea     rax, [rsp+0C8h+var_98]
0x18001c54a  mov     [rsp+0C8h+var_78], rax
0x18001c54f  test    r14, r14
0x18001c552  jnz     loc_18001C614
0x18001c558  mov     [rsp+0C8h+var_98], 80004003h
0x18001c560  test    rcx, rcx
0x18001c563  jnz     short loc_18001C5AC
0x18001c565  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c56c  nop     dword ptr [rax+rax+00h]
0x18001c571  mov     rcx, rax
0x18001c574  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c57b  test    rax, rax
0x18001c57e  jz      short loc_18001C59E
0x18001c580  mov     rax, [rax]
0x18001c583  mov     edx, 7F0h
0x18001c588  mov     rax, [rax+8]
0x18001c58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c591  test    eax, eax
0x18001c593  jz      short loc_18001C59E
0x18001c595  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c59c  jmp     short loc_18001C5AC
0x18001c59e  lea     rcx, qword_1800DBF70; this
0x18001c5a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c5ac  cmp     byte ptr [rcx+8], 0
0x18001c5b0  jz      short loc_18001C5DB
0x18001c5b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c5b7  mov     r9d, [rsp+0C8h+var_98]; int
0x18001c5bc  test    r9d, r9d
0x18001c5bf  jns     short loc_18001C5DB
0x18001c5c1  cmp     [rax+7CCh], r9d
0x18001c5c8  jz      short loc_18001C5DB
0x18001c5ca  mov     r8d, 60h ; '`'; int
0x18001c5d0  mov     rdx, r12; char *
0x18001c5d3  mov     rcx, rax; this
0x18001c5d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c5db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c5e2  jb      short loc_18001C60B
0x18001c5e4  mov     edx, 0Fh
0x18001c5e9  mov     eax, [rsp+0C8h+var_98]
0x18001c5ed  mov     [rsp+0C8h+var_A8], eax
0x18001c5f1  mov     r9, rsi
0x18001c5f4  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001c5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c602  mov     rcx, [rcx+10h]
0x18001c606  call    WPP_SF_qD
0x18001c60b  mov     ebx, [rsp+0C8h+var_98]
0x18001c60f  jmp     loc_18001C97F
0x18001c614  lea     rcx, [rsi+2A8h]
0x18001c61b  call    ??$MakeAndInitialize@VMkvSourceTelemetryLogger@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvSourceTelemetryLogger,MkvSourceTelemetryLogger,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>>)
0x18001c620  lea     rcx, [rsi+90h]; ppMediaEventQueue
0x18001c627  call    cs:__imp_MFCreateEventQueue
0x18001c62e  nop     dword ptr [rax+rax+00h]
0x18001c633  mov     [rsp+0C8h+var_98], eax
0x18001c637  test    eax, eax
0x18001c639  jns     loc_18001C6D8
0x18001c63f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c646  test    rcx, rcx
0x18001c649  jnz     short loc_18001C692
0x18001c64b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c652  nop     dword ptr [rax+rax+00h]
0x18001c657  mov     rcx, rax
0x18001c65a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c661  test    rax, rax
0x18001c664  jz      short loc_18001C684
0x18001c666  mov     rax, [rax]
0x18001c669  mov     edx, 7F0h
0x18001c66e  mov     rax, [rax+8]
0x18001c672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c677  test    eax, eax
0x18001c679  jz      short loc_18001C684
0x18001c67b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c682  jmp     short loc_18001C692
0x18001c684  lea     rcx, qword_1800DBF70; this
0x18001c68b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c692  cmp     byte ptr [rcx+8], 0
0x18001c696  jz      short loc_18001C6C1
0x18001c698  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c69d  mov     r9d, [rsp+0C8h+var_98]; int
0x18001c6a2  test    r9d, r9d
0x18001c6a5  jns     short loc_18001C6C1
0x18001c6a7  cmp     [rax+7CCh], r9d
0x18001c6ae  jz      short loc_18001C6C1
0x18001c6b0  mov     r8d, 64h ; 'd'; int
0x18001c6b6  mov     rdx, r12; char *
0x18001c6b9  mov     rcx, rax; this
0x18001c6bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c6c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c6c8  jb      loc_18001C97B
0x18001c6ce  mov     edx, 10h
0x18001c6d3  jmp     loc_18001C958
0x18001c6d8  lea     rcx, [rsi+0B8h]; this
0x18001c6df  mov     rdx, r14; struct IMFByteStream *
0x18001c6e2  call    ?Init@MkvReader@@QEAAJPEAUIMFByteStream@@@Z; MkvReader::Init(IMFByteStream *)
0x18001c6e7  mov     [rsp+0C8h+var_98], eax
0x18001c6eb  test    eax, eax
0x18001c6ed  jns     loc_18001C78C
0x18001c6f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c6fa  test    rcx, rcx
0x18001c6fd  jnz     short loc_18001C746
0x18001c6ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c706  nop     dword ptr [rax+rax+00h]
0x18001c70b  mov     rcx, rax
0x18001c70e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c715  test    rax, rax
0x18001c718  jz      short loc_18001C738
0x18001c71a  mov     rax, [rax]
0x18001c71d  mov     edx, 7F0h
0x18001c722  mov     rax, [rax+8]
0x18001c726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c72b  test    eax, eax
0x18001c72d  jz      short loc_18001C738
0x18001c72f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c736  jmp     short loc_18001C746
0x18001c738  lea     rcx, qword_1800DBF70; this
0x18001c73f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c746  cmp     byte ptr [rcx+8], 0
0x18001c74a  jz      short loc_18001C775
0x18001c74c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c751  mov     r9d, [rsp+0C8h+var_98]; int
0x18001c756  test    r9d, r9d
0x18001c759  jns     short loc_18001C775
0x18001c75b  cmp     [rax+7CCh], r9d
0x18001c762  jz      short loc_18001C775
0x18001c764  mov     r8d, 67h ; 'g'; int
0x18001c76a  mov     rdx, r12; char *
0x18001c76d  mov     rcx, rax; this
0x18001c770  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c775  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c77c  jb      loc_18001C97B
0x18001c782  mov     edx, 11h
0x18001c787  jmp     loc_18001C958
0x18001c78c  mov     [rsp+0C8h+var_88], 0
0x18001c795  mov     rax, [r14]
0x18001c798  lea     rdx, [rsp+0C8h+var_88]
0x18001c79d  mov     rcx, r14
0x18001c7a0  mov     rax, [rax+20h]
0x18001c7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a9  shr     eax, 1Fh
0x18001c7ac  mov     [rsi+251h], al
0x18001c7b2  lea     rbx, [rsi+298h]
0x18001c7b9  mov     r8, rsi
0x18001c7bc  mov     edx, 4
0x18001c7c1  lea     rcx, [rsp+0C8h+var_70]
0x18001c7c6  call    ??0Command@MkvMfSource@MkvMfSourceLib@@QEAA@W4Kind@012@PEAV12@@Z; MkvMfSourceLib::MkvMfSource::Command::Command(MkvMfSourceLib::MkvMfSource::Command::Kind,MkvMfSourceLib::MkvMfSource *)
0x18001c7cb  nop
0x18001c7cc  mov     r8, rax
0x18001c7cf  mov     rdx, [rbx]
0x18001c7d2  mov     rcx, rbx
0x18001c7d5  call    ??$_Emplace@VCommand@MkvMfSource@MkvMfSourceLib@@@?$list@VCommand@MkvMfSource@MkvMfSourceLib@@V?$allocator@VCommand@MkvMfSource@MkvMfSourceLib@@@std@@@std@@QEAAPEAU?$_List_node@VCommand@MkvMfSource@MkvMfSourceLib@@PEAX@1@QEAU21@$$QEAVCommand@MkvMfSource@MkvMfSourceLib@@@Z; std::list<MkvMfSourceLib::MkvMfSource::Command>::_Emplace<MkvMfSourceLib::MkvMfSource::Command>(std::_List_node<MkvMfSourceLib::MkvMfSource::Command,void *> * const,MkvMfSourceLib::MkvMfSource::Command &&)
0x18001c7da  nop
0x18001c7db  lea     rcx, [rsp+0C8h+var_70]; this
0x18001c7e0  call    ??1Command@MkvMfSource@MkvMfSourceLib@@QEAA@XZ; MkvMfSourceLib::MkvMfSource::Command::~Command(void)
0x18001c7e5  nop
0x18001c7e6  lea     rbx, [rsi+1C0h]
0x18001c7ed  mov     rdx, rbx; pdwWorkQueue
0x18001c7f0  mov     ecx, 5; dwWorkQueue
0x18001c7f5  call    cs:__imp_MFAllocateSerialWorkQueue
0x18001c7fc  nop     dword ptr [rax+rax+00h]
0x18001c801  mov     [rsp+0C8h+var_98], eax
0x18001c805  test    eax, eax
0x18001c807  jns     loc_18001C8A6
0x18001c80d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c814  test    rcx, rcx
0x18001c817  jnz     short loc_18001C860
0x18001c819  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c820  nop     dword ptr [rax+rax+00h]
0x18001c825  mov     rcx, rax
0x18001c828  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c82f  test    rax, rax
0x18001c832  jz      short loc_18001C852
0x18001c834  mov     rax, [rax]
0x18001c837  mov     edx, 7F0h
0x18001c83c  mov     rax, [rax+8]
0x18001c840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c845  test    eax, eax
0x18001c847  jz      short loc_18001C852
0x18001c849  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c850  jmp     short loc_18001C860
0x18001c852  lea     rcx, qword_1800DBF70; this
0x18001c859  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c860  cmp     byte ptr [rcx+8], 0
0x18001c864  jz      short loc_18001C88F
0x18001c866  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c86b  mov     r9d, [rsp+0C8h+var_98]; int
0x18001c870  test    r9d, r9d
0x18001c873  jns     short loc_18001C88F
0x18001c875  cmp     [rax+7CCh], r9d
0x18001c87c  jz      short loc_18001C88F
0x18001c87e  mov     r8d, 74h ; 't'; int
0x18001c884  mov     rdx, r12; char *
0x18001c887  mov     rcx, rax; this
0x18001c88a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c88f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c896  jb      loc_18001C97B
0x18001c89c  mov     edx, 12h
0x18001c8a1  jmp     loc_18001C958
0x18001c8a6  mov     ecx, [rbx]; dwWorkQueue
0x18001c8a8  test    ecx, ecx
0x18001c8aa  jz      loc_18001C98D
0x18001c8b0  call    cs:__imp_MFLockWorkQueue
0x18001c8b7  nop     dword ptr [rax+rax+00h]
0x18001c8bc  mov     [rsp+0C8h+var_98], eax
0x18001c8c0  test    eax, eax
0x18001c8c2  jns     loc_18001C98D
0x18001c8c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c8cf  test    rcx, rcx
0x18001c8d2  jnz     short loc_18001C91B
0x18001c8d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c8db  nop     dword ptr [rax+rax+00h]
0x18001c8e0  mov     rcx, rax
0x18001c8e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c8ea  test    rax, rax
0x18001c8ed  jz      short loc_18001C90D
0x18001c8ef  mov     rax, [rax]
0x18001c8f2  mov     edx, 7F0h
0x18001c8f7  mov     rax, [rax+8]
0x18001c8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c900  test    eax, eax
0x18001c902  jz      short loc_18001C90D
0x18001c904  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c90b  jmp     short loc_18001C91B
0x18001c90d  lea     rcx, qword_1800DBF70; this
0x18001c914  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c91b  cmp     byte ptr [rcx+8], 0
0x18001c91f  jz      short loc_18001C94A
0x18001c921  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c926  mov     r9d, [rsp+0C8h+var_98]; int
0x18001c92b  test    r9d, r9d
0x18001c92e  jns     short loc_18001C94A
0x18001c930  cmp     [rax+7CCh], r9d
0x18001c937  jz      short loc_18001C94A
0x18001c939  mov     r8d, 78h ; 'x'; int
0x18001c93f  mov     rdx, r12; char *
0x18001c942  mov     rcx, rax; this
0x18001c945  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c94a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c951  jb      short loc_18001C97B
0x18001c953  mov     edx, 13h
0x18001c958  mov     eax, [rsp+0C8h+var_98]
0x18001c95c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c963  mov     [rsp+0C8h+var_A8], eax
0x18001c967  mov     r9, rsi
0x18001c96a  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001c971  mov     rcx, [rcx+10h]
0x18001c975  call    WPP_SF_qD
0x18001c97a  nop
0x18001c97b  mov     ebx, [rsp+0C8h+var_98]
0x18001c97f  lea     rcx, [rsp+0C8h+var_94]; this
0x18001c984  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001c989  mov     eax, ebx
0x18001c98b  jmp     short loc_18001C9FB
0x18001c98d  mov     [rsp+0C8h+var_90], 0
0x18001c995  call    IsShouldChangeSourceCachingBehaviorPresent
0x18001c99a  test    al, al
0x18001c99c  jz      short loc_18001C9D5
0x18001c99e  call    cs:__imp_ShouldChangeSourceCachingBehavior
0x18001c9a5  nop     dword ptr [rax+rax+00h]
0x18001c9aa  test    eax, eax
  ... truncated ...
```
