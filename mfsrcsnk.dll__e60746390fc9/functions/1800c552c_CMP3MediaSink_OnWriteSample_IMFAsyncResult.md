# CMP3MediaSink::OnWriteSample(IMFAsyncResult *)

- ea: `0x1800c552c`
- end: `0x1800c5c0f`
- name: `?OnWriteSample@CMP3MediaSink@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `1763`
- prototype: `void __fastcall(CMP3MediaSink *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1801212e0`

## callees

- `0x18000b680`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800c552c`
- `0x1801099f0`
- `0x18011b1e4`
- `0x1801208c0`
- `0x180121644`
- `0x180121710`
- `0x18012181c`
- `0x180121c30`
- `0x180121ed0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5be2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5be2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5a83`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5a83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c556b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5623`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c556b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5623`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c5653`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c57bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c5931`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c59fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c5653`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c57bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c5931`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c59fd`
- `MFPlat!MFPutWorkItemEx` at `0x1800c5b60`
- `MFPlat!MFPutWorkItemEx` at `0x1800c5b60`

## string_xrefs

- `0x1800c5577`: `CMP3MediaSink::OnWriteSample`
- `0x1800c562f`: `CMP3MediaSink::OnWriteSample`
- `0x1800c56aa`: `CMP3MediaSink::OnWriteSample`
- `0x1800c5816`: `CMP3MediaSink::OnWriteSample`
- `0x1800c5988`: `CMP3MediaSink::OnWriteSample`
- `0x1800c5a54`: `CMP3MediaSink::OnWriteSample`

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
  if ( (unsigned __int8)byte_1801B110A >= 8u )
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
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v17 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v26 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  if ( (unsigned __int8)byte_1801B110A >= 8u )
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
0x1800c552c  mov     [rsp-8+arg_10], rbx
0x1800c5531  push    rbp
0x1800c5532  push    rsi
0x1800c5533  push    rdi
0x1800c5534  push    r12
0x1800c5536  push    r13
0x1800c5538  push    r14
0x1800c553a  push    r15
0x1800c553c  lea     rbp, [rsp-27h]
0x1800c5541  sub     rsp, 0A0h
0x1800c5548  mov     rax, cs:__security_cookie
0x1800c554f  xor     rax, rsp
0x1800c5552  mov     [rbp+57h+var_38], rax
0x1800c5556  mov     rsi, rcx
0x1800c5559  xor     r14d, r14d
0x1800c555c  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800c5560  mov     [rbp+57h+var_68], r14
0x1800c5564  mov     [rbp+57h+var_50], r14d
0x1800c5568  mov     r12, rdx
0x1800c556b  call    cs:__imp_EnterCriticalSection
0x1800c5571  mov     r8d, 28Eh; int
0x1800c5577  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800c557e  lea     rcx, [rbp+57h+var_70]; this
0x1800c5582  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c5587  cmp     cs:byte_1801B110A, 8
0x1800c558e  jb      short loc_1800C55AE
0x1800c5590  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5597  lea     edx, [r14+42h]
0x1800c559b  mov     r9, rsi
0x1800c559e  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800c55a5  mov     rcx, [rcx+60h]
0x1800c55a9  call    WPP_SF_q
0x1800c55ae  cmp     dword ptr [rsi+70h], 4
0x1800c55b2  jnz     short loc_1800C55C5
0x1800c55b4  xor     r13d, r13d
0x1800c55b7  mov     [rbp+57h+var_58], r14
0x1800c55bb  xor     r15d, r15d
0x1800c55be  mov     edi, 0C00D3E85h
0x1800c55c3  jmp     short loc_1800C5606
0x1800c55c5  mov     rcx, [rsi+80h]
0x1800c55cc  xor     edi, edi
0x1800c55ce  mov     [rbp+57h+var_58], rcx
0x1800c55d2  mov     rax, [rcx]
0x1800c55d5  mov     rax, [rax+8]
0x1800c55d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c55de  mov     r13, [rsi+88h]
0x1800c55e5  test    r13, r13
0x1800c55e8  jz      short loc_1800C55FA
0x1800c55ea  mov     rax, [r13+0]
0x1800c55ee  mov     rcx, r13
0x1800c55f1  mov     rax, [rax+8]
0x1800c55f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c55fa  mov     r15, [rsi+188h]
0x1800c5601  lock inc dword ptr [r15+8]
0x1800c5606  lea     rcx, [rbp+57h+var_70]; this
0x1800c560a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800c560f  lea     rcx, [rsi+48h]; lpCriticalSection
0x1800c5613  call    cs:__imp_LeaveCriticalSection
0x1800c5619  lea     rbx, [rsi+90h]
0x1800c5620  mov     rcx, rbx; lpCriticalSection
0x1800c5623  call    cs:__imp_EnterCriticalSection
0x1800c5629  mov     r8d, 2A2h; int
0x1800c562f  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800c5636  lea     rcx, [rbp+57h+var_70]; this
0x1800c563a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c563f  test    edi, edi
0x1800c5641  jns     loc_1800C56F7
0x1800c5647  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c564e  test    rcx, rcx
0x1800c5651  jnz     short loc_1800C5694
0x1800c5653  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c5659  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5660  mov     rcx, rax
0x1800c5663  test    rax, rax
0x1800c5666  jz      short loc_1800C5686
0x1800c5668  mov     rax, [rax]
0x1800c566b  mov     edx, 7F0h
0x1800c5670  mov     rax, [rax+8]
0x1800c5674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5679  test    eax, eax
0x1800c567b  jz      short loc_1800C5686
0x1800c567d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5684  jmp     short loc_1800C5694
0x1800c5686  lea     rcx, qword_1801B07E0; this
0x1800c568d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5694  cmp     [rcx+8], r14b
0x1800c5698  jz      short loc_1800C56BF
0x1800c569a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c569f  cmp     [rax+7CCh], edi
0x1800c56a5  jz      short loc_1800C56BF
0x1800c56a7  mov     r9d, edi; int
0x1800c56aa  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800c56b1  mov     r8d, 2A2h; int
0x1800c56b7  mov     rcx, rax; this
0x1800c56ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c56bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c56c6  jb      short loc_1800C56EB
0x1800c56c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c56cf  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800c56d6  mov     edx, 43h ; 'C'
0x1800c56db  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800c56df  mov     r9, rsi
0x1800c56e2  mov     rcx, [rcx+10h]
0x1800c56e6  call    WPP_SF_qD
0x1800c56eb  lea     r12, [rsi+0B8h]
0x1800c56f2  jmp     loc_1800C5AA3
0x1800c56f7  mov     rdx, r12
0x1800c56fa  test    r13, r13
0x1800c56fd  jnz     short loc_1800C5715
0x1800c56ff  mov     rcx, [rbp+57h+var_58]
0x1800c5703  lea     r8, [rbp+57h+var_50]
0x1800c5707  mov     rax, [rcx]
0x1800c570a  mov     rax, [rax+70h]
0x1800c570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5713  jmp     short loc_1800C5725
0x1800c5715  mov     rax, [r13+0]
0x1800c5719  mov     rcx, r13
0x1800c571c  mov     rax, [rax+20h]
0x1800c5720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5725  mov     edi, eax
0x1800c5727  test    eax, eax
0x1800c5729  jns     short loc_1800C573F
0x1800c572b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5732  jb      short loc_1800C5781
0x1800c5734  mov     edx, 44h ; 'D'
0x1800c5739  mov     dword ptr [rsp+0D0h+pvValue], eax
0x1800c573d  jmp     short loc_1800C5767
0x1800c573f  mov     rax, [r12]
0x1800c5743  mov     rcx, r12
0x1800c5746  mov     rax, [rax+20h]
0x1800c574a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c574f  mov     edi, eax
0x1800c5751  test    eax, eax
0x1800c5753  jns     short loc_1800C5781
0x1800c5755  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c575c  jb      short loc_1800C5781
0x1800c575e  mov     edx, 45h ; 'E'
0x1800c5763  mov     dword ptr [rsp+0D0h+pvValue], eax
0x1800c5767  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c576e  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800c5775  mov     r9, rsi
0x1800c5778  mov     rcx, [rcx+10h]
0x1800c577c  call    WPP_SF_qD
0x1800c5781  lea     r12, [rsi+0B8h]
0x1800c5788  mov     rcx, r12
0x1800c578b  lea     rdx, [rbp+57h+var_68]
0x1800c578f  call    ?Pop@?$CTFifo@PEAUIMFSample@@@@QEAAHAEAPEAUIMFSample@@@Z; CTFifo<IMFSample *>::Pop(IMFSample * &)
0x1800c5794  test    edi, edi
0x1800c5796  js      loc_1800C5A95
0x1800c579c  test    eax, eax
0x1800c579e  jnz     loc_1800C5860
0x1800c57a4  cmp     dword ptr [rsi+70h], 3
0x1800c57a8  jz      loc_1800C5A9F
0x1800c57ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c57b5  mov     edi, 0C00D36BBh
0x1800c57ba  test    rcx, rcx
0x1800c57bd  jnz     short loc_1800C5800
0x1800c57bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c57c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c57cc  mov     rcx, rax
0x1800c57cf  test    rax, rax
0x1800c57d2  jz      short loc_1800C57F2
0x1800c57d4  mov     rax, [rax]
0x1800c57d7  mov     edx, 7F0h
0x1800c57dc  mov     rax, [rax+8]
0x1800c57e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c57e5  test    eax, eax
0x1800c57e7  jz      short loc_1800C57F2
0x1800c57e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c57f0  jmp     short loc_1800C5800
0x1800c57f2  lea     rcx, qword_1801B07E0; this
0x1800c57f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5800  cmp     [rcx+8], r14b
0x1800c5804  jz      short loc_1800C582B
0x1800c5806  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c580b  cmp     [rax+7CCh], edi
0x1800c5811  jz      short loc_1800C582B
0x1800c5813  mov     r9d, edi; int
0x1800c5816  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800c581d  mov     r8d, 2C4h; int
0x1800c5823  mov     rcx, rax; this
0x1800c5826  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c582b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5832  jb      loc_1800C5A9F
0x1800c5838  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c583f  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800c5846  mov     edx, 46h ; 'F'
0x1800c584b  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800c584f  mov     r9, rsi
0x1800c5852  mov     rcx, [rcx+10h]
0x1800c5856  call    WPP_SF_qD
0x1800c585b  jmp     loc_1800C5A9F
0x1800c5860  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x1800c5867  mov     r14, [rbp+57h+var_68]
0x1800c586b  jz      loc_1800C5911
0x1800c5871  mov     rcx, r14; struct IMFSample *
0x1800c5874  call    ?MFWMI_GetMFSampleTotalSpace@@YAKPEAUIMFSample@@@Z; MFWMI_GetMFSampleTotalSpace(IMFSample *)
0x1800c5879  mov     [rbp+57h+var_40], 0
0x1800c5881  lea     rdx, [rbp+57h+var_40]
0x1800c5885  mov     rcx, [r14]
0x1800c5888  mov     r12d, eax
0x1800c588b  mov     rax, [rcx+118h]
0x1800c5892  mov     rcx, r14
0x1800c5895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c589a  mov     [rbp+57h+var_48], 0
0x1800c58a2  lea     rdx, [rbp+57h+var_48]
0x1800c58a6  mov     rcx, [r14]
0x1800c58a9  mov     rax, [rcx+128h]
0x1800c58b0  mov     rcx, r14
0x1800c58b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c58b8  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 8
0x1800c58bf  jz      short loc_1800C590A
0x1800c58c1  mov     rax, [rbp+57h+var_48]
0x1800c58c5  lea     r8, [rbp+57h+var_60]
0x1800c58c9  mov     rcx, [rbp+57h+var_40]
0x1800c58cd  lea     rdx, Buffer_Output
0x1800c58d4  mov     [rsp+0D0h+var_78], rax
0x1800c58d9  mov     r9, rsi
0x1800c58dc  mov     [rsp+0D0h+var_80], r12d
0x1800c58e1  mov     [rsp+0D0h+var_88], r12d
0x1800c58e6  mov     [rsp+0D0h+var_90], r14
0x1800c58eb  mov     [rsp+0D0h+var_A0], rcx
0x1800c58f0  mov     [rsp+0D0h+var_A8], 0
0x1800c58f9  mov     byte ptr [rsp+0D0h+pvValue], 0Bh
0x1800c58fe  mov     [rbp+57h+var_60], 6B33504Dh
0x1800c5905  call    McTemplateU0s4pupippqqi_EventWriteTransfer
0x1800c590a  lea     r12, [rsi+0B8h]
0x1800c5911  mov     edx, edi; int
0x1800c5913  mov     rcx, r15; this
0x1800c5916  call    ?NotifySampleWritten@CMP3MediaStream@@QEAAJJ@Z; CMP3MediaStream::NotifySampleWritten(long)
0x1800c591b  mov     edi, eax
0x1800c591d  test    eax, eax
0x1800c591f  jns     loc_1800C59D2
0x1800c5925  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c592c  test    rcx, rcx
0x1800c592f  jnz     short loc_1800C5972
0x1800c5931  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c5937  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c593e  mov     rcx, rax
0x1800c5941  test    rax, rax
0x1800c5944  jz      short loc_1800C5964
0x1800c5946  mov     rax, [rax]
0x1800c5949  mov     edx, 7F0h
0x1800c594e  mov     rax, [rax+8]
0x1800c5952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5957  test    eax, eax
0x1800c5959  jz      short loc_1800C5964
0x1800c595b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5962  jmp     short loc_1800C5972
0x1800c5964  lea     rcx, qword_1801B07E0; this
0x1800c596b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5972  cmp     byte ptr [rcx+8], 0
0x1800c5976  jz      short loc_1800C599D
0x1800c5978  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c597d  cmp     [rax+7CCh], edi
0x1800c5983  jz      short loc_1800C599D
0x1800c5985  mov     r9d, edi; int
0x1800c5988  lea     rdx, aCmp3mediasinkO_4; "CMP3MediaSink::OnWriteSample"
0x1800c598f  mov     r8d, 2DFh; int
0x1800c5995  mov     rcx, rax; this
0x1800c5998  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c599d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c59a4  jb      loc_1800C5AA3
0x1800c59aa  mov     edx, 47h ; 'G'
0x1800c59af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c59b6  lea     r8, WPP_b2dbc1529fde3b116a04799763f041e4_Traceguids
0x1800c59bd  mov     r9, rsi
0x1800c59c0  mov     dword ptr [rsp+0D0h+pvValue], edi
0x1800c59c4  mov     rcx, [rcx+10h]
0x1800c59c8  call    WPP_SF_qD
0x1800c59cd  jmp     loc_1800C5AA3
0x1800c59d2  cmp     dword ptr [rsi+170h], 1
0x1800c59d9  jb      loc_1800C5A7C
0x1800c59df  mov     rcx, rsi; this
0x1800c59e2  call    ?BeginWriteSample@CMP3MediaSink@@IEAAJXZ; CMP3MediaSink::BeginWriteSample(void)
0x1800c59e7  mov     edi, eax
0x1800c59e9  test    eax, eax
0x1800c59eb  jns     loc_1800C5A89
0x1800c59f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c59f8  test    rcx, rcx
0x1800c59fb  jnz     short loc_1800C5A3E
0x1800c59fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c5a03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5a0a  mov     rcx, rax
0x1800c5a0d  test    rax, rax
0x1800c5a10  jz      short loc_1800C5A30
0x1800c5a12  mov     rax, [rax]
0x1800c5a15  mov     edx, 7F0h
0x1800c5a1a  mov     rax, [rax+8]
0x1800c5a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5a23  test    eax, eax
0x1800c5a25  jz      short loc_1800C5A30
0x1800c5a27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5a2e  jmp     short loc_1800C5A3E
0x1800c5a30  lea     rcx, qword_1801B07E0; this
0x1800c5a37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c5a3e  cmp     byte ptr [rcx+8], 0
0x1800c5a42  jz      short loc_1800C5A69
0x1800c5a44  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c5a49  cmp     [rax+7CCh], edi
  ... truncated ...
```
