# CMFSourceReaderStream::OnSourceSampleAvailable(IMFSample *,__int64,ulong *)

- ea: `0x180024220`
- end: `0x180024af0`
- name: `?OnSourceSampleAvailable@CMFSourceReaderStream@@AEAAJPEAUIMFSample@@_JPEAK@Z`
- size: `2256`
- prototype: `__int64 __fastcall(CMFSourceReaderStream *__hidden this, struct IMFSample *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800214f0`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x180024220`
- `0x1800252a0`
- `0x180025384`
- `0x180045594`
- `0x18006c1b0`
- `0x18007b670`
- `0x1800acd2c`
- `0x1800ef0a0`
- `0x1800ef100`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002442f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002466f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002442f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002466f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002439f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002467b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800247cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180024899`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002439f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002467b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800247cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180024899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800242f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800245de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002469c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024735`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800247ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800248ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800242f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800245de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002469c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024735`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800247ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800248ba`

## string_xrefs

- `0x180024296`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x1800243cb`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x180024485`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x18002494f`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x1800249b6`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x180024a7f`: `CMFSourceReaderStream::OnSourceSampleAvailable`
- `0x180024596`: `CMFSourceReaderStream::TraceSample`

## pseudocode

```c
__int64 __fastcall CMFSourceReaderStream::OnSourceSampleAvailable(
        CMFSourceReaderStream *this,
        struct IMFSample *a2,
        __int64 a3,
        unsigned int *a4)
{
  __int64 result; // rax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  CallStackTracing *v12; // rsi
  CallStackTracing *v13; // rax
  CallStackTracing *v14; // rbx
  char *v15; // rsi
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  CallStackTracing *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  int *v23; // rax
  int v24; // ebx
  struct IMFSampleVtbl *lpVtbl; // rax
  CallStackTracing *v26; // rbx
  CallStackTracing *v27; // rax
  CallStackContext *v28; // rsi
  DWORD v29; // r14d
  CallStackContext *v30; // rax
  __int64 v31; // rdx
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  __int64 v34; // rax
  CallStackTracing *v35; // rbx
  CallStackTracing *v36; // rax
  CallStackContext *v37; // r14
  DWORD v38; // r15d
  CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 v43; // rax
  CallStackContext *v44; // r14
  DWORD v45; // r15d
  CallStackContext *v46; // rax
  __int64 v47; // rdx
  CallStackTracing *v48; // rcx
  CallStackTracing *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  int v55; // edx
  char v56; // cl
  char v57; // al
  __int64 v58; // rdx
  __int64 v59; // rcx
  int v60; // esi
  int v61; // [rsp+60h] [rbp-20h] BYREF
  int v62; // [rsp+64h] [rbp-1Ch] BYREF
  int v63; // [rsp+68h] [rbp-18h] BYREF
  __int64 v64; // [rsp+70h] [rbp-10h] BYREF
  __int64 v65; // [rsp+78h] [rbp-8h] BYREF
  char v66; // [rsp+B0h] [rbp+30h] BYREF

  if ( *((_DWORD *)this + 32) )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v14 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = (char *)v14 + 208;
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v14 + 3));
      if ( Value )
      {
        v15 = Value;
      }
      else if ( !GetLastError() )
      {
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v20 = CallStackTracing::s_wpInstance;
        }
        v21 = (**(__int64 (__fastcall ***)(CallStackTracing *))v20)(v20);
        if ( v21 )
          v15 = (char *)v21;
      }
      SetLastError(LastError);
      v18 = *((unsigned int *)v15 + 497);
      if ( (unsigned int)v18 < *((_DWORD *)v15 + 498) )
      {
        v19 = 2 * v18;
        *(_QWORD *)&v15[8 * v19] = "CMFSourceReaderStream::OnSourceSampleAvailable";
        *(_DWORD *)&v15[8 * v19 + 8] = 4270;
      }
      ++*((_DWORD *)v15 + 497);
    }
    if ( (unsigned __int8)byte_18010CAF1 < 0x10u )
      goto LABEL_26;
    v22 = 395;
    goto LABEL_38;
  }
  if ( a2 )
  {
    if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
    {
      v23 = (int *)*((_QWORD *)this + 202);
      v65 = 0;
      v64 = 0;
      v63 = 0;
      v24 = *v23;
      lpVtbl = a2->lpVtbl;
      v62 = 0;
      v61 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->GetSampleTime)(a2, &v65) < 0 )
        v65 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleDuration)(a2, &v64) < 0 )
        v64 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, int *))a2->lpVtbl->GetUINT32)(
             a2,
             &MFSampleExtension_Discontinuity,
             &v63) < 0 )
        v63 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, const GUID *, int *))a2->lpVtbl->GetUINT32)(
             a2,
             &MFSampleExtension_CleanPoint,
             &v62) < 0 )
        v62 = 0;
      if ( ((int (__fastcall *)(struct IMFSample *, void *, int *))a2->lpVtbl->GetUINT32)(
             a2,
             &MFSampleExtension_EOS,
             &v61) < 0 )
        v61 = 0;
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v66, "CMFSourceReaderStream::TraceSample", 7921);
      if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
      {
        v55 = 95;
        v56 = 95;
        if ( v61 )
          v56 = 69;
        v57 = 95;
        if ( v62 )
          v57 = 67;
        if ( v63 )
          v55 = 68;
        WPP_SF_qsqDIIccc(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          v55,
          68,
          (_DWORD)this,
          (__int64)"MFTChain->ProcessInput",
          *((_QWORD *)this + 204),
          v24,
          v65,
          v64,
          v55,
          v57,
          v56);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
    }
    result = (*(__int64 (__fastcall **)(_QWORD, struct IMFSample *))(**((_QWORD **)this + 204) + 96LL))(
               *((_QWORD *)this + 204),
               a2);
    v9 = result;
    if ( (_DWORD)result == -1072875851 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v66,
        "CMFSourceReaderStream::OnSourceSampleAvailable",
        4328);
      if ( (unsigned __int8)byte_18010CAF1 >= 4u )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          400,
          &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
          this,
          *((_QWORD *)this + 204));
      v60 = CInputSampleData::QueueSampleInfo((CMFSourceReaderStream *)((char *)this + 1328), a2, *a4, a3);
      if ( v60 < 0 )
      {
        v35 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v59, v58);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = (CallStackTracing *)((char *)v35 + 208);
          v38 = GetLastError();
          v39 = (CallStackContext *)TlsGetValue(*((_DWORD *)v35 + 3));
          if ( v39 )
          {
            v37 = v39;
          }
          else if ( !GetLastError() )
          {
            v41 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
              CallStackTracing::s_wpInstance = v42;
              if ( v42
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
              {
                v41 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v41 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
            if ( v43 )
              v37 = (CallStackContext *)v43;
          }
          SetLastError(v38);
          if ( *((_DWORD *)v37 + 499) != v60 )
            CallStackContext::TraceFailure(v37, "CMFSourceReaderStream::OnSourceSampleAvailable", 4330, v60);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            401,
            &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
            this,
            v60);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
      return (unsigned int)v60;
    }
    else if ( (_DWORD)result )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v66,
        "CMFSourceReaderStream::OnSourceSampleAvailable",
        4334);
      if ( byte_18010CAF1 )
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          402,
          &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
          this,
          *((_QWORD *)this + 204),
          v9);
      if ( v9 < 0 )
      {
        v12 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v44 = (CallStackTracing *)((char *)v12 + 208);
          v45 = GetLastError();
          v46 = (CallStackContext *)TlsGetValue(*((_DWORD *)v12 + 3));
          if ( v46 )
          {
            v44 = v46;
          }
          else if ( !GetLastError() )
          {
            v48 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
              CallStackTracing::s_wpInstance = v49;
              if ( v49
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
              {
                v48 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v48 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v50 = (**(__int64 (__fastcall ***)(CallStackTracing *))v48)(v48);
            if ( v50 )
              v44 = (CallStackContext *)v50;
          }
          SetLastError(v45);
          if ( *((_DWORD *)v44 + 499) != v9 )
            CallStackContext::TraceFailure(v44, "CMFSourceReaderStream::OnSourceSampleAvailable", 4335, v9);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            403,
            &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
            this,
            v9);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
      return (unsigned int)v9;
    }
    return result;
  }
  if ( (*a4 & 0x100) != 0 )
  {
    *a4 &= ~0x100u;
    *((_DWORD *)this + 33) = 1;
    *((_QWORD *)this + 17) = a3;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v66,
      "CMFSourceReaderStream::OnSourceSampleAvailable",
      4293);
    if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
      WPP_SF_qqi(*((_QWORD *)WPP_GLOBAL_Control + 7), v51, v52, this, *((_QWORD *)this + 204), *((_QWORD *)this + 17));
    goto LABEL_26;
  }
  if ( *((_DWORD *)this + 30) )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v66,
      "CMFSourceReaderStream::OnSourceSampleAvailable",
      4307);
    if ( (unsigned __int8)byte_18010CAF1 < 0x10u )
    {
LABEL_26:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
      return CMFSourceReaderStream::DrainTransformChain(this);
    }
    v22 = 397;
LABEL_38:
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      v22,
      &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
      this,
      *((_QWORD *)this + 204));
    goto LABEL_26;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v66,
    "CMFSourceReaderStream::OnSourceSampleAvailable",
    4316);
  if ( byte_18010CAF1 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 398, &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids, this);
  v26 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v54, v53);
    CallStackTracing::s_wpInstance = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v26 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v26 = (CallStackTracing *)&qword_18010C230;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
    }
  }
  if ( *((_BYTE *)v26 + 8) )
  {
    v28 = (CallStackTracing *)((char *)v26 + 208);
    v29 = GetLastError();
    v30 = (CallStackContext *)TlsGetValue(*((_DWORD *)v26 + 3));
    if ( v30 )
    {
      v28 = v30;
    }
    else if ( !GetLastError() )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
      if ( v34 )
        v28 = (CallStackContext *)v34;
    }
    SetLastError(v29);
    if ( *((_DWORD *)v28 + 499) != -2147467259 )
      CallStackContext::TraceFailure(v28, "CMFSourceReaderStream::OnSourceSampleAvailable", 4317, -2147467259);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      399,
      &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids,
      this,
      -2147467259);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180024220  mov     [rsp-28h+arg_8], rbx
0x180024225  mov     [rsp-28h+arg_10], rsi
0x18002422a  push    rbp
0x18002422b  push    rdi
0x18002422c  push    r12
0x18002422e  push    r14
0x180024230  push    r15
0x180024232  mov     rbp, rsp
0x180024235  sub     rsp, 80h
0x18002423c  cmp     dword ptr [rcx+80h], 0
0x180024243  mov     r14, r9
0x180024246  mov     r15, r8
0x180024249  mov     rsi, rdx
0x18002424c  mov     rdi, rcx
0x18002424f  jnz     loc_180024376
0x180024255  test    rdx, rdx
0x180024258  jz      loc_180024464
0x18002425e  cmp     cs:byte_18010CAF1, 10h
0x180024265  jnb     loc_1800244CE
0x18002426b  mov     rcx, [rdi+660h]
0x180024272  mov     rdx, rsi
0x180024275  mov     rax, [rcx]
0x180024278  mov     rax, [rax+60h]
0x18002427c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024281  mov     ebx, eax
0x180024283  cmp     eax, 0C00D36B5h
0x180024288  jz      loc_180024A7F
0x18002428e  test    eax, eax
0x180024290  jz      loc_180024402
0x180024296  lea     r12, aCmfsourcereade_90; "CMFSourceReaderStream::OnSourceSampleAv"...
0x18002429d  mov     r8d, 10EEh; int
0x1800242a3  mov     rdx, r12; char *
0x1800242a6  lea     rcx, [rbp+arg_0]; this
0x1800242aa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800242af  cmp     cs:byte_18010CAF1, 1
0x1800242b6  jb      short loc_1800242E7
0x1800242b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242bf  lea     r8, WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids
0x1800242c6  mov     rax, [rdi+660h]
0x1800242cd  mov     edx, 192h
0x1800242d2  mov     dword ptr [rsp+80h+var_58], ebx
0x1800242d6  mov     r9, rdi
0x1800242d9  mov     [rsp+80h+var_60], rax
0x1800242de  mov     rcx, [rcx+38h]
0x1800242e2  call    WPP_SF_qqD
0x1800242e7  test    ebx, ebx
0x1800242e9  jns     short loc_180024366
0x1800242eb  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800242f2  test    rsi, rsi
0x1800242f5  jnz     short loc_180024330
0x1800242f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800242fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024304  mov     rcx, rax
0x180024307  test    rax, rax
0x18002430a  jz      loc_180024873
0x180024310  mov     rax, [rax]
0x180024313  mov     edx, 7F0h
0x180024318  mov     rax, [rax+8]
0x18002431c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024321  test    eax, eax
0x180024323  jz      loc_180024873
0x180024329  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024330  cmp     byte ptr [rsi+8], 0
0x180024334  jnz     loc_180024886
0x18002433a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024341  jb      short loc_180024366
0x180024343  mov     rcx, cs:WPP_GLOBAL_Control
0x18002434a  lea     r8, WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids
0x180024351  mov     edx, 193h
0x180024356  mov     dword ptr [rsp+80h+var_60], ebx
0x18002435a  mov     r9, rdi
0x18002435d  mov     rcx, [rcx+10h]
0x180024361  call    WPP_SF_qD
0x180024366  lea     rcx, [rbp+arg_0]; this
0x18002436a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002436f  mov     eax, ebx
0x180024371  jmp     loc_180024402
0x180024376  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002437d  test    rbx, rbx
0x180024380  jz      loc_18002441E
0x180024386  cmp     byte ptr [rbx+8], 0
0x18002438a  jz      short loc_1800243E4
0x18002438c  lea     rsi, [rbx+0D0h]
0x180024393  call    cs:__imp_GetLastError
0x180024399  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002439c  mov     r14d, eax
0x18002439f  call    cs:__imp_TlsGetValue
0x1800243a5  test    rax, rax
0x1800243a8  jz      loc_18002442F
0x1800243ae  mov     rsi, rax
0x1800243b1  mov     ecx, r14d; dwErrCode
0x1800243b4  call    cs:__imp_SetLastError
0x1800243ba  mov     eax, [rsi+7C4h]
0x1800243c0  cmp     eax, [rsi+7C8h]
0x1800243c6  jnb     short loc_1800243DE
0x1800243c8  add     rax, rax
0x1800243cb  lea     r12, aCmfsourcereade_90; "CMFSourceReaderStream::OnSourceSampleAv"...
0x1800243d2  mov     [rsi+rax*8], r12
0x1800243d6  mov     dword ptr [rsi+rax*8+8], 10AEh
0x1800243de  inc     dword ptr [rsi+7C4h]
0x1800243e4  cmp     cs:byte_18010CAF1, 10h
0x1800243eb  jnb     loc_180024941
0x1800243f1  lea     rcx, [rbp+arg_0]; this
0x1800243f5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800243fa  mov     rcx, rdi; this
0x1800243fd  call    ?DrainTransformChain@CMFSourceReaderStream@@AEAAJXZ; CMFSourceReaderStream::DrainTransformChain(void)
0x180024402  lea     r11, [rsp+80h+var_s0]
0x18002440a  mov     rbx, [r11+38h]
0x18002440e  mov     rsi, [r11+40h]
0x180024412  mov     rsp, r11
0x180024415  pop     r15
0x180024417  pop     r14
0x180024419  pop     r12
0x18002441b  pop     rdi
0x18002441c  pop     rbp
0x18002441d  retn
0x18002441e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180024423  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002442a  jmp     loc_180024386
0x18002442f  call    cs:__imp_GetLastError
0x180024435  test    eax, eax
0x180024437  jnz     loc_1800243B1
0x18002443d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024444  test    rcx, rcx
0x180024447  jz      loc_1800245C1
0x18002444d  mov     rax, [rcx]
0x180024450  mov     rax, [rax]
0x180024453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024458  test    rax, rax
0x18002445b  cmovnz  rsi, rax
0x18002445f  jmp     loc_1800243B1
0x180024464  mov     eax, [r9]
0x180024467  bt      eax, 8
0x18002446b  jb      loc_18002494B
0x180024471  cmp     dword ptr [rcx+78h], 0
0x180024475  lea     rcx, [rbp+arg_0]; this
0x180024479  jz      loc_1800249B6
0x18002447f  mov     r8d, 10D3h; int
0x180024485  lea     rdx, aCmfsourcereade_90; "CMFSourceReaderStream::OnSourceSampleAv"...
0x18002448c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024491  cmp     cs:byte_18010CAF1, 10h
0x180024498  jb      loc_1800243F1
0x18002449e  mov     edx, 18Dh
0x1800244a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244aa  lea     r8, WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids
0x1800244b1  mov     rax, [rdi+660h]
0x1800244b8  mov     r9, rdi
0x1800244bb  mov     [rsp+80h+var_60], rax
0x1800244c0  mov     rcx, [rcx+38h]
0x1800244c4  call    WPP_SF_qq
0x1800244c9  jmp     loc_1800243F1
0x1800244ce  mov     rax, [rcx+650h]
0x1800244d5  xor     r12d, r12d
0x1800244d8  mov     rcx, rsi
0x1800244db  mov     [rbp+var_8], r12
0x1800244df  mov     [rbp+var_10], r12
0x1800244e3  mov     [rbp+var_18], r12d
0x1800244e7  mov     ebx, [rax]
0x1800244e9  mov     rax, [rdx]
0x1800244ec  lea     rdx, [rbp+var_8]
0x1800244f0  mov     [rbp+var_1C], r12d
0x1800244f4  mov     [rbp+var_20], r12d
0x1800244f8  mov     rax, [rax+118h]
0x1800244ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024504  test    eax, eax
0x180024506  jns     short loc_18002450C
0x180024508  mov     [rbp+var_8], r12
0x18002450c  mov     rax, [rsi]
0x18002450f  lea     rdx, [rbp+var_10]
0x180024513  mov     rcx, rsi
0x180024516  mov     rax, [rax+128h]
0x18002451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024522  test    eax, eax
0x180024524  jns     short loc_18002452A
0x180024526  mov     [rbp+var_10], r12
0x18002452a  mov     rax, [rsi]
0x18002452d  lea     r8, [rbp+var_18]
0x180024531  lea     rdx, MFSampleExtension_Discontinuity
0x180024538  mov     rcx, rsi
0x18002453b  mov     rax, [rax+38h]
0x18002453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024544  test    eax, eax
0x180024546  jns     short loc_18002454C
0x180024548  mov     [rbp+var_18], r12d
0x18002454c  mov     rax, [rsi]
0x18002454f  lea     r8, [rbp+var_1C]
0x180024553  lea     rdx, MFSampleExtension_CleanPoint
0x18002455a  mov     rcx, rsi
0x18002455d  mov     rax, [rax+38h]
0x180024561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024566  test    eax, eax
0x180024568  jns     short loc_18002456E
0x18002456a  mov     [rbp+var_1C], r12d
0x18002456e  mov     rax, [rsi]
0x180024571  lea     r8, [rbp+var_20]
0x180024575  lea     rdx, MFSampleExtension_EOS
0x18002457c  mov     rcx, rsi
0x18002457f  mov     rax, [rax+38h]
0x180024583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024588  test    eax, eax
0x18002458a  jns     short loc_180024590
0x18002458c  mov     [rbp+var_20], r12d
0x180024590  mov     r8d, 1EF1h; int
0x180024596  lea     rdx, aCmfsourcereade_31; "CMFSourceReaderStream::TraceSample"
0x18002459d  lea     rcx, [rbp+arg_0]; this
0x1800245a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800245a6  cmp     cs:byte_18010CAF1, 10h
0x1800245ad  jnb     loc_1800249FC
0x1800245b3  lea     rcx, [rbp+arg_0]; this
0x1800245b7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800245bc  jmp     loc_18002426B
0x1800245c1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800245c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245cd  jmp     loc_18002444D
0x1800245d2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245d9  test    rbx, rbx
0x1800245dc  jnz     short loc_18002460F
0x1800245de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800245e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800245eb  mov     rcx, rax
0x1800245ee  test    rax, rax
0x1800245f1  jz      short loc_180024658
0x1800245f3  mov     rax, [rax]
0x1800245f6  mov     edx, 7F0h
0x1800245fb  mov     rax, [rax+8]
0x1800245ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024604  test    eax, eax
0x180024606  jz      short loc_180024658
0x180024608  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002460f  cmp     byte ptr [rbx+8], 0
0x180024613  jnz     short loc_180024668
0x180024615  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002461c  jb      short loc_180024645
0x18002461e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024625  lea     r8, WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids
0x18002462c  mov     edx, 18Fh
0x180024631  mov     dword ptr [rsp+80h+var_60], 80004005h
0x180024639  mov     r9, rdi
0x18002463c  mov     rcx, [rcx+10h]
0x180024640  call    WPP_SF_qD
0x180024645  lea     rcx, [rbp+arg_0]; this
0x180024649  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002464e  mov     eax, 80004005h
0x180024653  jmp     loc_180024402
0x180024658  lea     rbx, qword_18010C230
0x18002465f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024666  jmp     short loc_18002460F
0x180024668  lea     rsi, [rbx+0D0h]
0x18002466f  call    cs:__imp_GetLastError
0x180024675  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180024678  mov     r14d, eax
0x18002467b  call    cs:__imp_TlsGetValue
0x180024681  test    rax, rax
0x180024684  jnz     short loc_1800246D3
0x180024686  call    cs:__imp_GetLastError
0x18002468c  test    eax, eax
0x18002468e  jnz     short loc_1800246D6
0x180024690  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024697  test    rcx, rcx
0x18002469a  jnz     short loc_1800246BF
0x18002469c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800246a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800246a9  mov     rcx, rax
0x1800246ac  test    rax, rax
0x1800246af  jnz     short loc_18002470B
0x1800246b1  lea     rcx, qword_18010C230
0x1800246b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800246bf  mov     rax, [rcx]
0x1800246c2  mov     rax, [rax]
0x1800246c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246ca  test    rax, rax
0x1800246cd  cmovnz  rsi, rax
0x1800246d1  jmp     short loc_1800246D6
0x1800246d3  mov     rsi, rax
0x1800246d6  mov     ecx, r14d; dwErrCode
0x1800246d9  call    cs:__imp_SetLastError
0x1800246df  cmp     dword ptr [rsi+7CCh], 80004005h
0x1800246e9  jz      loc_180024615
0x1800246ef  mov     r9d, 80004005h; int
0x1800246f5  mov     r8d, 10DDh; int
0x1800246fb  mov     rdx, r12; char *
0x1800246fe  mov     rcx, rsi; this
0x180024701  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180024706  jmp     loc_180024615
0x18002470b  mov     rax, [rax]
0x18002470e  mov     edx, 7F0h
0x180024713  mov     rax, [rax+8]
0x180024717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002471c  test    eax, eax
0x18002471e  jz      short loc_1800246B1
0x180024720  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024727  jmp     short loc_1800246BF
0x180024729  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024730  test    rbx, rbx
0x180024733  jnz     short loc_180024766
0x180024735  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002473b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024742  mov     rcx, rax
0x180024745  test    rax, rax
0x180024748  jz      short loc_1800247A8
  ... truncated ...
```
