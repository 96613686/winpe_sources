# CWAVEStreamSink::ProcessSample(IMFSample *)

- ea: `0x1800435a0`
- end: `0x180043c93`
- name: `?ProcessSample@CWAVEStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `1779`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180034d10`
- `0x1800435a0`
- `0x180043c9c`
- `0x180071a44`
- `0x180073b14`
- `0x18011da38`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043779`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043779`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043629`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043629`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800437d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004380d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800438c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800438fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800437d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004380d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043849`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800438c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800438fd`

## string_xrefs

- `0x1800435d0`: `CWAVEStreamSink::ProcessSample`
- `0x1800439bb`: `CWAVEStreamSink::ProcessSample`
- `0x1800439ea`: `CWAVEStreamSink::ProcessSample`
- `0x180043a18`: `CWAVEStreamSink::ProcessSample`
- `0x180043a46`: `CWAVEStreamSink::ProcessSample`

## pseudocode

```c
__int64 __fastcall CWAVEStreamSink::ProcessSample(CWAVEStreamSink *this, struct IMFSample *a2)
{
  unsigned int v3; // r13d
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // rdx
  int v11; // r14d
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // eax
  CallStackTracing *v17; // rcx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  struct CallStackContext *v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // [rsp+30h] [rbp-10h] BYREF
  __int64 v43; // [rsp+38h] [rbp-8h] BYREF
  __int64 v44; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v45; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v46; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
    v7 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v7 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v8 = 2 * v7;
      *((_QWORD *)ThreadRelativeContext + v8) = "CWAVEStreamSink::ProcessSample";
      *((_DWORD *)ThreadRelativeContext + 2 * v8 + 2) = 125;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v43 = 0;
  v45 = 0;
  v46 = 0;
  v42 = 0x7FFFFFFFFFFFFFFFLL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  v9 = CBaseStreamSink::ProcessSample(this, a2);
  if ( v9 < 0 )
  {
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v17 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(v17);
      if ( *((_DWORD *)v31 + 499) != v9 )
        CallStackContext::TraceFailure(v31, "CWAVEStreamSink::ProcessSample", 136, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_26;
    v38 = 23;
LABEL_60:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v38,
      WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids,
      (char *)this - 16,
      v9);
    goto LABEL_26;
  }
  v9 = ((__int64 (__fastcall *)(struct IMFSample *, unsigned int *))a2->lpVtbl->GetBufferCount)(a2, &v46);
  if ( v9 < 0 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v32 + 499) != v9 )
        CallStackContext::TraceFailure(v32, "CWAVEStreamSink::ProcessSample", 138, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_26;
    v38 = 24;
    goto LABEL_60;
  }
  if ( *((_DWORD *)this + 167)
    && !((unsigned int (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleDuration)(a2, &v42) )
  {
    *((_QWORD *)this + 56) += v42;
  }
  if ( *((_QWORD *)this + 54) || (v9 = CWAVEStreamSink::WAVEHeaderWrite((CRIFFMetadata **)this - 2), v9 >= 0) )
  {
    v11 = 0;
    while ( 1 )
    {
      if ( v3 >= v46 )
        goto LABEL_26;
      lpVtbl = a2->lpVtbl;
      v44 = 0;
      v9 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, __int64 *))lpVtbl->GetBufferByIndex)(a2, v3, &v44);
      if ( v9 < 0 )
        break;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v44 + 24LL))(
             v44,
             &v43,
             0,
             &v45);
      if ( v9 < 0 )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v36 + 499) != v9 )
            CallStackContext::TraceFailure(v36, "CWAVEStreamSink::ProcessSample", 160, v9);
        }
        if ( !g_wppLevels )
          goto LABEL_98;
        v41 = 27;
        goto LABEL_97;
      }
      v15 = v45;
      if ( v45 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, char *, __int64))(**((_QWORD **)this + 46) + 104LL))(
                *((_QWORD *)this + 46),
                v43,
                v45,
                (char *)this + 344,
                v44);
        v15 = v45;
        v11 = v16;
      }
      if ( v11 < 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 32LL))(v44);
        if ( v9 < 0 )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v34 + 499) != v9 )
              CallStackContext::TraceFailure(v34, "CWAVEStreamSink::ProcessSample", 170, v9);
          }
          if ( g_wppLevels )
          {
            v41 = 28;
            goto LABEL_97;
          }
LABEL_98:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v44);
          goto LABEL_26;
        }
        v15 = v45;
      }
      v9 = v11;
      *((_QWORD *)this + 54) += (unsigned int)v15;
      if ( v11 < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v35 + 499) != v11 )
            CallStackContext::TraceFailure(v35, "CWAVEStreamSink::ProcessSample", 176, v11);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids,
            (char *)this - 16,
            v11);
        goto LABEL_98;
      }
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      ++v3;
    }
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v37 + 499) != v9 )
        CallStackContext::TraceFailure(v37, "CWAVEStreamSink::ProcessSample", 158, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_98;
    v41 = 26;
LABEL_97:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v41,
      WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids,
      (char *)this - 16,
      v9);
    goto LABEL_98;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v33 + 499) != v9 )
      CallStackContext::TraceFailure(v33, "CWAVEStreamSink::ProcessSample", 151, v9);
  }
  if ( g_wppLevels )
  {
    v38 = 25;
    goto LABEL_60;
  }
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800435a0  mov     [rsp-38h+arg_8], rbx
0x1800435a5  push    rbp
0x1800435a6  push    rsi
0x1800435a7  push    rdi
0x1800435a8  push    r12
0x1800435aa  push    r13
0x1800435ac  push    r14
0x1800435ae  push    r15
0x1800435b0  mov     rbp, rsp
0x1800435b3  sub     rsp, 40h
0x1800435b7  mov     rsi, rcx
0x1800435ba  xor     r13d, r13d
0x1800435bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800435c4  mov     r12, rdx
0x1800435c7  test    rcx, rcx
0x1800435ca  jz      loc_1800437A2
0x1800435d0  lea     r14, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x1800435d7  cmp     [rcx+8], r13b
0x1800435db  jz      short loc_180043605
0x1800435dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800435e2  mov     ecx, [rax+7C4h]
0x1800435e8  cmp     ecx, [rax+7C8h]
0x1800435ee  jnb     short loc_1800435FF
0x1800435f0  add     rcx, rcx
0x1800435f3  mov     [rax+rcx*8], r14
0x1800435f7  mov     dword ptr [rax+rcx*8+8], 7Dh ; '}'
0x1800435ff  inc     dword ptr [rax+7C4h]
0x180043605  mov     rax, 7FFFFFFFFFFFFFFFh
0x18004360f  mov     [rbp+var_8], r13
0x180043613  lea     rbx, [rsi+188h]
0x18004361a  mov     [rbp+arg_10], r13d
0x18004361e  mov     rcx, rbx; lpCriticalSection
0x180043621  mov     [rbp+arg_18], r13d
0x180043625  mov     [rbp+var_10], rax
0x180043629  call    cs:__imp_EnterCriticalSection
0x18004362f  mov     rdx, r12; struct IMFSample *
0x180043632  mov     rcx, rsi; this
0x180043635  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x18004363a  lea     r15, [rsi-10h]
0x18004363e  mov     edi, eax
0x180043640  test    eax, eax
0x180043642  js      loc_180043753
0x180043648  mov     rax, [r12]
0x18004364c  lea     rdx, [rbp+arg_18]
0x180043650  mov     rcx, r12
0x180043653  mov     rax, [rax+138h]
0x18004365a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004365f  mov     edi, eax
0x180043661  test    eax, eax
0x180043663  js      loc_1800437C1
0x180043669  cmp     [r15+2ACh], r13d
0x180043670  jnz     loc_180043ACD
0x180043676  cmp     [rsi+1B0h], r13
0x18004367d  jz      loc_180043AFC
0x180043683  mov     r14d, r13d
0x180043686  cmp     r13d, [rbp+arg_18]
0x18004368a  jnb     loc_180043776
0x180043690  mov     rax, [r12]
0x180043694  lea     r8, [rbp+arg_0]
0x180043698  mov     edx, r13d
0x18004369b  mov     [rbp+arg_0], 0
0x1800436a3  mov     rcx, r12
0x1800436a6  mov     rax, [rax+140h]
0x1800436ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b2  mov     edi, eax
0x1800436b4  test    eax, eax
0x1800436b6  js      loc_1800438ED
0x1800436bc  mov     rcx, [rbp+arg_0]
0x1800436c0  lea     r9, [rbp+arg_10]
0x1800436c4  xor     r8d, r8d
0x1800436c7  lea     rdx, [rbp+var_8]
0x1800436cb  mov     rax, [rcx]
0x1800436ce  mov     rax, [rax+18h]
0x1800436d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436d7  mov     edi, eax
0x1800436d9  test    eax, eax
0x1800436db  js      loc_1800438B1
0x1800436e1  mov     edx, [rbp+arg_10]
0x1800436e4  test    edx, edx
0x1800436e6  jz      short loc_180043718
0x1800436e8  mov     rcx, [rsi+170h]
0x1800436ef  lea     r9, [rsi+158h]
0x1800436f6  mov     r10, [rbp+arg_0]
0x1800436fa  mov     r8d, edx
0x1800436fd  mov     rdx, [rbp+var_8]
0x180043701  mov     [rsp+40h+var_20], r10
0x180043706  mov     rax, [rcx]
0x180043709  mov     rax, [rax+68h]
0x18004370d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043712  mov     edx, [rbp+arg_10]
0x180043715  mov     r14d, eax
0x180043718  test    r14d, r14d
0x18004371b  js      loc_180043B4F
0x180043721  mov     eax, edx
0x180043723  mov     edi, r14d
0x180043726  add     [rsi+1B0h], rax
0x18004372d  test    r14d, r14d
0x180043730  js      loc_180043875
0x180043736  mov     rcx, [rbp+arg_0]
0x18004373a  test    rcx, rcx
0x18004373d  jz      short loc_18004374B
0x18004373f  mov     rax, [rcx]
0x180043742  mov     rax, [rax+10h]
0x180043746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004374b  inc     r13d
0x18004374e  jmp     loc_180043686
0x180043753  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004375a  test    rcx, rcx
0x18004375d  jz      short loc_1800437B3
0x18004375f  cmp     [rcx+8], r13b
0x180043763  jnz     loc_180043929
0x180043769  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043770  jnb     loc_180043A60
0x180043776  mov     rcx, rbx; lpCriticalSection
0x180043779  call    cs:__imp_LeaveCriticalSection
0x18004377f  lea     rcx, [rbp+arg_0]; this
0x180043783  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180043788  mov     rbx, [rsp+40h+arg_8]
0x180043790  mov     eax, edi
0x180043792  add     rsp, 40h
0x180043796  pop     r15
0x180043798  pop     r14
0x18004379a  pop     r13
0x18004379c  pop     r12
0x18004379e  pop     rdi
0x18004379f  pop     rsi
0x1800437a0  pop     rbp
0x1800437a1  retn
0x1800437a2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800437a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437ae  jmp     loc_1800435D0
0x1800437b3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800437b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437bf  jmp     short loc_18004375F
0x1800437c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437c8  test    rcx, rcx
0x1800437cb  jnz     loc_180043AAF
0x1800437d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800437d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437de  mov     rcx, rax
0x1800437e1  test    rax, rax
0x1800437e4  jnz     loc_180043A8F
0x1800437ea  lea     rcx, qword_1801B07E0
0x1800437f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800437f8  jmp     loc_180043AAF
0x1800437fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043804  test    rcx, rcx
0x180043807  jnz     loc_180043B33
0x18004380d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043813  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004381a  mov     rcx, rax
0x18004381d  test    rax, rax
0x180043820  jnz     loc_180043B13
0x180043826  lea     rcx, qword_1801B07E0
0x18004382d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043834  jmp     loc_180043B33
0x180043839  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043840  test    rcx, rcx
0x180043843  jnz     loc_180043B91
0x180043849  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004384f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043856  mov     rcx, rax
0x180043859  test    rax, rax
0x18004385c  jnz     loc_180043B71
0x180043862  lea     rcx, qword_1801B07E0
0x180043869  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043870  jmp     loc_180043B91
0x180043875  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004387c  test    rcx, rcx
0x18004387f  jnz     loc_180043BD2
0x180043885  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004388b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043892  mov     rcx, rax
0x180043895  test    rax, rax
0x180043898  jnz     loc_180043BB2
0x18004389e  lea     rcx, qword_1801B07E0
0x1800438a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800438ac  jmp     loc_180043BD2
0x1800438b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800438b8  test    rcx, rcx
0x1800438bb  jnz     loc_180043C15
0x1800438c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800438c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800438ce  mov     rcx, rax
0x1800438d1  test    rax, rax
0x1800438d4  jnz     loc_180043BF5
0x1800438da  lea     rcx, qword_1801B07E0
0x1800438e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800438e8  jmp     loc_180043C15
0x1800438ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800438f4  test    rcx, rcx
0x1800438f7  jnz     loc_180043C4F
0x1800438fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043903  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004390a  mov     rcx, rax
0x18004390d  test    rax, rax
0x180043910  jnz     loc_180043C2F
0x180043916  lea     rcx, qword_1801B07E0
0x18004391d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043924  jmp     loc_180043C4F
0x180043929  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004392e  cmp     [rax+7CCh], edi
0x180043934  jz      loc_180043769
0x18004393a  mov     r9d, edi; int
0x18004393d  mov     r8d, 88h; int
0x180043943  mov     rdx, r14; char *
0x180043946  mov     rcx, rax; this
0x180043949  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004394e  jmp     loc_180043769
0x180043953  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043958  cmp     [rax+7CCh], edi
0x18004395e  jz      loc_180043AB9
0x180043964  mov     r9d, edi; int
0x180043967  mov     r8d, 8Ah; int
0x18004396d  mov     rdx, r14; char *
0x180043970  mov     rcx, rax; this
0x180043973  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043978  jmp     loc_180043AB9
0x18004397d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043982  cmp     [rax+7CCh], edi
0x180043988  jz      loc_180043B3D
0x18004398e  mov     r9d, edi; int
0x180043991  mov     r8d, 97h; int
0x180043997  mov     rdx, r14; char *
0x18004399a  mov     rcx, rax; this
0x18004399d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800439a2  jmp     loc_180043B3D
0x1800439a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800439ac  cmp     [rax+7CCh], edi
0x1800439b2  jz      loc_180043B9B
0x1800439b8  mov     r9d, edi; int
0x1800439bb  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x1800439c2  mov     r8d, 0AAh; int
0x1800439c8  mov     rcx, rax; this
0x1800439cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800439d0  jmp     loc_180043B9B
0x1800439d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800439da  cmp     [rax+7CCh], r14d
0x1800439e1  jz      loc_180043BDC
0x1800439e7  mov     r9d, r14d; int
0x1800439ea  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x1800439f1  mov     r8d, 0B0h; int
0x1800439f7  mov     rcx, rax; this
0x1800439fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800439ff  jmp     loc_180043BDC
0x180043a04  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043a09  cmp     [rax+7CCh], edi
0x180043a0f  jz      loc_180043C1F
0x180043a15  mov     r9d, edi; int
0x180043a18  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180043a1f  mov     r8d, 0A0h; int
0x180043a25  mov     rcx, rax; this
0x180043a28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043a2d  jmp     loc_180043C1F
0x180043a32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043a37  cmp     [rax+7CCh], edi
0x180043a3d  jz      loc_180043C59
0x180043a43  mov     r9d, edi; int
0x180043a46  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180043a4d  mov     r8d, 9Eh; int
0x180043a53  mov     rcx, rax; this
0x180043a56  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043a5b  jmp     loc_180043C59
0x180043a60  mov     edx, 17h
0x180043a65  jmp     short loc_180043A6C
0x180043a67  mov     edx, 19h
0x180043a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a73  lea     r8, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x180043a7a  mov     r9, r15
0x180043a7d  mov     dword ptr [rsp+40h+var_20], edi
0x180043a81  mov     rcx, [rcx+10h]
0x180043a85  call    WPP_SF_qD
0x180043a8a  jmp     loc_180043776
0x180043a8f  mov     rax, [rax]
0x180043a92  mov     edx, 7F0h
0x180043a97  mov     rax, [rax+8]
0x180043a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043aa0  test    eax, eax
0x180043aa2  jz      loc_1800437EA
0x180043aa8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180043aaf  cmp     [rcx+8], r13b
0x180043ab3  jnz     loc_180043953
0x180043ab9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043ac0  jb      loc_180043776
0x180043ac6  mov     edx, 18h
0x180043acb  jmp     short loc_180043A6C
0x180043acd  mov     rax, [r12]
0x180043ad1  lea     rdx, [rbp+var_10]
0x180043ad5  mov     rcx, r12
0x180043ad8  mov     rax, [rax+128h]
0x180043adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ae4  test    eax, eax
0x180043ae6  jnz     loc_180043676
0x180043aec  mov     rax, [rbp+var_10]
0x180043af0  add     [rsi+1C0h], rax
0x180043af7  jmp     loc_180043676
0x180043afc  mov     rcx, r15; this
0x180043aff  call    ?WAVEHeaderWrite@CWAVEStreamSink@@AEAAJXZ; CWAVEStreamSink::WAVEHeaderWrite(void)
0x180043b04  mov     edi, eax
0x180043b06  test    eax, eax
  ... truncated ...
```
