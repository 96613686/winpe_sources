# CAVIStreamSink::GetNextSample(IMFSample * *)

- ea: `0x18012a558`
- end: `0x18012ad1d`
- name: `?GetNextSample@CAVIStreamSink@@AEAAJPEAPEAUIMFSample@@@Z`
- size: `1989`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18012ad24`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180128728`
- `0x18012a558`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ad04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ad04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a57c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012a57c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a5cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a6a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a80e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a8c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a97b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012aa54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ab00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012abac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ac58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a5cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a6a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a80e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a8c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012a97b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012aa54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ab00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012abac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18012ac58`
- `MFPlat!MFCreateMemoryBuffer` at `0x18012a7f2`
- `MFPlat!MFCreateMemoryBuffer` at `0x18012a7f2`
- `MFPlat!MFCreateSample` at `0x18012aa38`
- `MFPlat!MFCreateSample` at `0x18012aa38`

## string_xrefs

- `0x18012a585`: `CAVIStreamSink::GetNextSample`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::GetNextSample(CAVIStreamSink *this, struct IMFSample **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  HRESULT v5; // ebx
  __int64 v6; // rdx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v10; // r14
  _QWORD *v11; // rax
  __int64 v12; // rcx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  char v43; // [rsp+80h] [rbp+48h] BYREF
  IMFSample *ppIMFSample; // [rsp+88h] [rbp+50h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+90h] [rbp+58h] BYREF
  void *v46; // [rsp+98h] [rbp+60h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 536);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  v5 = a2 == 0 ? 0x80004003 : 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CAVIStreamSink::GetNextSample", 1414);
  ppBuffer = 0;
  ppIMFSample = 0;
  v46 = 0;
  if ( !a2 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::GetNextSample", 1421, v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, this, v5);
    goto LABEL_117;
  }
  *a2 = 0;
  v10 = (__int64 *)*((_QWORD *)this + 65);
  --*((_DWORD *)this + 128);
  v11 = (_QWORD *)v10[1];
  v12 = *v10;
  *v11 = *v10;
  *(_QWORD *)(v12 + 8) = v11;
  if ( v10 )
  {
    if ( *((_BYTE *)v10 + 56) )
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
      v5 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v18, "CAVIStreamSink::GetNextSample", 1428, -2147418113);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          228,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          this,
          -2147418113);
      goto LABEL_116;
    }
    _InterlockedDecrement((volatile signed __int32 *)this + 126);
    v5 = MFCreateMemoryBuffer(*((_DWORD *)v10 + 6), &ppBuffer);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
             ppBuffer,
             &v46,
             0,
             0);
      if ( v5 >= 0 )
      {
        memcpy_0(v46, (const void *)v10[2], *((unsigned int *)v10 + 6));
        v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
               ppBuffer,
               *((unsigned int *)v10 + 6));
        if ( v5 < 0 )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != v5 )
              CallStackContext::TraceFailure(v29, "CAVIStreamSink::GetNextSample", 1437, v5);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              231,
              &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
              this,
              v5);
          ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
          goto LABEL_116;
        }
        ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
        v5 = MFCreateSample(&ppIMFSample);
        if ( v5 >= 0 )
        {
          v5 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                 ppIMFSample,
                 ppBuffer);
          if ( v5 >= 0 )
          {
            v5 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
                   ppIMFSample,
                   v10[5]);
            if ( v5 >= 0 )
            {
              v5 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(
                     ppIMFSample,
                     v10[6]);
              if ( v5 >= 0 )
              {
                *a2 = ppIMFSample;
                ppIMFSample = 0;
                goto LABEL_116;
              }
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
                CallStackTracing::s_wpInstance = v40;
                if ( v40
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                {
                  v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v39 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v39 + 8) )
              {
                v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                if ( *((_DWORD *)v41 + 499) != v5 )
                  CallStackContext::TraceFailure(v41, "CAVIStreamSink::GetNextSample", 1444, v5);
              }
              if ( !g_wppLevels )
                goto LABEL_116;
              v22 = 235;
            }
            else
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v36 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                if ( *((_DWORD *)v38 + 499) != v5 )
                  CallStackContext::TraceFailure(v38, "CAVIStreamSink::GetNextSample", 1443, v5);
              }
              if ( !g_wppLevels )
                goto LABEL_116;
              v22 = 234;
            }
          }
          else
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
              {
                v33 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v33 + 8) )
            {
              v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)v35 + 499) != v5 )
                CallStackContext::TraceFailure(v35, "CAVIStreamSink::GetNextSample", 1442, v5);
            }
            if ( !g_wppLevels )
              goto LABEL_116;
            v22 = 233;
          }
        }
        else
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
            if ( *((_DWORD *)v32 + 499) != v5 )
              CallStackContext::TraceFailure(v32, "CAVIStreamSink::GetNextSample", 1441, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_116;
          v22 = 232;
        }
      }
      else
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v5 )
            CallStackContext::TraceFailure(v25, "CAVIStreamSink::GetNextSample", 1434, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_116;
        v22 = 230;
      }
    }
    else
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v5 )
          CallStackContext::TraceFailure(v21, "CAVIStreamSink::GetNextSample", 1433, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v22 = 229;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids, this, v5);
LABEL_116:
    CAVIStreamSink::StreamSampleQueueEntry::`scalar deleting destructor'(
      (CAVIStreamSink::StreamSampleQueueEntry *)v10,
      v6);
    goto LABEL_117;
  }
  v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  v5 = -2147418113;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != -2147418113 )
      CallStackContext::TraceFailure(v15, "CAVIStreamSink::GetNextSample", 1425, -2147418113);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      227,
      &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
      this,
      -2147418113);
LABEL_117:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18012a558  push    rbp
0x18012a55a  push    rbx
0x18012a55b  push    rsi
0x18012a55c  push    rdi
0x18012a55d  push    r12
0x18012a55f  push    r13
0x18012a561  push    r14
0x18012a563  push    r15
0x18012a565  mov     rbp, rsp
0x18012a568  sub     rsp, 38h
0x18012a56c  lea     r15, [rcx+218h]
0x18012a573  mov     rsi, rcx
0x18012a576  mov     rcx, r15; lpCriticalSection
0x18012a579  mov     rdi, rdx
0x18012a57c  call    cs:__imp_EnterCriticalSection
0x18012a582  mov     rax, rdi
0x18012a585  lea     r13, aCavistreamsink_21; "CAVIStreamSink::GetNextSample"
0x18012a58c  neg     rax
0x18012a58f  lea     rcx, [rbp+arg_0]; this
0x18012a593  mov     r8d, 586h; int
0x18012a599  mov     rdx, r13; char *
0x18012a59c  sbb     ebx, ebx
0x18012a59e  not     ebx
0x18012a5a0  and     ebx, 80004003h
0x18012a5a6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18012a5ab  xor     r12d, r12d
0x18012a5ae  mov     [rbp+ppBuffer], r12
0x18012a5b2  mov     [rbp+ppIMFSample], r12
0x18012a5b6  mov     [rbp+arg_18], r12
0x18012a5ba  test    rdi, rdi
0x18012a5bd  jnz     loc_18012A66C
0x18012a5c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a5ca  test    rcx, rcx
0x18012a5cd  jnz     short loc_18012A610
0x18012a5cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a5d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a5dc  mov     rcx, rax
0x18012a5df  test    rax, rax
0x18012a5e2  jz      short loc_18012A602
0x18012a5e4  mov     rax, [rax]
0x18012a5e7  mov     edx, 7F0h
0x18012a5ec  mov     rax, [rax+8]
0x18012a5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a5f5  test    eax, eax
0x18012a5f7  jz      short loc_18012A602
0x18012a5f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a600  jmp     short loc_18012A610
0x18012a602  lea     rcx, qword_1801B07E0; this
0x18012a609  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a610  cmp     [rcx+8], r12b
0x18012a614  jz      short loc_18012A637
0x18012a616  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a61b  cmp     [rax+7CCh], ebx
0x18012a621  jz      short loc_18012A637
0x18012a623  mov     r9d, ebx; int
0x18012a626  mov     r8d, 58Dh; int
0x18012a62c  mov     rdx, r13; char *
0x18012a62f  mov     rcx, rax; this
0x18012a632  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a637  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a63e  jb      loc_18012ACE6
0x18012a644  mov     edx, 0E2h
0x18012a649  mov     [rsp+38h+var_18], ebx
0x18012a64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a654  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x18012a65b  mov     r9, rsi
0x18012a65e  mov     rcx, [rcx+10h]
0x18012a662  call    WPP_SF_qD
0x18012a667  jmp     loc_18012ACE6
0x18012a66c  mov     [rdi], r12
0x18012a66f  mov     r14, [rsi+208h]
0x18012a676  dec     dword ptr [rsi+200h]
0x18012a67c  mov     rax, [r14+8]
0x18012a680  mov     rcx, [r14]
0x18012a683  mov     [rax], rcx
0x18012a686  mov     [rcx+8], rax
0x18012a68a  test    r14, r14
0x18012a68d  jnz     loc_18012A729
0x18012a693  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a69a  mov     edi, 8000FFFFh
0x18012a69f  mov     ebx, edi
0x18012a6a1  test    rcx, rcx
0x18012a6a4  jnz     short loc_18012A6E7
0x18012a6a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a6ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a6b3  mov     rcx, rax
0x18012a6b6  test    rax, rax
0x18012a6b9  jz      short loc_18012A6D9
0x18012a6bb  mov     rax, [rax]
0x18012a6be  mov     edx, 7F0h
0x18012a6c3  mov     rax, [rax+8]
0x18012a6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a6cc  test    eax, eax
0x18012a6ce  jz      short loc_18012A6D9
0x18012a6d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a6d7  jmp     short loc_18012A6E7
0x18012a6d9  lea     rcx, qword_1801B07E0; this
0x18012a6e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a6e7  cmp     [rcx+8], r12b
0x18012a6eb  jz      short loc_18012A70E
0x18012a6ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a6f2  cmp     [rax+7CCh], edi
0x18012a6f8  jz      short loc_18012A70E
0x18012a6fa  mov     r9d, edi; int
0x18012a6fd  mov     r8d, 591h; int
0x18012a703  mov     rdx, r13; char *
0x18012a706  mov     rcx, rax; this
0x18012a709  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a70e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a715  jb      loc_18012ACE6
0x18012a71b  mov     edx, 0E3h
0x18012a720  mov     [rsp+38h+var_18], edi
0x18012a724  jmp     loc_18012A64D
0x18012a729  cmp     [r14+38h], r12b
0x18012a72d  jz      loc_18012A7E3
0x18012a733  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a73a  mov     edi, 8000FFFFh
0x18012a73f  mov     ebx, edi
0x18012a741  test    rcx, rcx
0x18012a744  jnz     short loc_18012A787
0x18012a746  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a74c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a753  mov     rcx, rax
0x18012a756  test    rax, rax
0x18012a759  jz      short loc_18012A779
0x18012a75b  mov     rax, [rax]
0x18012a75e  mov     edx, 7F0h
0x18012a763  mov     rax, [rax+8]
0x18012a767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a76c  test    eax, eax
0x18012a76e  jz      short loc_18012A779
0x18012a770  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a777  jmp     short loc_18012A787
0x18012a779  lea     rcx, qword_1801B07E0; this
0x18012a780  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a787  cmp     [rcx+8], r12b
0x18012a78b  jz      short loc_18012A7AE
0x18012a78d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a792  cmp     [rax+7CCh], edi
0x18012a798  jz      short loc_18012A7AE
0x18012a79a  mov     r9d, edi; int
0x18012a79d  mov     r8d, 594h; int
0x18012a7a3  mov     rdx, r13; char *
0x18012a7a6  mov     rcx, rax; this
0x18012a7a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a7ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a7b5  jb      loc_18012ACDE
0x18012a7bb  mov     edx, 0E4h
0x18012a7c0  mov     [rsp+38h+var_18], edi
0x18012a7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a7cb  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x18012a7d2  mov     r9, rsi
0x18012a7d5  mov     rcx, [rcx+10h]
0x18012a7d9  call    WPP_SF_qD
0x18012a7de  jmp     loc_18012ACDE
0x18012a7e3  lock dec dword ptr [rsi+1F8h]
0x18012a7ea  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18012a7ee  mov     ecx, [r14+18h]; cbMaxLength
0x18012a7f2  call    cs:__imp_MFCreateMemoryBuffer
0x18012a7f8  mov     ebx, eax
0x18012a7fa  test    eax, eax
0x18012a7fc  jns     loc_18012A891
0x18012a802  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a809  test    rcx, rcx
0x18012a80c  jnz     short loc_18012A84F
0x18012a80e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a814  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a81b  mov     rcx, rax
0x18012a81e  test    rax, rax
0x18012a821  jz      short loc_18012A841
0x18012a823  mov     rax, [rax]
0x18012a826  mov     edx, 7F0h
0x18012a82b  mov     rax, [rax+8]
0x18012a82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a834  test    eax, eax
0x18012a836  jz      short loc_18012A841
0x18012a838  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a83f  jmp     short loc_18012A84F
0x18012a841  lea     rcx, qword_1801B07E0; this
0x18012a848  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a84f  cmp     [rcx+8], r12b
0x18012a853  jz      short loc_18012A876
0x18012a855  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a85a  cmp     [rax+7CCh], ebx
0x18012a860  jz      short loc_18012A876
0x18012a862  mov     r9d, ebx; int
0x18012a865  mov     r8d, 599h; int
0x18012a86b  mov     rdx, r13; char *
0x18012a86e  mov     rcx, rax; this
0x18012a871  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a876  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a87d  jb      loc_18012ACDE
0x18012a883  mov     edx, 0E5h
0x18012a888  mov     [rsp+38h+var_18], ebx
0x18012a88c  jmp     loc_18012A7C4
0x18012a891  mov     rcx, [rbp+ppBuffer]
0x18012a895  lea     rdx, [rbp+arg_18]
0x18012a899  xor     r9d, r9d
0x18012a89c  xor     r8d, r8d
0x18012a89f  mov     rax, [rcx]
0x18012a8a2  mov     rax, [rax+18h]
0x18012a8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a8ab  mov     ebx, eax
0x18012a8ad  test    eax, eax
0x18012a8af  jns     loc_18012A940
0x18012a8b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a8bc  test    rcx, rcx
0x18012a8bf  jnz     short loc_18012A902
0x18012a8c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a8c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a8ce  mov     rcx, rax
0x18012a8d1  test    rax, rax
0x18012a8d4  jz      short loc_18012A8F4
0x18012a8d6  mov     rax, [rax]
0x18012a8d9  mov     edx, 7F0h
0x18012a8de  mov     rax, [rax+8]
0x18012a8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a8e7  test    eax, eax
0x18012a8e9  jz      short loc_18012A8F4
0x18012a8eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a8f2  jmp     short loc_18012A902
0x18012a8f4  lea     rcx, qword_1801B07E0; this
0x18012a8fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a902  cmp     [rcx+8], r12b
0x18012a906  jz      short loc_18012A929
0x18012a908  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a90d  cmp     [rax+7CCh], ebx
0x18012a913  jz      short loc_18012A929
0x18012a915  mov     r9d, ebx; int
0x18012a918  mov     r8d, 59Ah; int
0x18012a91e  mov     rdx, r13; char *
0x18012a921  mov     rcx, rax; this
0x18012a924  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a929  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a930  jb      loc_18012ACDE
0x18012a936  mov     edx, 0E6h
0x18012a93b  jmp     loc_18012A888
0x18012a940  mov     r8d, [r14+18h]; Size
0x18012a944  mov     rdx, [r14+10h]; Src
0x18012a948  mov     rcx, [rbp+arg_18]; void *
0x18012a94c  call    memcpy_0
0x18012a951  mov     rcx, [rbp+ppBuffer]
0x18012a955  mov     edx, [r14+18h]
0x18012a959  mov     rax, [rcx]
0x18012a95c  mov     rax, [rax+30h]
0x18012a960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a965  mov     ebx, eax
0x18012a967  test    eax, eax
0x18012a969  jns     loc_18012AA24
0x18012a96f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a976  test    rcx, rcx
0x18012a979  jnz     short loc_18012A9BC
0x18012a97b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18012a981  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a988  mov     rcx, rax
0x18012a98b  test    rax, rax
0x18012a98e  jz      short loc_18012A9AE
0x18012a990  mov     rax, [rax]
0x18012a993  mov     edx, 7F0h
0x18012a998  mov     rax, [rax+8]
0x18012a99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a9a1  test    eax, eax
0x18012a9a3  jz      short loc_18012A9AE
0x18012a9a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a9ac  jmp     short loc_18012A9BC
0x18012a9ae  lea     rcx, qword_1801B07E0; this
0x18012a9b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18012a9bc  cmp     [rcx+8], r12b
0x18012a9c0  jz      short loc_18012A9E3
0x18012a9c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18012a9c7  cmp     [rax+7CCh], ebx
0x18012a9cd  jz      short loc_18012A9E3
0x18012a9cf  mov     r9d, ebx; int
0x18012a9d2  mov     r8d, 59Dh; int
0x18012a9d8  mov     rdx, r13; char *
0x18012a9db  mov     rcx, rax; this
0x18012a9de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18012a9e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18012a9ea  jb      short loc_18012AA0F
0x18012a9ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a9f3  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x18012a9fa  mov     edx, 0E7h
0x18012a9ff  mov     [rsp+38h+var_18], ebx
0x18012aa03  mov     r9, rsi
0x18012aa06  mov     rcx, [rcx+10h]
0x18012aa0a  call    WPP_SF_qD
0x18012aa0f  mov     rcx, [rbp+ppBuffer]
0x18012aa13  mov     rax, [rcx]
0x18012aa16  mov     rax, [rax+20h]
0x18012aa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aa1f  jmp     loc_18012ACDE
0x18012aa24  mov     rcx, [rbp+ppBuffer]
0x18012aa28  mov     rax, [rcx]
0x18012aa2b  mov     rax, [rax+20h]
0x18012aa2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aa34  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18012aa38  call    cs:__imp_MFCreateSample
0x18012aa3e  mov     ebx, eax
0x18012aa40  test    eax, eax
0x18012aa42  jns     loc_18012AAD3
  ... truncated ...
```
