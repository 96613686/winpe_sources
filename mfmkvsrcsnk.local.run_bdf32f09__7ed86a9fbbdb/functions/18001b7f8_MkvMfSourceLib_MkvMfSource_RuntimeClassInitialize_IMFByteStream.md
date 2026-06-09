# MkvMfSourceLib::MkvMfSource::RuntimeClassInitialize(IMFByteStream *)

- ea: `0x18001b7f8`
- end: `0x18001bd64`
- name: `?RuntimeClassInitialize@MkvMfSource@MkvMfSourceLib@@QEAAJPEAUIMFByteStream@@@Z`
- size: `1388`
- prototype: `int(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFByteStream *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000bf60`

## callees

- `0x1800023e0`
- `0x180003304`
- `0x1800097f0`
- `0x18000c00c`
- `0x18000cfb4`
- `0x18000d0f8`
- `0x18000d7cc`
- `0x18000d80c`
- `0x18001b7f8`
- `0x180020c3c`
- `0x180020d84`
- `0x180043cac`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b8e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bb71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bc20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b8e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bb71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bc20`
- `MFPlat!MFLockWorkQueue` at `0x18001bc02`
- `MFPlat!MFLockWorkQueue` at `0x18001bc02`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18001bb53`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18001bb53`
- `MFPlat!MFCreateEventQueue` at `0x18001b99d`
- `MFPlat!MFCreateEventQueue` at `0x18001b99d`
- `ext-ms-mf-pal-l2-1-0!ShouldChangeSourceCachingBehavior` at `0x18001bce4`
- `ext-ms-mf-pal-l2-1-0!ShouldChangeSourceCachingBehavior` at `0x18001bce4`

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
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v23 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    std::list<MkvMfSourceLib::MkvMfSource::Command>::push_back((char *)this + 664, v27);
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
        v33 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18001b7f8  mov     [rsp+arg_10], rbx
0x18001b7fd  mov     [rsp+arg_18], rsi
0x18001b802  push    rdi
0x18001b803  push    r12
0x18001b805  push    r14
0x18001b807  sub     rsp, 0B0h
0x18001b80e  mov     rax, cs:__security_cookie
0x18001b815  xor     rax, rsp
0x18001b818  mov     [rsp+0C8h+var_28], rax
0x18001b820  mov     r14, rdx
0x18001b823  mov     rsi, rcx
0x18001b826  mov     [rsp+0C8h+var_98], 0
0x18001b82e  mov     r8d, 5Fh ; '_'; int
0x18001b834  lea     r12, aMkvmfsourcelib_78; "MkvMfSourceLib::MkvMfSource::RuntimeCla"...
0x18001b83b  mov     rdx, r12; char *
0x18001b83e  lea     rcx, [rsp+0C8h+var_94]; this
0x18001b843  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001b848  nop
0x18001b849  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b850  cmp     byte ptr [rcx+8], 0
0x18001b854  jz      short loc_18001B8BC
0x18001b856  cmp     qword ptr [rsi+2B0h], 0
0x18001b85e  jz      short loc_18001B8BC
0x18001b860  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b865  mov     rdi, rax
0x18001b868  mov     rdx, [rsi+2B0h]
0x18001b86f  mov     rcx, [rdx]
0x18001b872  mov     rax, [rcx+128h]
0x18001b879  mov     rcx, rdx
0x18001b87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b881  mov     ebx, eax
0x18001b883  mov     r8, [rsi+2B0h]
0x18001b88a  mov     rcx, [r8]
0x18001b88d  mov     rax, [rcx+118h]
0x18001b894  lea     rdx, [rsp+0C8h+var_38]
0x18001b89c  mov     rcx, r8
0x18001b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a4  movups  xmm0, xmmword ptr [rax]
0x18001b8a7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001b8af  mov     [rdi+7E0h], ebx
0x18001b8b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b8bc  mov     [rsp+0C8h+var_80], rsi
0x18001b8c1  lea     rax, [rsp+0C8h+var_98]
0x18001b8c6  mov     [rsp+0C8h+var_78], rax
0x18001b8cb  test    r14, r14
0x18001b8ce  jnz     loc_18001B98A
0x18001b8d4  mov     [rsp+0C8h+var_98], 80004003h
0x18001b8dc  test    rcx, rcx
0x18001b8df  jnz     short loc_18001B922
0x18001b8e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001b8e7  mov     rcx, rax
0x18001b8ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b8f1  test    rax, rax
0x18001b8f4  jz      short loc_18001B914
0x18001b8f6  mov     rax, [rax]
0x18001b8f9  mov     edx, 7F0h
0x18001b8fe  mov     rax, [rax+8]
0x18001b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b907  test    eax, eax
0x18001b909  jz      short loc_18001B914
0x18001b90b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b912  jmp     short loc_18001B922
0x18001b914  lea     rcx, qword_1800D6F70; this
0x18001b91b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b922  cmp     byte ptr [rcx+8], 0
0x18001b926  jz      short loc_18001B951
0x18001b928  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b92d  mov     r9d, [rsp+0C8h+var_98]; int
0x18001b932  test    r9d, r9d
0x18001b935  jns     short loc_18001B951
0x18001b937  cmp     [rax+7CCh], r9d
0x18001b93e  jz      short loc_18001B951
0x18001b940  mov     r8d, 60h ; '`'; int
0x18001b946  mov     rdx, r12; char *
0x18001b949  mov     rcx, rax; this
0x18001b94c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001b951  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b958  jb      short loc_18001B981
0x18001b95a  mov     edx, 0Fh
0x18001b95f  mov     eax, [rsp+0C8h+var_98]
0x18001b963  mov     [rsp+0C8h+var_A8], eax
0x18001b967  mov     r9, rsi
0x18001b96a  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001b971  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b978  mov     rcx, [rcx+10h]
0x18001b97c  call    WPP_SF_qD
0x18001b981  mov     ebx, [rsp+0C8h+var_98]
0x18001b985  jmp     loc_18001BCC5
0x18001b98a  lea     rcx, [rsi+2A8h]
0x18001b991  call    ??$MakeAndInitialize@VMkvSourceTelemetryLogger@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VMkvSourceTelemetryLogger@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvSourceTelemetryLogger,MkvSourceTelemetryLogger,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<MkvSourceTelemetryLogger>>)
0x18001b996  lea     rcx, [rsi+90h]; ppMediaEventQueue
0x18001b99d  call    cs:__imp_MFCreateEventQueue
0x18001b9a3  mov     [rsp+0C8h+var_98], eax
0x18001b9a7  test    eax, eax
0x18001b9a9  jns     loc_18001BA42
0x18001b9af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b9b6  test    rcx, rcx
0x18001b9b9  jnz     short loc_18001B9FC
0x18001b9bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001b9c1  mov     rcx, rax
0x18001b9c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b9cb  test    rax, rax
0x18001b9ce  jz      short loc_18001B9EE
0x18001b9d0  mov     rax, [rax]
0x18001b9d3  mov     edx, 7F0h
0x18001b9d8  mov     rax, [rax+8]
0x18001b9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9e1  test    eax, eax
0x18001b9e3  jz      short loc_18001B9EE
0x18001b9e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b9ec  jmp     short loc_18001B9FC
0x18001b9ee  lea     rcx, qword_1800D6F70; this
0x18001b9f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b9fc  cmp     byte ptr [rcx+8], 0
0x18001ba00  jz      short loc_18001BA2B
0x18001ba02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001ba07  mov     r9d, [rsp+0C8h+var_98]; int
0x18001ba0c  test    r9d, r9d
0x18001ba0f  jns     short loc_18001BA2B
0x18001ba11  cmp     [rax+7CCh], r9d
0x18001ba18  jz      short loc_18001BA2B
0x18001ba1a  mov     r8d, 64h ; 'd'; int
0x18001ba20  mov     rdx, r12; char *
0x18001ba23  mov     rcx, rax; this
0x18001ba26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001ba2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ba32  jb      loc_18001BCC1
0x18001ba38  mov     edx, 10h
0x18001ba3d  jmp     loc_18001BC9E
0x18001ba42  lea     rcx, [rsi+0B8h]; this
0x18001ba49  mov     rdx, r14; struct IMFByteStream *
0x18001ba4c  call    ?Init@MkvReader@@QEAAJPEAUIMFByteStream@@@Z; MkvReader::Init(IMFByteStream *)
0x18001ba51  mov     [rsp+0C8h+var_98], eax
0x18001ba55  test    eax, eax
0x18001ba57  jns     loc_18001BAF0
0x18001ba5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba64  test    rcx, rcx
0x18001ba67  jnz     short loc_18001BAAA
0x18001ba69  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001ba6f  mov     rcx, rax
0x18001ba72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba79  test    rax, rax
0x18001ba7c  jz      short loc_18001BA9C
0x18001ba7e  mov     rax, [rax]
0x18001ba81  mov     edx, 7F0h
0x18001ba86  mov     rax, [rax+8]
0x18001ba8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba8f  test    eax, eax
0x18001ba91  jz      short loc_18001BA9C
0x18001ba93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ba9a  jmp     short loc_18001BAAA
0x18001ba9c  lea     rcx, qword_1800D6F70; this
0x18001baa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001baaa  cmp     byte ptr [rcx+8], 0
0x18001baae  jz      short loc_18001BAD9
0x18001bab0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bab5  mov     r9d, [rsp+0C8h+var_98]; int
0x18001baba  test    r9d, r9d
0x18001babd  jns     short loc_18001BAD9
0x18001babf  cmp     [rax+7CCh], r9d
0x18001bac6  jz      short loc_18001BAD9
0x18001bac8  mov     r8d, 67h ; 'g'; int
0x18001bace  mov     rdx, r12; char *
0x18001bad1  mov     rcx, rax; this
0x18001bad4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bad9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bae0  jb      loc_18001BCC1
0x18001bae6  mov     edx, 11h
0x18001baeb  jmp     loc_18001BC9E
0x18001baf0  mov     [rsp+0C8h+var_88], 0
0x18001baf9  mov     rax, [r14]
0x18001bafc  lea     rdx, [rsp+0C8h+var_88]
0x18001bb01  mov     rcx, r14
0x18001bb04  mov     rax, [rax+20h]
0x18001bb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb0d  shr     eax, 1Fh
0x18001bb10  mov     [rsi+251h], al
0x18001bb16  mov     r8, rsi
0x18001bb19  mov     edx, 4
0x18001bb1e  lea     rcx, [rsp+0C8h+var_70]
0x18001bb23  call    ??0Command@MkvMfSource@MkvMfSourceLib@@QEAA@W4Kind@012@PEAV12@@Z; MkvMfSourceLib::MkvMfSource::Command::Command(MkvMfSourceLib::MkvMfSource::Command::Kind,MkvMfSourceLib::MkvMfSource *)
0x18001bb28  nop
0x18001bb29  lea     rcx, [rsi+298h]
0x18001bb30  mov     rdx, rax
0x18001bb33  call    ?push_back@?$list@VCommand@MkvMfSource@MkvMfSourceLib@@V?$allocator@VCommand@MkvMfSource@MkvMfSourceLib@@@std@@@std@@QEAAX$$QEAVCommand@MkvMfSource@MkvMfSourceLib@@@Z; std::list<MkvMfSourceLib::MkvMfSource::Command>::push_back(MkvMfSourceLib::MkvMfSource::Command &&)
0x18001bb38  nop
0x18001bb39  lea     rcx, [rsp+0C8h+var_70]; this
0x18001bb3e  call    ??1Command@MkvMfSource@MkvMfSourceLib@@QEAA@XZ; MkvMfSourceLib::MkvMfSource::Command::~Command(void)
0x18001bb43  nop
0x18001bb44  lea     rbx, [rsi+1C0h]
0x18001bb4b  mov     rdx, rbx; pdwWorkQueue
0x18001bb4e  mov     ecx, 5; dwWorkQueue
0x18001bb53  call    cs:__imp_MFAllocateSerialWorkQueue
0x18001bb59  mov     [rsp+0C8h+var_98], eax
0x18001bb5d  test    eax, eax
0x18001bb5f  jns     loc_18001BBF8
0x18001bb65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb6c  test    rcx, rcx
0x18001bb6f  jnz     short loc_18001BBB2
0x18001bb71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001bb77  mov     rcx, rax
0x18001bb7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bb81  test    rax, rax
0x18001bb84  jz      short loc_18001BBA4
0x18001bb86  mov     rax, [rax]
0x18001bb89  mov     edx, 7F0h
0x18001bb8e  mov     rax, [rax+8]
0x18001bb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb97  test    eax, eax
0x18001bb99  jz      short loc_18001BBA4
0x18001bb9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bba2  jmp     short loc_18001BBB2
0x18001bba4  lea     rcx, qword_1800D6F70; this
0x18001bbab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bbb2  cmp     byte ptr [rcx+8], 0
0x18001bbb6  jz      short loc_18001BBE1
0x18001bbb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bbbd  mov     r9d, [rsp+0C8h+var_98]; int
0x18001bbc2  test    r9d, r9d
0x18001bbc5  jns     short loc_18001BBE1
0x18001bbc7  cmp     [rax+7CCh], r9d
0x18001bbce  jz      short loc_18001BBE1
0x18001bbd0  mov     r8d, 74h ; 't'; int
0x18001bbd6  mov     rdx, r12; char *
0x18001bbd9  mov     rcx, rax; this
0x18001bbdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bbe1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bbe8  jb      loc_18001BCC1
0x18001bbee  mov     edx, 12h
0x18001bbf3  jmp     loc_18001BC9E
0x18001bbf8  mov     ecx, [rbx]; dwWorkQueue
0x18001bbfa  test    ecx, ecx
0x18001bbfc  jz      loc_18001BCD3
0x18001bc02  call    cs:__imp_MFLockWorkQueue
0x18001bc08  mov     [rsp+0C8h+var_98], eax
0x18001bc0c  test    eax, eax
0x18001bc0e  jns     loc_18001BCD3
0x18001bc14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bc1b  test    rcx, rcx
0x18001bc1e  jnz     short loc_18001BC61
0x18001bc20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001bc26  mov     rcx, rax
0x18001bc29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bc30  test    rax, rax
0x18001bc33  jz      short loc_18001BC53
0x18001bc35  mov     rax, [rax]
0x18001bc38  mov     edx, 7F0h
0x18001bc3d  mov     rax, [rax+8]
0x18001bc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc46  test    eax, eax
0x18001bc48  jz      short loc_18001BC53
0x18001bc4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bc51  jmp     short loc_18001BC61
0x18001bc53  lea     rcx, qword_1800D6F70; this
0x18001bc5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001bc61  cmp     byte ptr [rcx+8], 0
0x18001bc65  jz      short loc_18001BC90
0x18001bc67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001bc6c  mov     r9d, [rsp+0C8h+var_98]; int
0x18001bc71  test    r9d, r9d
0x18001bc74  jns     short loc_18001BC90
0x18001bc76  cmp     [rax+7CCh], r9d
0x18001bc7d  jz      short loc_18001BC90
0x18001bc7f  mov     r8d, 78h ; 'x'; int
0x18001bc85  mov     rdx, r12; char *
0x18001bc88  mov     rcx, rax; this
0x18001bc8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001bc90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bc97  jb      short loc_18001BCC1
0x18001bc99  mov     edx, 13h
0x18001bc9e  mov     eax, [rsp+0C8h+var_98]
0x18001bca2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bca9  mov     [rsp+0C8h+var_A8], eax
0x18001bcad  mov     r9, rsi
0x18001bcb0  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001bcb7  mov     rcx, [rcx+10h]
0x18001bcbb  call    WPP_SF_qD
0x18001bcc0  nop
0x18001bcc1  mov     ebx, [rsp+0C8h+var_98]
0x18001bcc5  lea     rcx, [rsp+0C8h+var_94]; this
0x18001bcca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001bccf  mov     eax, ebx
0x18001bcd1  jmp     short loc_18001BD3B
0x18001bcd3  mov     [rsp+0C8h+var_90], 0
0x18001bcdb  call    IsShouldChangeSourceCachingBehaviorPresent
0x18001bce0  test    al, al
0x18001bce2  jz      short loc_18001BD15
0x18001bce4  call    cs:__imp_ShouldChangeSourceCachingBehavior
0x18001bcea  test    eax, eax
0x18001bcec  jz      short loc_18001BD15
0x18001bcee  mov     rax, [r14]
0x18001bcf1  lea     rdx, [rsp+0C8h+var_90]
0x18001bcf6  mov     rcx, r14
0x18001bcf9  mov     rax, [rax+18h]
0x18001bcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd02  test    eax, eax
0x18001bd04  js      short loc_18001BD15
0x18001bd06  mov     eax, [rsp+0C8h+var_90]
0x18001bd0a  shr     eax, 9
0x18001bd0d  and     al, 1
  ... truncated ...
```
