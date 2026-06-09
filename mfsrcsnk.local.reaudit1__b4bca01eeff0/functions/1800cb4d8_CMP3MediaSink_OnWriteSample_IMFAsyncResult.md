# CMP3MediaSink::OnWriteSample(IMFAsyncResult *)

- ea: `0x1800cb4d8`
- end: `0x1800cbbf8`
- name: `?OnWriteSample@CMP3MediaSink@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `1824`
- prototype: `void __fastcall(CMP3MediaSink *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180127fe0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18003db64`
- `0x180079680`
- `0x1800cb4d8`
- `0x180110ed0`
- `0x180121750`
- `0x180126fe0`
- `0x180128358`
- `0x180128424`
- `0x180128540`
- `0x180128980`
- `0x180128c34`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbbc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbbc4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cba59`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cba59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb5db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb5db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb783`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb9cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb783`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800cb9cd`
- `MFPlat!MFPutWorkItemEx` at `0x1800cbb3c`
- `MFPlat!MFPutWorkItemEx` at `0x1800cbb3c`

## string_xrefs

- `0x1800cb529`: `CMP3MediaSink::OnWriteSample`
- `0x1800cb5ed`: `CMP3MediaSink::OnWriteSample`
- `0x1800cb66e`: `CMP3MediaSink::OnWriteSample`
- `0x1800cb7e0`: `CMP3MediaSink::OnWriteSample`
- `0x1800cb958`: `CMP3MediaSink::OnWriteSample`
- `0x1800cba2a`: `CMP3MediaSink::OnWriteSample`

## pseudocode

```c
void __fastcall CMP3MediaSink::OnWriteSample(CMP3MediaSink *this, struct IMFAsyncResult *a2)
{
  struct IMFSample *v3; // r14
  __int64 v5; // r13
  volatile signed __int32 *v6; // r15
  int v7; // edi
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char *v12; // r12
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  struct IMFSample *v30; // rcx
  IMFAsyncResult *v31; // rdx
  int v32; // eax
  _BYTE v33[8]; // [rsp+60h] [rbp-19h] BYREF
  struct IMFSample *v34; // [rsp+68h] [rbp-11h] BYREF
  int v35; // [rsp+70h] [rbp-9h] BYREF
  __int64 v36; // [rsp+78h] [rbp-1h]
  int v37; // [rsp+80h] [rbp+7h] BYREF
  __int64 v38; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v39; // [rsp+90h] [rbp+17h] BYREF

  v3 = 0;
  v34 = 0;
  v37 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CMP3MediaSink::OnWriteSample", 654);
  if ( (unsigned __int8)byte_1801BA10A >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 66, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this);
  if ( *((_DWORD *)this + 28) == 4 )
  {
    v5 = 0;
    v36 = 0;
    v6 = 0;
    v7 = -1072873851;
  }
  else
  {
    v7 = 0;
    v36 = *((_QWORD *)this + 16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
    v5 = *((_QWORD *)this + 17);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*((_QWORD *)this + 17));
    v6 = (volatile signed __int32 *)*((_QWORD *)this + 49);
    _InterlockedIncrement(v6 + 2);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CMP3MediaSink::OnWriteSample", 674);
  if ( v7 < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSink::OnWriteSample", 674, v7);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v7);
    v12 = (char *)this + 184;
    goto LABEL_74;
  }
  if ( v5 )
    v13 = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *))(*(_QWORD *)v5 + 32LL))(v5, a2);
  else
    v13 = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, int *))(*(_QWORD *)v36 + 112LL))(v36, a2, &v37);
  v7 = v13;
  if ( v13 >= 0 )
  {
    v14 = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
    v7 = v14;
    if ( v14 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v14);
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v13);
  }
  v12 = (char *)this + 184;
  v15 = CTFifo<IMFSample *>::Pop((char *)this + 184, &v34);
  if ( v7 < 0 )
  {
    CMP3MediaStream::NotifySampleWritten((CMP3MediaStream *)v6, v7);
LABEL_73:
    v3 = v34;
    goto LABEL_74;
  }
  if ( !v15 )
  {
    if ( *((_DWORD *)this + 28) != 3 )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      v7 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v19, "CMP3MediaSink::OnWriteSample", 708, -1072875845);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids,
          this,
          -1072875845);
    }
    goto LABEL_73;
  }
  v3 = v34;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
  {
    MFWMI_GetMFSampleTotalSpace(v34);
    v39 = 0;
    ((void (__fastcall *)(struct IMFSample *, __int64 *))v3->lpVtbl->GetSampleTime)(v3, &v39);
    v38 = 0;
    ((void (__fastcall *)(struct IMFSample *, __int64 *))v3->lpVtbl->GetSampleDuration)(v3, &v38);
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
    {
      v35 = 1798525005;
      McTemplateU0s4pupippqqi_EventWriteTransfer(
        v39,
        (unsigned int)Buffer_Output,
        (unsigned int)&v35,
        (_DWORD)this,
        11,
        0,
        v39);
    }
    v12 = (char *)this + 184;
  }
  v7 = CMP3MediaStream::NotifySampleWritten((CMP3MediaStream *)v6, v7);
  if ( v7 < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != v7 )
        CallStackContext::TraceFailure(v23, "CMP3MediaSink::OnWriteSample", 735, v7);
    }
    if ( g_wppLevels )
    {
      v24 = 71;
LABEL_57:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v7);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  if ( !*((_DWORD *)this + 92) )
  {
    SetEvent(*((HANDLE *)this + 60));
    goto LABEL_71;
  }
  v7 = CMP3MediaSink::BeginWriteSample(this);
  if ( v7 >= 0 )
  {
LABEL_71:
    *((_DWORD *)this + 103) = 1;
    goto LABEL_74;
  }
  v26 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
    CallStackTracing::s_wpInstance = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v26 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v26 + 8) )
  {
    v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
    if ( *((_DWORD *)v28 + 499) != v7 )
      CallStackContext::TraceFailure(v28, "CMP3MediaSink::OnWriteSample", 746, v7);
  }
  if ( g_wppLevels )
  {
    v24 = 72;
    goto LABEL_57;
  }
LABEL_74:
  if ( (unsigned __int8)byte_1801BA10A >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 73, &WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids, this, v7);
  if ( v7 != -1072873851 )
  {
    if ( v7 < 0 )
    {
      if ( !v3 )
        goto LABEL_83;
      lpVtbl = v3->lpVtbl;
      v30 = v3;
LABEL_82:
      ((void (__fastcall *)(struct IMFSample *))lpVtbl->Release)(v30);
      v34 = 0;
LABEL_83:
      while ( (unsigned int)CTFifo<IMFSample *>::Pop(v12, &v34) )
      {
        CMP3MediaStream::NotifySampleWritten((CMP3MediaStream *)v6, v7);
        v30 = v34;
        if ( v34 )
        {
          lpVtbl = v34->lpVtbl;
          goto LABEL_82;
        }
      }
      CMFMediaEventGenerator::QueueEvent(
        (CMFMediaEventGenerator *)(v6 + 18),
        1,
        &GUID_00000000_0000_0000_0000_000000000000,
        v7,
        0);
      v3 = v34;
    }
    if ( !*((_DWORD *)this + 92) )
    {
      v31 = (IMFAsyncResult *)*((_QWORD *)this + 50);
      if ( v31 )
      {
        v32 = MFPutWorkItemEx(1u, v31);
        if ( v32 < 0 )
          CMFMediaEventGenerator::QueueEvent(
            (CMFMediaEventGenerator *)(v6 + 18),
            1,
            &GUID_00000000_0000_0000_0000_000000000000,
            v32,
            0);
      }
    }
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v3 )
    ((void (__fastcall *)(struct IMFSample *))v3->lpVtbl->Release)(v3);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v6 )
    CMP3MediaStream::Release((CMP3MediaStream *)v6);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
}

```

## disassembly

```asm
0x1800cb4d8  mov     [rsp-8+arg_10], rbx
0x1800cb4dd  push    rbp
0x1800cb4de  push    rsi
0x1800cb4df  push    rdi
0x1800cb4e0  push    r12
0x1800cb4e2  push    r13
0x1800cb4e4  push    r14
0x1800cb4e6  push    r15
0x1800cb4e8  lea     rbp, [rsp-27h]
0x1800cb4ed  sub     rsp, 0A0h
0x1800cb4f4  mov     rax, cs:__security_cookie
0x1800cb4fb  xor     rax, rsp
0x1800cb4fe  mov     [rbp+57h+var_38], rax
0x1800cb502  mov     rsi, rcx
0x1800cb505  xor     r14d, r14d
0x1800cb508  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800cb50c  mov     [rbp+57h+var_68], r14
0x1800cb510  mov     [rbp+57h+var_50], r14d
0x1800cb514  mov     r12, rdx
0x1800cb517  call    cs:__imp_EnterCriticalSection
0x1800cb51e  nop     dword ptr [rax+rax+00h]
0x1800cb523  mov     r8d, 28Eh; int
0x1800cb529  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800cb530  lea     rcx, [rbp+57h+var_70]; this
0x1800cb534  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cb539  cmp     cs:byte_1801BA10A, 8
0x1800cb540  jb      short loc_1800CB560
0x1800cb542  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb549  lea     edx, [r14+42h]
0x1800cb54d  mov     r9, rsi
0x1800cb550  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800cb557  mov     rcx, [rcx+60h]
0x1800cb55b  call    WPP_SF_q
0x1800cb560  cmp     dword ptr [rsi+70h], 4
0x1800cb564  jnz     short loc_1800CB577
0x1800cb566  xor     r13d, r13d
0x1800cb569  mov     [rbp+57h+var_58], r14
0x1800cb56d  xor     r15d, r15d
0x1800cb570  mov     edi, 0C00D3E85h
0x1800cb575  jmp     short loc_1800CB5B8
0x1800cb577  mov     rcx, [rsi+80h]
0x1800cb57e  xor     edi, edi
0x1800cb580  mov     [rbp+57h+var_58], rcx
0x1800cb584  mov     rax, [rcx]
0x1800cb587  mov     rax, [rax+8]
0x1800cb58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb590  mov     r13, [rsi+88h]
0x1800cb597  test    r13, r13
0x1800cb59a  jz      short loc_1800CB5AC
0x1800cb59c  mov     rax, [r13+0]
0x1800cb5a0  mov     rcx, r13
0x1800cb5a3  mov     rax, [rax+8]
0x1800cb5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb5ac  mov     r15, [rsi+188h]
0x1800cb5b3  lock inc dword ptr [r15+8]
0x1800cb5b8  lea     rcx, [rbp+57h+var_70]; this
0x1800cb5bc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cb5c1  lea     rcx, [rsi+48h]; lpCriticalSection
0x1800cb5c5  call    cs:__imp_LeaveCriticalSection
0x1800cb5cc  nop     dword ptr [rax+rax+00h]
0x1800cb5d1  lea     rbx, [rsi+90h]
0x1800cb5d8  mov     rcx, rbx; lpCriticalSection
0x1800cb5db  call    cs:__imp_EnterCriticalSection
0x1800cb5e2  nop     dword ptr [rax+rax+00h]
0x1800cb5e7  mov     r8d, 2A2h; int
0x1800cb5ed  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800cb5f4  lea     rcx, [rbp+57h+var_70]; this
0x1800cb5f8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cb5fd  test    edi, edi
0x1800cb5ff  jns     loc_1800CB6BB
0x1800cb605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb60c  test    rcx, rcx
0x1800cb60f  jnz     short loc_1800CB658
0x1800cb611  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cb618  nop     dword ptr [rax+rax+00h]
0x1800cb61d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb624  mov     rcx, rax
0x1800cb627  test    rax, rax
0x1800cb62a  jz      short loc_1800CB64A
0x1800cb62c  mov     rax, [rax]
0x1800cb62f  mov     edx, 7F0h
0x1800cb634  mov     rax, [rax+8]
0x1800cb638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb63d  test    eax, eax
0x1800cb63f  jz      short loc_1800CB64A
0x1800cb641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb648  jmp     short loc_1800CB658
0x1800cb64a  lea     rcx, qword_1801B97E0; this
0x1800cb651  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb658  cmp     [rcx+8], r14b
0x1800cb65c  jz      short loc_1800CB683
0x1800cb65e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb663  cmp     [rax+7CCh], edi
0x1800cb669  jz      short loc_1800CB683
0x1800cb66b  mov     r9d, edi; int
0x1800cb66e  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800cb675  mov     r8d, 2A2h; int
0x1800cb67b  mov     rcx, rax; this
0x1800cb67e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb683  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb68a  jb      short loc_1800CB6AF
0x1800cb68c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb693  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800cb69a  mov     edx, 43h ; 'C'
0x1800cb69f  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800cb6a3  mov     r9, rsi
0x1800cb6a6  mov     rcx, [rcx+10h]
0x1800cb6aa  call    WPP_SF_qD
0x1800cb6af  lea     r12, [rsi+0B8h]
0x1800cb6b6  jmp     loc_1800CBA7F
0x1800cb6bb  mov     rdx, r12
0x1800cb6be  test    r13, r13
0x1800cb6c1  jnz     short loc_1800CB6D9
0x1800cb6c3  mov     rcx, [rbp+57h+var_58]
0x1800cb6c7  lea     r8, [rbp+57h+var_50]
0x1800cb6cb  mov     rax, [rcx]
0x1800cb6ce  mov     rax, [rax+70h]
0x1800cb6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb6d7  jmp     short loc_1800CB6E9
0x1800cb6d9  mov     rax, [r13+0]
0x1800cb6dd  mov     rcx, r13
0x1800cb6e0  mov     rax, [rax+20h]
0x1800cb6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb6e9  mov     edi, eax
0x1800cb6eb  test    eax, eax
0x1800cb6ed  jns     short loc_1800CB703
0x1800cb6ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb6f6  jb      short loc_1800CB745
0x1800cb6f8  mov     edx, 44h ; 'D'
0x1800cb6fd  mov     dword ptr [rsp+0D0h+pvValue], eax
0x1800cb701  jmp     short loc_1800CB72B
0x1800cb703  mov     rax, [r12]
0x1800cb707  mov     rcx, r12
0x1800cb70a  mov     rax, [rax+20h]
0x1800cb70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb713  mov     edi, eax
0x1800cb715  test    eax, eax
0x1800cb717  jns     short loc_1800CB745
0x1800cb719  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb720  jb      short loc_1800CB745
0x1800cb722  mov     edx, 45h ; 'E'
0x1800cb727  mov     dword ptr [rsp+0D0h+pvValue], eax
0x1800cb72b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb732  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800cb739  mov     r9, rsi
0x1800cb73c  mov     rcx, [rcx+10h]
0x1800cb740  call    WPP_SF_qD
0x1800cb745  lea     r12, [rsi+0B8h]
0x1800cb74c  mov     rcx, r12
0x1800cb74f  lea     rdx, [rbp+57h+var_68]
0x1800cb753  call    ?Pop@?$CTFifo@PEAUIMFSample@@@@QEAAHAEAPEAUIMFSample@@@Z; CTFifo<IMFSample *>::Pop(IMFSample * &)
0x1800cb758  test    edi, edi
0x1800cb75a  js      loc_1800CBA71
0x1800cb760  test    eax, eax
0x1800cb762  jnz     loc_1800CB82A
0x1800cb768  cmp     dword ptr [rsi+70h], 3
0x1800cb76c  jz      loc_1800CBA7B
0x1800cb772  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb779  mov     edi, 0C00D36BBh
0x1800cb77e  test    rcx, rcx
0x1800cb781  jnz     short loc_1800CB7CA
0x1800cb783  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cb78a  nop     dword ptr [rax+rax+00h]
0x1800cb78f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb796  mov     rcx, rax
0x1800cb799  test    rax, rax
0x1800cb79c  jz      short loc_1800CB7BC
0x1800cb79e  mov     rax, [rax]
0x1800cb7a1  mov     edx, 7F0h
0x1800cb7a6  mov     rax, [rax+8]
0x1800cb7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb7af  test    eax, eax
0x1800cb7b1  jz      short loc_1800CB7BC
0x1800cb7b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb7ba  jmp     short loc_1800CB7CA
0x1800cb7bc  lea     rcx, qword_1801B97E0; this
0x1800cb7c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb7ca  cmp     [rcx+8], r14b
0x1800cb7ce  jz      short loc_1800CB7F5
0x1800cb7d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb7d5  cmp     [rax+7CCh], edi
0x1800cb7db  jz      short loc_1800CB7F5
0x1800cb7dd  mov     r9d, edi; int
0x1800cb7e0  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800cb7e7  mov     r8d, 2C4h; int
0x1800cb7ed  mov     rcx, rax; this
0x1800cb7f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb7f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb7fc  jb      loc_1800CBA7B
0x1800cb802  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb809  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800cb810  mov     edx, 46h ; 'F'
0x1800cb815  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800cb819  mov     r9, rsi
0x1800cb81c  mov     rcx, [rcx+10h]
0x1800cb820  call    WPP_SF_qD
0x1800cb825  jmp     loc_1800CBA7B
0x1800cb82a  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x1800cb831  mov     r14, [rbp+57h+var_68]
0x1800cb835  jz      loc_1800CB8DB
0x1800cb83b  mov     rcx, r14; struct IMFSample *
0x1800cb83e  call    ?MFWMI_GetMFSampleTotalSpace@@YAKPEAUIMFSample@@@Z; MFWMI_GetMFSampleTotalSpace(IMFSample *)
0x1800cb843  mov     [rbp+57h+var_40], 0
0x1800cb84b  lea     rdx, [rbp+57h+var_40]
0x1800cb84f  mov     rcx, [r14]
0x1800cb852  mov     r12d, eax
0x1800cb855  mov     rax, [rcx+118h]
0x1800cb85c  mov     rcx, r14
0x1800cb85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb864  mov     [rbp+57h+var_48], 0
0x1800cb86c  lea     rdx, [rbp+57h+var_48]
0x1800cb870  mov     rcx, [r14]
0x1800cb873  mov     rax, [rcx+128h]
0x1800cb87a  mov     rcx, r14
0x1800cb87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb882  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x1800cb889  jz      short loc_1800CB8D4
0x1800cb88b  mov     rax, [rbp+57h+var_48]
0x1800cb88f  lea     r8, [rbp+57h+var_60]
0x1800cb893  mov     rcx, [rbp+57h+var_40]
0x1800cb897  lea     rdx, Buffer_Output
0x1800cb89e  mov     [rsp+0D0h+var_78], rax
0x1800cb8a3  mov     r9, rsi
0x1800cb8a6  mov     [rsp+0D0h+var_80], r12d
0x1800cb8ab  mov     [rsp+0D0h+var_88], r12d
0x1800cb8b0  mov     [rsp+0D0h+var_90], r14
0x1800cb8b5  mov     [rsp+0D0h+var_A0], rcx
0x1800cb8ba  mov     [rsp+0D0h+var_A8], 0
0x1800cb8c3  mov     byte ptr [rsp+0D0h+pvValue], 0Bh
0x1800cb8c8  mov     [rbp+57h+var_60], 6B33504Dh
0x1800cb8cf  call    McTemplateU0s4pupippqqi_EventWriteTransfer
0x1800cb8d4  lea     r12, [rsi+0B8h]
0x1800cb8db  mov     edx, edi; int
0x1800cb8dd  mov     rcx, r15; this
0x1800cb8e0  call    ?NotifySampleWritten@CMP3MediaStream@@QEAAJJ@Z; CMP3MediaStream::NotifySampleWritten(long)
0x1800cb8e5  mov     edi, eax
0x1800cb8e7  test    eax, eax
0x1800cb8e9  jns     loc_1800CB9A2
0x1800cb8ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb8f6  test    rcx, rcx
0x1800cb8f9  jnz     short loc_1800CB942
0x1800cb8fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cb902  nop     dword ptr [rax+rax+00h]
0x1800cb907  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb90e  mov     rcx, rax
0x1800cb911  test    rax, rax
0x1800cb914  jz      short loc_1800CB934
0x1800cb916  mov     rax, [rax]
0x1800cb919  mov     edx, 7F0h
0x1800cb91e  mov     rax, [rax+8]
0x1800cb922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb927  test    eax, eax
0x1800cb929  jz      short loc_1800CB934
0x1800cb92b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb932  jmp     short loc_1800CB942
0x1800cb934  lea     rcx, qword_1801B97E0; this
0x1800cb93b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb942  cmp     byte ptr [rcx+8], 0
0x1800cb946  jz      short loc_1800CB96D
0x1800cb948  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb94d  cmp     [rax+7CCh], edi
0x1800cb953  jz      short loc_1800CB96D
0x1800cb955  mov     r9d, edi; int
0x1800cb958  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800cb95f  mov     r8d, 2DFh; int
0x1800cb965  mov     rcx, rax; this
0x1800cb968  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb96d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb974  jb      loc_1800CBA7F
0x1800cb97a  mov     edx, 47h ; 'G'
0x1800cb97f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb986  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800cb98d  mov     r9, rsi
0x1800cb990  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800cb994  mov     rcx, [rcx+10h]
0x1800cb998  call    WPP_SF_qD
0x1800cb99d  jmp     loc_1800CBA7F
0x1800cb9a2  cmp     dword ptr [rsi+170h], 1
0x1800cb9a9  jb      loc_1800CBA52
0x1800cb9af  mov     rcx, rsi; this
0x1800cb9b2  call    ?BeginWriteSample@CMP3MediaSink@@IEAAJXZ; CMP3MediaSink::BeginWriteSample(void)
0x1800cb9b7  mov     edi, eax
0x1800cb9b9  test    eax, eax
0x1800cb9bb  jns     loc_1800CBA65
0x1800cb9c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb9c8  test    rcx, rcx
0x1800cb9cb  jnz     short loc_1800CBA14
0x1800cb9cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800cb9d4  nop     dword ptr [rax+rax+00h]
0x1800cb9d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb9e0  mov     rcx, rax
0x1800cb9e3  test    rax, rax
0x1800cb9e6  jz      short loc_1800CBA06
0x1800cb9e8  mov     rax, [rax]
0x1800cb9eb  mov     edx, 7F0h
0x1800cb9f0  mov     rax, [rax+8]
0x1800cb9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb9f9  test    eax, eax
0x1800cb9fb  jz      short loc_1800CBA06
0x1800cb9fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
