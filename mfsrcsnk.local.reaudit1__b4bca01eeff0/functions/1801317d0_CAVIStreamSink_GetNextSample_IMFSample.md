# CAVIStreamSink::GetNextSample(IMFSample * *)

- ea: `0x1801317d0`
- end: `0x180131fea`
- name: `?GetNextSample@CAVIStreamSink@@AEAAJPEAPEAUIMFSample@@@Z`
- size: `2074`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample **)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180131ff0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x18012f8c8`
- `0x1801317d0`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180131fca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801317f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801317f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013184d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013192a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801319d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131aa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131d02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131db4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131e66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131f18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013184d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013192a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801319d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131aa4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131d02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131db4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131e66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180131f18`
- `MFPlat!MFCreateMemoryBuffer` at `0x180131a82`
- `MFPlat!MFCreateMemoryBuffer` at `0x180131a82`
- `MFPlat!MFCreateSample` at `0x180131ce0`
- `MFPlat!MFCreateSample` at `0x180131ce0`

## string_xrefs

- `0x180131803`: `CAVIStreamSink::GetNextSample`

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
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v16 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v27 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v39 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                  v36 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v33 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v30 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v23 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v19 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v13 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1801317d0  push    rbp
0x1801317d2  push    rbx
0x1801317d3  push    rsi
0x1801317d4  push    rdi
0x1801317d5  push    r12
0x1801317d7  push    r13
0x1801317d9  push    r14
0x1801317db  push    r15
0x1801317dd  mov     rbp, rsp
0x1801317e0  sub     rsp, 38h
0x1801317e4  lea     r15, [rcx+218h]
0x1801317eb  mov     rsi, rcx
0x1801317ee  mov     rcx, r15; lpCriticalSection
0x1801317f1  mov     rdi, rdx
0x1801317f4  call    cs:__imp_EnterCriticalSection
0x1801317fb  nop     dword ptr [rax+rax+00h]
0x180131800  mov     rax, rdi
0x180131803  lea     r13, aCavistreamsink_21; "CAVIStreamSink::GetNextSample"
0x18013180a  neg     rax
0x18013180d  lea     rcx, [rbp+arg_0]; this
0x180131811  mov     r8d, 586h; int
0x180131817  mov     rdx, r13; char *
0x18013181a  sbb     ebx, ebx
0x18013181c  not     ebx
0x18013181e  and     ebx, 80004003h
0x180131824  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180131829  xor     r12d, r12d
0x18013182c  mov     [rbp+ppBuffer], r12
0x180131830  mov     [rbp+ppIMFSample], r12
0x180131834  mov     [rbp+arg_18], r12
0x180131838  test    rdi, rdi
0x18013183b  jnz     loc_1801318F0
0x180131841  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131848  test    rcx, rcx
0x18013184b  jnz     short loc_180131894
0x18013184d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180131854  nop     dword ptr [rax+rax+00h]
0x180131859  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180131860  mov     rcx, rax
0x180131863  test    rax, rax
0x180131866  jz      short loc_180131886
0x180131868  mov     rax, [rax]
0x18013186b  mov     edx, 7F0h
0x180131870  mov     rax, [rax+8]
0x180131874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131879  test    eax, eax
0x18013187b  jz      short loc_180131886
0x18013187d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131884  jmp     short loc_180131894
0x180131886  lea     rcx, qword_1801B97E0; this
0x18013188d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131894  cmp     [rcx+8], r12b
0x180131898  jz      short loc_1801318BB
0x18013189a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013189f  cmp     [rax+7CCh], ebx
0x1801318a5  jz      short loc_1801318BB
0x1801318a7  mov     r9d, ebx; int
0x1801318aa  mov     r8d, 58Dh; int
0x1801318b0  mov     rdx, r13; char *
0x1801318b3  mov     rcx, rax; this
0x1801318b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801318bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801318c2  jb      loc_180131FAC
0x1801318c8  mov     edx, 0E2h
0x1801318cd  mov     [rsp+38h+var_18], ebx
0x1801318d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801318d8  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1801318df  mov     r9, rsi
0x1801318e2  mov     rcx, [rcx+10h]
0x1801318e6  call    WPP_SF_qD
0x1801318eb  jmp     loc_180131FAC
0x1801318f0  mov     [rdi], r12
0x1801318f3  mov     r14, [rsi+208h]
0x1801318fa  dec     dword ptr [rsi+200h]
0x180131900  mov     rax, [r14+8]
0x180131904  mov     rcx, [r14]
0x180131907  mov     [rax], rcx
0x18013190a  mov     [rcx+8], rax
0x18013190e  test    r14, r14
0x180131911  jnz     loc_1801319B3
0x180131917  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013191e  mov     edi, 8000FFFFh
0x180131923  mov     ebx, edi
0x180131925  test    rcx, rcx
0x180131928  jnz     short loc_180131971
0x18013192a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180131931  nop     dword ptr [rax+rax+00h]
0x180131936  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013193d  mov     rcx, rax
0x180131940  test    rax, rax
0x180131943  jz      short loc_180131963
0x180131945  mov     rax, [rax]
0x180131948  mov     edx, 7F0h
0x18013194d  mov     rax, [rax+8]
0x180131951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131956  test    eax, eax
0x180131958  jz      short loc_180131963
0x18013195a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131961  jmp     short loc_180131971
0x180131963  lea     rcx, qword_1801B97E0; this
0x18013196a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131971  cmp     [rcx+8], r12b
0x180131975  jz      short loc_180131998
0x180131977  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013197c  cmp     [rax+7CCh], edi
0x180131982  jz      short loc_180131998
0x180131984  mov     r9d, edi; int
0x180131987  mov     r8d, 591h; int
0x18013198d  mov     rdx, r13; char *
0x180131990  mov     rcx, rax; this
0x180131993  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180131998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013199f  jb      loc_180131FAC
0x1801319a5  mov     edx, 0E3h
0x1801319aa  mov     [rsp+38h+var_18], edi
0x1801319ae  jmp     loc_1801318D1
0x1801319b3  cmp     [r14+38h], r12b
0x1801319b7  jz      loc_180131A73
0x1801319bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801319c4  mov     edi, 8000FFFFh
0x1801319c9  mov     ebx, edi
0x1801319cb  test    rcx, rcx
0x1801319ce  jnz     short loc_180131A17
0x1801319d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801319d7  nop     dword ptr [rax+rax+00h]
0x1801319dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801319e3  mov     rcx, rax
0x1801319e6  test    rax, rax
0x1801319e9  jz      short loc_180131A09
0x1801319eb  mov     rax, [rax]
0x1801319ee  mov     edx, 7F0h
0x1801319f3  mov     rax, [rax+8]
0x1801319f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801319fc  test    eax, eax
0x1801319fe  jz      short loc_180131A09
0x180131a00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131a07  jmp     short loc_180131A17
0x180131a09  lea     rcx, qword_1801B97E0; this
0x180131a10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131a17  cmp     [rcx+8], r12b
0x180131a1b  jz      short loc_180131A3E
0x180131a1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180131a22  cmp     [rax+7CCh], edi
0x180131a28  jz      short loc_180131A3E
0x180131a2a  mov     r9d, edi; int
0x180131a2d  mov     r8d, 594h; int
0x180131a33  mov     rdx, r13; char *
0x180131a36  mov     rcx, rax; this
0x180131a39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180131a3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180131a45  jb      loc_180131FA4
0x180131a4b  mov     edx, 0E4h
0x180131a50  mov     [rsp+38h+var_18], edi
0x180131a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180131a5b  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x180131a62  mov     r9, rsi
0x180131a65  mov     rcx, [rcx+10h]
0x180131a69  call    WPP_SF_qD
0x180131a6e  jmp     loc_180131FA4
0x180131a73  lock dec dword ptr [rsi+1F8h]
0x180131a7a  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180131a7e  mov     ecx, [r14+18h]; cbMaxLength
0x180131a82  call    cs:__imp_MFCreateMemoryBuffer
0x180131a89  nop     dword ptr [rax+rax+00h]
0x180131a8e  mov     ebx, eax
0x180131a90  test    eax, eax
0x180131a92  jns     loc_180131B2D
0x180131a98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131a9f  test    rcx, rcx
0x180131aa2  jnz     short loc_180131AEB
0x180131aa4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180131aab  nop     dword ptr [rax+rax+00h]
0x180131ab0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180131ab7  mov     rcx, rax
0x180131aba  test    rax, rax
0x180131abd  jz      short loc_180131ADD
0x180131abf  mov     rax, [rax]
0x180131ac2  mov     edx, 7F0h
0x180131ac7  mov     rax, [rax+8]
0x180131acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131ad0  test    eax, eax
0x180131ad2  jz      short loc_180131ADD
0x180131ad4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131adb  jmp     short loc_180131AEB
0x180131add  lea     rcx, qword_1801B97E0; this
0x180131ae4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131aeb  cmp     [rcx+8], r12b
0x180131aef  jz      short loc_180131B12
0x180131af1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180131af6  cmp     [rax+7CCh], ebx
0x180131afc  jz      short loc_180131B12
0x180131afe  mov     r9d, ebx; int
0x180131b01  mov     r8d, 599h; int
0x180131b07  mov     rdx, r13; char *
0x180131b0a  mov     rcx, rax; this
0x180131b0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180131b12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180131b19  jb      loc_180131FA4
0x180131b1f  mov     edx, 0E5h
0x180131b24  mov     [rsp+38h+var_18], ebx
0x180131b28  jmp     loc_180131A54
0x180131b2d  mov     rcx, [rbp+ppBuffer]
0x180131b31  lea     rdx, [rbp+arg_18]
0x180131b35  xor     r9d, r9d
0x180131b38  xor     r8d, r8d
0x180131b3b  mov     rax, [rcx]
0x180131b3e  mov     rax, [rax+18h]
0x180131b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131b47  mov     ebx, eax
0x180131b49  test    eax, eax
0x180131b4b  jns     loc_180131BE2
0x180131b51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131b58  test    rcx, rcx
0x180131b5b  jnz     short loc_180131BA4
0x180131b5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180131b64  nop     dword ptr [rax+rax+00h]
0x180131b69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180131b70  mov     rcx, rax
0x180131b73  test    rax, rax
0x180131b76  jz      short loc_180131B96
0x180131b78  mov     rax, [rax]
0x180131b7b  mov     edx, 7F0h
0x180131b80  mov     rax, [rax+8]
0x180131b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131b89  test    eax, eax
0x180131b8b  jz      short loc_180131B96
0x180131b8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131b94  jmp     short loc_180131BA4
0x180131b96  lea     rcx, qword_1801B97E0; this
0x180131b9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131ba4  cmp     [rcx+8], r12b
0x180131ba8  jz      short loc_180131BCB
0x180131baa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180131baf  cmp     [rax+7CCh], ebx
0x180131bb5  jz      short loc_180131BCB
0x180131bb7  mov     r9d, ebx; int
0x180131bba  mov     r8d, 59Ah; int
0x180131bc0  mov     rdx, r13; char *
0x180131bc3  mov     rcx, rax; this
0x180131bc6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180131bcb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180131bd2  jb      loc_180131FA4
0x180131bd8  mov     edx, 0E6h
0x180131bdd  jmp     loc_180131B24
0x180131be2  mov     r8d, [r14+18h]; Size
0x180131be6  mov     rdx, [r14+10h]; Src
0x180131bea  mov     rcx, [rbp+arg_18]; void *
0x180131bee  call    memcpy_0
0x180131bf3  mov     rcx, [rbp+ppBuffer]
0x180131bf7  mov     edx, [r14+18h]
0x180131bfb  mov     rax, [rcx]
0x180131bfe  mov     rax, [rax+30h]
0x180131c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131c07  mov     ebx, eax
0x180131c09  test    eax, eax
0x180131c0b  jns     loc_180131CCC
0x180131c11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131c18  test    rcx, rcx
0x180131c1b  jnz     short loc_180131C64
0x180131c1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180131c24  nop     dword ptr [rax+rax+00h]
0x180131c29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180131c30  mov     rcx, rax
0x180131c33  test    rax, rax
0x180131c36  jz      short loc_180131C56
0x180131c38  mov     rax, [rax]
0x180131c3b  mov     edx, 7F0h
0x180131c40  mov     rax, [rax+8]
0x180131c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131c49  test    eax, eax
0x180131c4b  jz      short loc_180131C56
0x180131c4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180131c54  jmp     short loc_180131C64
0x180131c56  lea     rcx, qword_1801B97E0; this
0x180131c5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180131c64  cmp     [rcx+8], r12b
0x180131c68  jz      short loc_180131C8B
0x180131c6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180131c6f  cmp     [rax+7CCh], ebx
0x180131c75  jz      short loc_180131C8B
0x180131c77  mov     r9d, ebx; int
0x180131c7a  mov     r8d, 59Dh; int
0x180131c80  mov     rdx, r13; char *
0x180131c83  mov     rcx, rax; this
0x180131c86  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180131c8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180131c92  jb      short loc_180131CB7
0x180131c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180131c9b  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x180131ca2  mov     edx, 0E7h
0x180131ca7  mov     [rsp+38h+var_18], ebx
0x180131cab  mov     r9, rsi
0x180131cae  mov     rcx, [rcx+10h]
0x180131cb2  call    WPP_SF_qD
0x180131cb7  mov     rcx, [rbp+ppBuffer]
0x180131cbb  mov     rax, [rcx]
0x180131cbe  mov     rax, [rax+20h]
0x180131cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131cc7  jmp     loc_180131FA4
0x180131ccc  mov     rcx, [rbp+ppBuffer]
  ... truncated ...
```
