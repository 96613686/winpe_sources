# CWAVEStreamSink::ProcessSample(IMFSample *)

- ea: `0x180046ae0`
- end: `0x180047204`
- name: `?ProcessSample@CWAVEStreamSink@@UEAAJPEAUIMFSample@@@Z`
- size: `1828`
- prototype: `__int64 __fastcall(CWAVEStreamSink *__hidden this, struct IMFSample *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180036c30`
- `0x180046ae0`
- `0x18004720c`
- `0x180077708`
- `0x180079680`
- `0x1801240f8`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046cbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046cbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046b69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046b69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046da2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046da2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e68`

## string_xrefs

- `0x180046b10`: `CWAVEStreamSink::ProcessSample`
- `0x180046f2c`: `CWAVEStreamSink::ProcessSample`
- `0x180046f5b`: `CWAVEStreamSink::ProcessSample`
- `0x180046f89`: `CWAVEStreamSink::ProcessSample`
- `0x180046fb7`: `CWAVEStreamSink::ProcessSample`

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
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v27 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v23 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v25 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v29 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v21 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180046ae0  mov     [rsp-38h+arg_8], rbx
0x180046ae5  push    rbp
0x180046ae6  push    rsi
0x180046ae7  push    rdi
0x180046ae8  push    r12
0x180046aea  push    r13
0x180046aec  push    r14
0x180046aee  push    r15
0x180046af0  mov     rbp, rsp
0x180046af3  sub     rsp, 40h
0x180046af7  mov     rsi, rcx
0x180046afa  xor     r13d, r13d
0x180046afd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180046b04  mov     r12, rdx
0x180046b07  test    rcx, rcx
0x180046b0a  jz      loc_180046CEF
0x180046b10  lea     r14, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180046b17  cmp     [rcx+8], r13b
0x180046b1b  jz      short loc_180046B45
0x180046b1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046b22  mov     ecx, [rax+7C4h]
0x180046b28  cmp     ecx, [rax+7C8h]
0x180046b2e  jnb     short loc_180046B3F
0x180046b30  add     rcx, rcx
0x180046b33  mov     [rax+rcx*8], r14
0x180046b37  mov     dword ptr [rax+rcx*8+8], 7Dh ; '}'
0x180046b3f  inc     dword ptr [rax+7C4h]
0x180046b45  mov     rax, 7FFFFFFFFFFFFFFFh
0x180046b4f  mov     [rbp+var_8], r13
0x180046b53  lea     rbx, [rsi+188h]
0x180046b5a  mov     [rbp+arg_10], r13d
0x180046b5e  mov     rcx, rbx; lpCriticalSection
0x180046b61  mov     [rbp+arg_18], r13d
0x180046b65  mov     [rbp+var_10], rax
0x180046b69  call    cs:__imp_EnterCriticalSection
0x180046b70  nop     dword ptr [rax+rax+00h]
0x180046b75  mov     rdx, r12; struct IMFSample *
0x180046b78  mov     rcx, rsi; this
0x180046b7b  call    ?ProcessSample@CBaseStreamSink@@UEAAJPEAUIMFSample@@@Z; CBaseStreamSink::ProcessSample(IMFSample *)
0x180046b80  lea     r15, [rsi-10h]
0x180046b84  mov     edi, eax
0x180046b86  test    eax, eax
0x180046b88  js      loc_180046C99
0x180046b8e  mov     rax, [r12]
0x180046b92  lea     rdx, [rbp+arg_18]
0x180046b96  mov     rcx, r12
0x180046b99  mov     rax, [rax+138h]
0x180046ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ba5  mov     edi, eax
0x180046ba7  test    eax, eax
0x180046ba9  js      loc_180046D0E
0x180046baf  cmp     [r15+2ACh], r13d
0x180046bb6  jnz     loc_18004703E
0x180046bbc  cmp     [rsi+1B0h], r13
0x180046bc3  jz      loc_18004706D
0x180046bc9  mov     r14d, r13d
0x180046bcc  cmp     r13d, [rbp+arg_18]
0x180046bd0  jnb     loc_180046CBC
0x180046bd6  mov     rax, [r12]
0x180046bda  lea     r8, [rbp+arg_0]
0x180046bde  mov     edx, r13d
0x180046be1  mov     [rbp+arg_0], 0
0x180046be9  mov     rcx, r12
0x180046bec  mov     rax, [rax+140h]
0x180046bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bf8  mov     edi, eax
0x180046bfa  test    eax, eax
0x180046bfc  js      loc_180046E58
0x180046c02  mov     rcx, [rbp+arg_0]
0x180046c06  lea     r9, [rbp+arg_10]
0x180046c0a  xor     r8d, r8d
0x180046c0d  lea     rdx, [rbp+var_8]
0x180046c11  mov     rax, [rcx]
0x180046c14  mov     rax, [rax+18h]
0x180046c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c1d  mov     edi, eax
0x180046c1f  test    eax, eax
0x180046c21  js      loc_180046E16
0x180046c27  mov     edx, [rbp+arg_10]
0x180046c2a  test    edx, edx
0x180046c2c  jz      short loc_180046C5E
0x180046c2e  mov     rcx, [rsi+170h]
0x180046c35  lea     r9, [rsi+158h]
0x180046c3c  mov     r10, [rbp+arg_0]
0x180046c40  mov     r8d, edx
0x180046c43  mov     rdx, [rbp+var_8]
0x180046c47  mov     [rsp+40h+var_20], r10
0x180046c4c  mov     rax, [rcx]
0x180046c4f  mov     rax, [rax+68h]
0x180046c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c58  mov     edx, [rbp+arg_10]
0x180046c5b  mov     r14d, eax
0x180046c5e  test    r14d, r14d
0x180046c61  js      loc_1800470C0
0x180046c67  mov     eax, edx
0x180046c69  mov     edi, r14d
0x180046c6c  add     [rsi+1B0h], rax
0x180046c73  test    r14d, r14d
0x180046c76  js      loc_180046DD4
0x180046c7c  mov     rcx, [rbp+arg_0]
0x180046c80  test    rcx, rcx
0x180046c83  jz      short loc_180046C91
0x180046c85  mov     rax, [rcx]
0x180046c88  mov     rax, [rax+10h]
0x180046c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c91  inc     r13d
0x180046c94  jmp     loc_180046BCC
0x180046c99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180046ca0  test    rcx, rcx
0x180046ca3  jz      short loc_180046D00
0x180046ca5  cmp     [rcx+8], r13b
0x180046ca9  jnz     loc_180046E9A
0x180046caf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046cb6  jnb     loc_180046FD1
0x180046cbc  mov     rcx, rbx; lpCriticalSection
0x180046cbf  call    cs:__imp_LeaveCriticalSection
0x180046cc6  nop     dword ptr [rax+rax+00h]
0x180046ccb  lea     rcx, [rbp+arg_0]; this
0x180046ccf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180046cd4  mov     rbx, [rsp+40h+arg_8]
0x180046cdc  mov     eax, edi
0x180046cde  add     rsp, 40h
0x180046ce2  pop     r15
0x180046ce4  pop     r14
0x180046ce6  pop     r13
0x180046ce8  pop     r12
0x180046cea  pop     rdi
0x180046ceb  pop     rsi
0x180046cec  pop     rbp
0x180046ced  retn
0x180046cef  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180046cf4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cfb  jmp     loc_180046B10
0x180046d00  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180046d05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d0c  jmp     short loc_180046CA5
0x180046d0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d15  test    rcx, rcx
0x180046d18  jnz     loc_180047020
0x180046d1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046d25  nop     dword ptr [rax+rax+00h]
0x180046d2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d31  mov     rcx, rax
0x180046d34  test    rax, rax
0x180046d37  jnz     loc_180047000
0x180046d3d  lea     rcx, qword_1801B97E0
0x180046d44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d4b  jmp     loc_180047020
0x180046d50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d57  test    rcx, rcx
0x180046d5a  jnz     loc_1800470A4
0x180046d60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046d67  nop     dword ptr [rax+rax+00h]
0x180046d6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d73  mov     rcx, rax
0x180046d76  test    rax, rax
0x180046d79  jnz     loc_180047084
0x180046d7f  lea     rcx, qword_1801B97E0
0x180046d86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d8d  jmp     loc_1800470A4
0x180046d92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d99  test    rcx, rcx
0x180046d9c  jnz     loc_180047102
0x180046da2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046da9  nop     dword ptr [rax+rax+00h]
0x180046dae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046db5  mov     rcx, rax
0x180046db8  test    rax, rax
0x180046dbb  jnz     loc_1800470E2
0x180046dc1  lea     rcx, qword_1801B97E0
0x180046dc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046dcf  jmp     loc_180047102
0x180046dd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ddb  test    rcx, rcx
0x180046dde  jnz     loc_180047143
0x180046de4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046deb  nop     dword ptr [rax+rax+00h]
0x180046df0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046df7  mov     rcx, rax
0x180046dfa  test    rax, rax
0x180046dfd  jnz     loc_180047123
0x180046e03  lea     rcx, qword_1801B97E0
0x180046e0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e11  jmp     loc_180047143
0x180046e16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e1d  test    rcx, rcx
0x180046e20  jnz     loc_180047186
0x180046e26  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046e2d  nop     dword ptr [rax+rax+00h]
0x180046e32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e39  mov     rcx, rax
0x180046e3c  test    rax, rax
0x180046e3f  jnz     loc_180047166
0x180046e45  lea     rcx, qword_1801B97E0
0x180046e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e53  jmp     loc_180047186
0x180046e58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e5f  test    rcx, rcx
0x180046e62  jnz     loc_1800471C0
0x180046e68  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046e6f  nop     dword ptr [rax+rax+00h]
0x180046e74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e7b  mov     rcx, rax
0x180046e7e  test    rax, rax
0x180046e81  jnz     loc_1800471A0
0x180046e87  lea     rcx, qword_1801B97E0
0x180046e8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e95  jmp     loc_1800471C0
0x180046e9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046e9f  cmp     [rax+7CCh], edi
0x180046ea5  jz      loc_180046CAF
0x180046eab  mov     r9d, edi; int
0x180046eae  mov     r8d, 88h; int
0x180046eb4  mov     rdx, r14; char *
0x180046eb7  mov     rcx, rax; this
0x180046eba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046ebf  jmp     loc_180046CAF
0x180046ec4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046ec9  cmp     [rax+7CCh], edi
0x180046ecf  jz      loc_18004702A
0x180046ed5  mov     r9d, edi; int
0x180046ed8  mov     r8d, 8Ah; int
0x180046ede  mov     rdx, r14; char *
0x180046ee1  mov     rcx, rax; this
0x180046ee4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046ee9  jmp     loc_18004702A
0x180046eee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046ef3  cmp     [rax+7CCh], edi
0x180046ef9  jz      loc_1800470AE
0x180046eff  mov     r9d, edi; int
0x180046f02  mov     r8d, 97h; int
0x180046f08  mov     rdx, r14; char *
0x180046f0b  mov     rcx, rax; this
0x180046f0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046f13  jmp     loc_1800470AE
0x180046f18  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046f1d  cmp     [rax+7CCh], edi
0x180046f23  jz      loc_18004710C
0x180046f29  mov     r9d, edi; int
0x180046f2c  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180046f33  mov     r8d, 0AAh; int
0x180046f39  mov     rcx, rax; this
0x180046f3c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046f41  jmp     loc_18004710C
0x180046f46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046f4b  cmp     [rax+7CCh], r14d
0x180046f52  jz      loc_18004714D
0x180046f58  mov     r9d, r14d; int
0x180046f5b  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180046f62  mov     r8d, 0B0h; int
0x180046f68  mov     rcx, rax; this
0x180046f6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046f70  jmp     loc_18004714D
0x180046f75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046f7a  cmp     [rax+7CCh], edi
0x180046f80  jz      loc_180047190
0x180046f86  mov     r9d, edi; int
0x180046f89  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180046f90  mov     r8d, 0A0h; int
0x180046f96  mov     rcx, rax; this
0x180046f99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046f9e  jmp     loc_180047190
0x180046fa3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046fa8  cmp     [rax+7CCh], edi
0x180046fae  jz      loc_1800471CA
0x180046fb4  mov     r9d, edi; int
0x180046fb7  lea     rdx, aCwavestreamsin_0; "CWAVEStreamSink::ProcessSample"
0x180046fbe  mov     r8d, 9Eh; int
0x180046fc4  mov     rcx, rax; this
0x180046fc7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046fcc  jmp     loc_1800471CA
0x180046fd1  mov     edx, 17h
0x180046fd6  jmp     short loc_180046FDD
0x180046fd8  mov     edx, 19h
0x180046fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180046fe4  lea     r8, WPP_8d3eff03cff836abfd6e8e500f4dc29e_Traceguids
0x180046feb  mov     r9, r15
0x180046fee  mov     dword ptr [rsp+40h+var_20], edi
0x180046ff2  mov     rcx, [rcx+10h]
0x180046ff6  call    WPP_SF_qD
0x180046ffb  jmp     loc_180046CBC
0x180047000  mov     rax, [rax]
0x180047003  mov     edx, 7F0h
0x180047008  mov     rax, [rax+8]
0x18004700c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047011  test    eax, eax
0x180047013  jz      loc_180046D3D
0x180047019  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180047020  cmp     [rcx+8], r13b
0x180047024  jnz     loc_180046EC4
0x18004702a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180047031  jb      loc_180046CBC
0x180047037  mov     edx, 18h
0x18004703c  jmp     short loc_180046FDD
0x18004703e  mov     rax, [r12]
0x180047042  lea     rdx, [rbp+var_10]
0x180047046  mov     rcx, r12
0x180047049  mov     rax, [rax+128h]
0x180047050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047055  test    eax, eax
  ... truncated ...
```
