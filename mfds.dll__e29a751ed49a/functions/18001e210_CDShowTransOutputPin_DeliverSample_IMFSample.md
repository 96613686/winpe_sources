# CDShowTransOutputPin::DeliverSample(IMFSample *)

- ea: `0x18001e210`
- end: `0x18001e935`
- name: `?DeliverSample@CDShowTransOutputPin@@QEAAJPEAUIMFSample@@@Z`
- size: `1829`
- prototype: `__int64 __fastcall(CDShowTransOutputPin *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18001d9f0`

## callees

- `0x1800140b0`
- `0x18001e210`
- `0x18001e940`
- `0x18001eb90`
- `0x180023e10`
- `0x180032a50`
- `0x180051550`
- `0x180051ce4`
- `0x180053dc0`
- `0x180073d0c`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e424`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e498`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e424`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e498`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e4ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e4ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e28e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e564`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e28e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e622`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e5af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e5af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e274`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e549`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e274`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e549`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e71b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e78b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e7f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e889`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e8ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e71b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e78b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e7f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e889`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001e8ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CDShowTransOutputPin::DeliverSample(CDShowTransOutputPin *this, struct IMFSample *a2)
{
  CallStackTracing *v4; // rdi
  char *v5; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  struct CDShowTransRoot *v11; // r15
  volatile signed __int32 *v12; // rax
  __int64 v13; // rcx
  volatile signed __int32 *v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 v18; // rax
  RTL_SRWLOCK *v19; // rdi
  PVOID Ptr; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v24; // rcx
  unsigned int v25; // esi
  CallStackTracing *v26; // rdi
  GUID *v27; // rbx
  DWORD v28; // r14d
  GUID *v29; // rax
  int v30; // eax
  int v31; // eax
  CallStackTracing *v33; // rcx
  __int64 v34; // rax
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rax
  __int64 v41; // rdx
  CallStackTracing *v42; // rax
  CallStackTracing *v43; // rax
  CallStackTracing *v44; // rax
  CallStackTracing *v45; // rax
  struct IMediaSample *v46[4]; // [rsp+30h] [rbp-20h] BYREF
  int v47; // [rsp+90h] [rbp+40h] BYREF
  volatile signed __int32 *v48; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v49; // [rsp+A8h] [rbp+58h] BYREF

  v47 = 0;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v33)(v33);
      if ( v34 )
        v5 = (char *)v34;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CDShowTransOutputPin::DeliverSample";
      *(_DWORD *)&v5[8 * v9 + 8] = 1185;
    }
    ++*((_DWORD *)v5 + 497);
  }
  v46[1] = 0;
  v46[2] = (struct IMediaSample *)&v47;
  if ( (*((_DWORD *)this + 4) & 0xFFFFFFFD) != 0 || *((_DWORD *)this + 2) != 1 )
    goto LABEL_33;
  v10 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 20) == 1 )
  {
    if ( !v10 )
      goto LABEL_13;
LABEL_33:
    v47 = -2147467259;
    goto LABEL_40;
  }
  if ( v10 == 2 )
    goto LABEL_33;
LABEL_13:
  v11 = 0;
  v12 = (volatile signed __int32 *)operator new(0x40u);
  v14 = v12;
  v48 = v12;
  if ( v12 )
  {
    v15 = *((_QWORD *)this + 5);
    *(_QWORD *)v12 = &CDShowTransSample::`vftable'{for `IMediaSample'};
    *((_QWORD *)v12 + 1) = &CDShowTransSample::`vftable'{for `IAttributeGet'};
    *((_DWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 3) = a2;
    if ( a2 )
      ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
    *((_QWORD *)v14 + 4) = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    *((_QWORD *)v14 + 5) = 0;
    *((_QWORD *)v14 + 6) = 0;
    *((_QWORD *)v14 + 7) = -1;
    v47 = ((__int64 (__fastcall *)(struct IMFSample *))a2->lpVtbl->ConvertToContiguousBuffer)(a2);
    v49 = -1;
    if ( ((int (__fastcall *)(struct IMFSample *, __int128 *, __int64 *))a2->lpVtbl->GetUINT64)(
           a2,
           &MFSampleExtension_ByteStreamOffset,
           &v49) >= 0 )
      *((_QWORD *)v14 + 7) = v49;
  }
  else
  {
    v14 = 0;
  }
  if ( v47 < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13);
      CallStackTracing::s_wpInstance = v40;
      if ( !v40 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v47 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v47 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransOutputPin::DeliverSample", 1190, v47);
    }
    if ( !g_wppLevels )
      goto LABEL_36;
    v41 = 38;
LABEL_88:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v47);
    goto LABEL_36;
  }
  _InterlockedIncrement(v14 + 4);
  v46[0] = (struct IMediaSample *)v14;
  LODWORD(v48) = 0;
  v47 = DShow::COutputQueue::ReceiveMultiple(*((DShow::COutputQueue **)this + 4), v46, 1, (int *)&v48);
  if ( v47 < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16);
      CallStackTracing::s_wpInstance = v42;
      if ( !v42 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v47 < 0 && *((_DWORD *)v38 + 499) != v47 )
        CallStackContext::TraceFailure(v38, "CDShowTransOutputPin::DeliverSample", 1196, v47);
    }
    if ( !g_wppLevels )
      goto LABEL_36;
    v41 = 39;
    goto LABEL_88;
  }
  if ( *((_DWORD *)this + 2) != 1 )
  {
    v11 = 0;
LABEL_28:
    v47 = -2147467259;
    goto LABEL_29;
  }
  v17 = *((_QWORD *)this + 6);
  if ( *(_DWORD *)(v17 + 88) == GetCurrentThreadId() )
    ++*(_DWORD *)(v17 + 92);
  else
    AcquireSRWLockShared((PSRWLOCK)(v17 + 80));
  v11 = *(struct CDShowTransRoot **)(v17 + 72);
  if ( !v11 )
    goto LABEL_28;
  v18 = *((_QWORD *)v11 + 3);
  if ( !*(_QWORD *)(v18 + 200) )
    ATL::AtlThrowImpl(-2147024809);
  v19 = *(RTL_SRWLOCK **)(**(_QWORD **)(v18 + 192) + 56LL);
  AcquireSRWLockShared(v19 + 11);
  Ptr = v19[14].Ptr;
  ReleaseSRWLockShared(v19 + 11);
  if ( !Ptr )
  {
    v47 = CDShowTransOutputPin::RequestInputSamples(this, v11, 1u);
    if ( v47 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v21);
        CallStackTracing::s_wpInstance = v43;
        if ( !v43 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v47 < 0 && *((_DWORD *)v39 + 499) != v47 )
          CallStackContext::TraceFailure(v39, "CDShowTransOutputPin::DeliverSample", 1215, v47);
      }
      if ( g_wppLevels )
      {
        v41 = 40;
        goto LABEL_88;
      }
    }
  }
LABEL_36:
  if ( v47 < 0 )
  {
LABEL_29:
    if ( v14 )
      CDShowTransSample::Release((CDShowTransSample *)v14);
  }
  if ( v11 )
  {
    v22 = *((_QWORD *)this + 6);
    CurrentThreadId = GetCurrentThreadId();
    v24 = (CMFSRWLock *)(v22 + 80);
    if ( *(_DWORD *)(v22 + 88) == CurrentThreadId )
      CMFSRWLock::UnlockExclusive(v24);
    else
      ReleaseSRWLockShared((PSRWLOCK)v24);
  }
LABEL_40:
  v25 = v47;
  v26 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v27 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v28 = GetLastError();
    v29 = (GUID *)TlsGetValue(*((_DWORD *)v26 + 3));
    if ( v29 )
    {
      v27 = v29;
    }
    else if ( !GetLastError() )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
      if ( v36 )
        v27 = (GUID *)v36;
    }
    SetLastError(v28);
    v30 = *(_DWORD *)&v27[124].Data2;
    if ( v30 )
    {
      v31 = v30 - 1;
      *(_DWORD *)&v27[124].Data2 = v31;
      if ( !v31 )
      {
        *(_DWORD *)&v27[124].Data2 = 0;
        v27[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_QWORD *)&v27[126].Data1 = 0;
        *(_DWORD *)&v27[124].Data4[4] = 0;
        *(_DWORD *)v27[126].Data4 = 0;
        v27[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v25;
}

```

## disassembly

```asm
0x18001e210  mov     [rsp-38h+arg_8], rbx
0x18001e215  push    rbp
0x18001e216  push    rsi
0x18001e217  push    rdi
0x18001e218  push    r12
0x18001e21a  push    r13
0x18001e21c  push    r14
0x18001e21e  push    r15
0x18001e220  mov     rbp, rsp
0x18001e223  sub     rsp, 50h
0x18001e227  mov     r12, rdx
0x18001e22a  mov     r14, rcx
0x18001e22d  xor     r13d, r13d
0x18001e230  mov     [rbp+arg_0], r13d
0x18001e234  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e23b  jz      loc_18001E87F
0x18001e241  lea     r15, qword_1800EB130
0x18001e248  lea     rcx, aCdshowtransout_0; "CDShowTransOutputPin::DeliverSample"
0x18001e24f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e256  cmp     [rdi+8], r13b
0x18001e25a  jz      short loc_18001E2C4
0x18001e25c  lea     rbx, [rdi+0D0h]
0x18001e263  call    cs:__imp_GetLastError
0x18001e26a  nop     dword ptr [rax+rax+00h]
0x18001e26f  mov     esi, eax
0x18001e271  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001e274  call    cs:__imp_TlsGetValue
0x18001e27b  nop     dword ptr [rax+rax+00h]
0x18001e280  test    rax, rax
0x18001e283  jz      loc_18001E5E7
0x18001e289  mov     rbx, rax
0x18001e28c  mov     ecx, esi; dwErrCode
0x18001e28e  call    cs:__imp_SetLastError
0x18001e295  nop     dword ptr [rax+rax+00h]
0x18001e29a  lea     rcx, aCdshowtransout_0; "CDShowTransOutputPin::DeliverSample"
0x18001e2a1  mov     eax, [rbx+7C4h]
0x18001e2a7  cmp     eax, [rbx+7C8h]
0x18001e2ad  jnb     short loc_18001E2BE
0x18001e2af  add     rax, rax
0x18001e2b2  mov     [rbx+rax*8], rcx
0x18001e2b6  mov     dword ptr [rbx+rax*8+8], 4A1h
0x18001e2be  inc     dword ptr [rbx+7C4h]
0x18001e2c4  mov     [rbp+var_18], r13
0x18001e2c8  lea     rax, [rbp+arg_0]
0x18001e2cc  mov     [rbp+var_10], rax
0x18001e2d0  test    dword ptr [r14+10h], 0FFFFFFFDh
0x18001e2d8  jnz     loc_18001E47A
0x18001e2de  cmp     dword ptr [r14+8], 1
0x18001e2e3  jnz     loc_18001E47A
0x18001e2e9  mov     eax, [r14+0Ch]
0x18001e2ed  cmp     dword ptr [r14+50h], 1
0x18001e2f2  jnz     loc_18001E8D4
0x18001e2f8  test    eax, eax
0x18001e2fa  jnz     loc_18001E47A
0x18001e300  mov     r15, r13
0x18001e303  mov     ecx, 40h ; '@'; Size
0x18001e308  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e30d  mov     rsi, rax
0x18001e310  mov     [rbp+arg_10], rax
0x18001e314  test    rax, rax
0x18001e317  jz      loc_18001E46C
0x18001e31d  mov     rbx, [r14+28h]
0x18001e321  lea     rax, ??_7CDShowTransSample@@6BIMediaSample@@@; const CDShowTransSample::`vftable'{for `IMediaSample'}
0x18001e328  mov     [rsi], rax
0x18001e32b  lea     rax, ??_7CDShowTransSample@@6BIAttributeGet@@@; const CDShowTransSample::`vftable'{for `IAttributeGet'}
0x18001e332  mov     [rsi+8], rax
0x18001e336  mov     [rsi+10h], r13d
0x18001e33a  mov     [rsi+18h], r12
0x18001e33e  test    r12, r12
0x18001e341  jz      short loc_18001E354
0x18001e343  mov     rax, [r12]
0x18001e347  mov     rcx, r12
0x18001e34a  mov     rax, [rax+8]
0x18001e34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e353  nop
0x18001e354  mov     [rsi+20h], rbx
0x18001e358  test    rbx, rbx
0x18001e35b  jz      short loc_18001E36D
0x18001e35d  mov     rax, [rbx]
0x18001e360  mov     rcx, rbx
0x18001e363  mov     rax, [rax+8]
0x18001e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36c  nop
0x18001e36d  lea     rdx, [rsi+28h]
0x18001e371  mov     [rdx], r13
0x18001e374  mov     [rsi+30h], r13
0x18001e378  mov     qword ptr [rsi+38h], 0FFFFFFFFFFFFFFFFh
0x18001e380  mov     rax, [r12]
0x18001e384  mov     rcx, r12
0x18001e387  mov     rax, [rax+148h]
0x18001e38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e393  mov     [rbp+arg_0], eax
0x18001e396  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x18001e39e  mov     rax, [r12]
0x18001e3a2  lea     r8, [rbp+arg_18]
0x18001e3a6  lea     rdx, MFSampleExtension_ByteStreamOffset
0x18001e3ad  mov     rcx, r12
0x18001e3b0  mov     rax, [rax+40h]
0x18001e3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b9  test    eax, eax
0x18001e3bb  js      short loc_18001E3C5
0x18001e3bd  mov     rax, [rbp+arg_18]
0x18001e3c1  mov     [rsi+38h], rax
0x18001e3c5  cmp     [rbp+arg_0], 0
0x18001e3c9  jl      loc_18001E711
0x18001e3cf  lock inc dword ptr [rsi+10h]
0x18001e3d3  mov     [rbp+var_20], rsi
0x18001e3d7  mov     dword ptr [rbp+arg_10], r13d
0x18001e3db  lea     r9, [rbp+arg_10]; int *
0x18001e3df  mov     r8d, 1; int
0x18001e3e5  lea     rdx, [rbp+var_20]; struct IMediaSample **
0x18001e3e9  mov     rcx, [r14+20h]; this
0x18001e3ed  call    ?ReceiveMultiple@COutputQueue@DShow@@QEAAJPEAPEAUIMediaSample@@JPEAJ@Z; DShow::COutputQueue::ReceiveMultiple(IMediaSample * *,long,long *)
0x18001e3f2  mov     [rbp+arg_0], eax
0x18001e3f5  test    eax, eax
0x18001e3f7  js      loc_18001E781
0x18001e3fd  cmp     dword ptr [r14+8], 1
0x18001e402  jnz     loc_18001E8E2
0x18001e408  mov     r15, [r14+30h]
0x18001e40c  call    cs:__imp_GetCurrentThreadId
0x18001e413  nop     dword ptr [rax+rax+00h]
0x18001e418  mov     ecx, [r15+58h]
0x18001e41c  cmp     ecx, eax
0x18001e41e  jz      short loc_18001E474
0x18001e420  lea     rcx, [r15+50h]; SRWLock
0x18001e424  call    cs:__imp_AcquireSRWLockShared
0x18001e42b  nop     dword ptr [rax+rax+00h]
0x18001e430  mov     r15, [r15+48h]
0x18001e434  test    r15, r15
0x18001e437  jz      short loc_18001E452
0x18001e439  mov     rax, [r15+18h]
0x18001e43d  cmp     qword ptr [rax+0C8h], 0
0x18001e445  ja      short loc_18001E486
0x18001e447  mov     ecx, 80070057h; int
0x18001e44c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e452  mov     [rbp+arg_0], 80004005h
0x18001e459  test    rsi, rsi
0x18001e45c  jz      loc_18001E4E5
0x18001e462  mov     rcx, rsi; this
0x18001e465  call    ?Release@CDShowTransSample@@UEAAKXZ; CDShowTransSample::Release(void)
0x18001e46a  jmp     short loc_18001E4E5
0x18001e46c  mov     rsi, r13
0x18001e46f  jmp     loc_18001E3C5
0x18001e474  inc     dword ptr [r15+5Ch]
0x18001e478  jmp     short loc_18001E430
0x18001e47a  mov     [rbp+arg_0], 80004005h
0x18001e481  jmp     loc_18001E51C
0x18001e486  mov     rax, [rax+0C0h]
0x18001e48d  mov     rcx, [rax]
0x18001e490  mov     rdi, [rcx+38h]
0x18001e494  lea     rcx, [rdi+58h]; SRWLock
0x18001e498  call    cs:__imp_AcquireSRWLockShared
0x18001e49f  nop     dword ptr [rax+rax+00h]
0x18001e4a4  mov     rbx, [rdi+70h]
0x18001e4a8  lea     rcx, [rdi+58h]; SRWLock
0x18001e4ac  call    cs:__imp_ReleaseSRWLockShared
0x18001e4b3  nop     dword ptr [rax+rax+00h]
0x18001e4b8  nop
0x18001e4b9  cmp     rbx, 1
0x18001e4bd  jnb     short loc_18001E4DB
0x18001e4bf  mov     r8d, 1; unsigned int
0x18001e4c5  mov     rdx, r15; struct CDShowTransRoot *
0x18001e4c8  mov     rcx, r14; this
0x18001e4cb  call    ?RequestInputSamples@CDShowTransOutputPin@@QEAAJPEAVCDShowTransRoot@@K@Z; CDShowTransOutputPin::RequestInputSamples(CDShowTransRoot *,ulong)
0x18001e4d0  mov     [rbp+arg_0], eax
0x18001e4d3  test    eax, eax
0x18001e4d5  js      loc_18001E7EE
0x18001e4db  cmp     [rbp+arg_0], 0
0x18001e4df  jl      loc_18001E459
0x18001e4e5  test    r15, r15
0x18001e4e8  jz      short loc_18001E515
0x18001e4ea  mov     rbx, [r14+30h]
0x18001e4ee  call    cs:__imp_GetCurrentThreadId
0x18001e4f5  nop     dword ptr [rax+rax+00h]
0x18001e4fa  mov     edx, [rbx+58h]
0x18001e4fd  lea     rcx, [rbx+50h]; this
0x18001e501  cmp     edx, eax
0x18001e503  jz      loc_18001E5DC
0x18001e509  call    cs:__imp_ReleaseSRWLockShared
0x18001e510  nop     dword ptr [rax+rax+00h]
0x18001e515  lea     r15, qword_1800EB130
0x18001e51c  mov     esi, [rbp+arg_0]
0x18001e51f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e526  cmp     byte ptr [rdi+8], 0
0x18001e52a  jz      loc_18001E5C1
0x18001e530  lea     rbx, [rdi+0D0h]
0x18001e537  call    cs:__imp_GetLastError
0x18001e53e  nop     dword ptr [rax+rax+00h]
0x18001e543  mov     r14d, eax
0x18001e546  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001e549  call    cs:__imp_TlsGetValue
0x18001e550  nop     dword ptr [rax+rax+00h]
0x18001e555  test    rax, rax
0x18001e558  jz      loc_18001E622
0x18001e55e  mov     rbx, rax
0x18001e561  mov     ecx, r14d; dwErrCode
0x18001e564  call    cs:__imp_SetLastError
0x18001e56b  nop     dword ptr [rax+rax+00h]
0x18001e570  mov     eax, [rbx+7C4h]
0x18001e576  test    eax, eax
0x18001e578  jz      short loc_18001E5C1
0x18001e57a  sub     eax, 1
0x18001e57d  mov     [rbx+7C4h], eax
0x18001e583  jnz     short loc_18001E5C1
0x18001e585  mov     [rbx+7C4h], r13d
0x18001e58c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001e593  movups  xmmword ptr [rbx+7D0h], xmm0
0x18001e59a  mov     [rbx+7E0h], r13
0x18001e5a1  mov     [rbx+7CCh], r13d
0x18001e5a8  mov     [rbx+7E8h], r13d
0x18001e5af  call    cs:__imp_GetCurrentThreadId
0x18001e5b6  nop     dword ptr [rax+rax+00h]
0x18001e5bb  mov     [rbx+7C0h], eax
0x18001e5c1  mov     eax, esi
0x18001e5c3  mov     rbx, [rsp+50h+arg_8]
0x18001e5cb  add     rsp, 50h
0x18001e5cf  pop     r15
0x18001e5d1  pop     r14
0x18001e5d3  pop     r13
0x18001e5d5  pop     r12
0x18001e5d7  pop     rdi
0x18001e5d8  pop     rsi
0x18001e5d9  pop     rbp
0x18001e5da  retn
0x18001e5dc  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18001e5e1  nop
0x18001e5e2  jmp     loc_18001E515
0x18001e5e7  call    cs:__imp_GetLastError
0x18001e5ee  nop     dword ptr [rax+rax+00h]
0x18001e5f3  test    eax, eax
0x18001e5f5  jnz     loc_18001E28C
0x18001e5fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e602  test    rcx, rcx
0x18001e605  jz      loc_18001E889
0x18001e60b  mov     rax, [rcx]
0x18001e60e  mov     rax, [rax]
0x18001e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e616  test    rax, rax
0x18001e619  cmovnz  rbx, rax
0x18001e61d  jmp     loc_18001E28C
0x18001e622  call    cs:__imp_GetLastError
0x18001e629  nop     dword ptr [rax+rax+00h]
0x18001e62e  test    eax, eax
0x18001e630  jnz     loc_18001E561
0x18001e636  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e63d  test    rcx, rcx
0x18001e640  jz      loc_18001E8EA
0x18001e646  mov     rax, [rcx]
0x18001e649  mov     rax, [rax]
0x18001e64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e651  test    rax, rax
0x18001e654  cmovnz  rbx, rax
0x18001e658  jmp     loc_18001E561
0x18001e65d  mov     rcx, rdi; this
0x18001e660  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e665  mov     r9d, [rbp+arg_0]; int
0x18001e669  test    r9d, r9d
0x18001e66c  jns     loc_18001E76A
0x18001e672  cmp     [rax+7CCh], r9d
0x18001e679  jz      loc_18001E76A
0x18001e67f  mov     r8d, 4A6h; int
0x18001e685  lea     rdx, aCdshowtransout_0; "CDShowTransOutputPin::DeliverSample"
0x18001e68c  mov     rcx, rax; this
0x18001e68f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e694  jmp     loc_18001E76A
0x18001e699  mov     rcx, rdi; this
0x18001e69c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e6a1  mov     r9d, [rbp+arg_0]; int
0x18001e6a5  test    r9d, r9d
0x18001e6a8  jns     loc_18001E7DA
0x18001e6ae  cmp     [rax+7CCh], r9d
0x18001e6b5  jz      loc_18001E7DA
0x18001e6bb  mov     r8d, 4ACh; int
0x18001e6c1  lea     rdx, aCdshowtransout_0; "CDShowTransOutputPin::DeliverSample"
0x18001e6c8  mov     rcx, rax; this
0x18001e6cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e6d0  jmp     loc_18001E7DA
0x18001e6d5  mov     rcx, rdi; this
0x18001e6d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e6dd  mov     r9d, [rbp+arg_0]; int
0x18001e6e1  test    r9d, r9d
0x18001e6e4  jns     loc_18001E847
0x18001e6ea  cmp     [rax+7CCh], r9d
0x18001e6f1  jz      loc_18001E847
0x18001e6f7  mov     r8d, 4BFh; int
0x18001e6fd  lea     rdx, aCdshowtransout_0; "CDShowTransOutputPin::DeliverSample"
0x18001e704  mov     rcx, rax; this
0x18001e707  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e70c  jmp     loc_18001E847
0x18001e711  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e719  jnz     short loc_18001E759
0x18001e71b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001e722  nop     dword ptr [rax+rax+00h]
0x18001e727  mov     rcx, rax
0x18001e72a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e731  test    rax, rax
0x18001e734  jz      short loc_18001E74B
0x18001e736  mov     rax, [rax]
0x18001e739  mov     edx, 7F0h
0x18001e73e  mov     rax, [rax+8]
  ... truncated ...
```
