# CDShowStream::CDShowStream(ulong,CDShowSource *,CDSSampleSink *,long *)

- ea: `0x18004ce6c`
- end: `0x18004d7c4`
- name: `??0CDShowStream@@QEAA@KPEAVCDShowSource@@PEAVCDSSampleSink@@PEAJ@Z`
- size: `2392`
- prototype: `CDShowStream *__usercall@<rax>(CDShowStream *__hidden this@<rcx>, unsigned int@<edx>, struct CDShowSource *@<r8>, struct CDSSampleSink *@<r9>, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x180095050`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180034b38`
- `0x180037120`
- `0x180041d8c`
- `0x18004ce6c`
- `0x18004d7cc`
- `0x18004d868`
- `0x18004d8ec`
- `0x180051ce4`
- `0x18005f78c`
- `0x180073d0c`
- `0x180076738`
- `0x18007c8e8`
- `0x18008aaac`
- `0x180094f1c`
- `0x1800970e0`
- `0x180099bcc`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d064`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d142`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d064`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d27d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d15e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d18d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d33e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d60a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d6af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d0af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d18d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d33e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d60a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d6af`
- `MFPlat!MFCreateStreamDescriptor` at `0x18004d4d6`
- `MFPlat!MFCreateStreamDescriptor` at `0x18004d4d6`

## pseudocode

```c
CDShowStream *__fastcall CDShowStream::CDShowStream(
        CDShowStream *this,
        int a2,
        struct CDShowSource *a3,
        struct CDSSampleSink *a4,
        int *a5)
{
  int *v5; // r15
  int v9; // ecx
  int v10; // r14d
  int v11; // edi
  DWORD v12; // r12d
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  struct CDSSampleSink *v17; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  HANDLE v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  signed int v26; // eax
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  struct CDSSampleSink *v30; // rbx
  unsigned int i; // r15d
  __int64 v32; // rdi
  __int64 v33; // rbx
  struct _RTL_CRITICAL_SECTION *v34; // rdi
  struct IMFMediaType *v35; // rbx
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  CSampleRequestQueueProtected *v46; // rax
  CSampleRequestQueueProtected *v47; // rax
  CSampleRequestQueue *v48; // rax
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  IMFMediaType *v55; // rax
  int v56; // r14d
  int *v57; // rbx
  IMFMediaType **v58; // [rsp+30h] [rbp-20h] BYREF
  DWORD v59; // [rsp+38h] [rbp-18h]
  __int64 v60; // [rsp+3Ch] [rbp-14h]
  IMFMediaType **apMediaTypes; // [rsp+90h] [rbp+40h]
  int v62; // [rsp+98h] [rbp+48h] BYREF
  struct CDSSampleSink *v63; // [rsp+A8h] [rbp+58h]

  v63 = a4;
  v5 = a5;
  CDSSourceObjectBase::CDSSourceObjectBase((CDShowStream *)((char *)this + 8), a5);
  v10 = 1;
  *((_DWORD *)this + 26) = 1148407155;
  *((_DWORD *)this + 27) = 17;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v62 = 1934455620;
    McTemplateU0s4pu_EventWriteTransfer(v9, (unsigned int)Object_Create, (unsigned int)&v62, (_DWORD)this + 104, 17);
  }
  *((_DWORD *)this + 34) = a2;
  v11 = *v5;
  *(_QWORD *)this = &CDShowStream::`vftable'{for `IMFMediaStream'};
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 1) = &CDShowStream::`vftable'{for `CDSSourceObjectBase'};
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 10) = &CDShowStream::`vftable'{for `IMFVideoSampleAllocatorNotify'};
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 11) = &CDShowStream::`vftable'{for `IMFQualityAdvise2'};
  v12 = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 12) = &CDShowStream::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  *(_QWORD *)((char *)this + 172) = 1;
  *(_QWORD *)((char *)this + 180) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = -1;
  apMediaTypes = 0;
  v58 = 0;
  v60 = 0;
  v59 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v62, "CDShowStream::CDShowStream", 84);
  if ( v11 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowStream::CDShowStream", 84, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_73;
    v16 = 12;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids, this, v11);
LABEL_73:
    CDSSampleSinkInputPin::SetMFStream(*((CDSSampleSinkInputPin **)v63 + 5), 0);
    goto LABEL_74;
  }
  *((_QWORD *)this + 14) = a3;
  if ( a3 )
    _InterlockedAdd((volatile signed __int32 *)a3 + 10, 1u);
  v17 = v63;
  *((_QWORD *)this + 15) = v63;
  if ( v17 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 + 1) + 8LL))(*((_QWORD *)v17 + 1));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 19) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v22 + 499) != v11 )
          CallStackContext::TraceFailure(v22, "CDShowStream::CDShowStream", 100, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_73;
      v16 = 13;
      goto LABEL_14;
    }
  }
  v23 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 20) = v23;
  if ( !v23 )
  {
    v26 = GetLastError();
    v11 = v26;
    if ( v26 > 0 )
      v11 = (unsigned __int16)v26 | 0x80070000;
    if ( v11 < 0 )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( *((_DWORD *)v29 + 499) != v11 )
          CallStackContext::TraceFailure(v29, "CDShowStream::CDShowStream", 111, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_73;
      v16 = 14;
      goto LABEL_14;
    }
  }
  v30 = v63;
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 17), v24, v25, this, *((_DWORD *)this + 34), *((_QWORD *)v63 + 5));
  CDSSampleSinkInputPin::SetMFStream(*((CDSSampleSinkInputPin **)v30 + 5), this);
  for ( i = 0; ; ++i )
  {
    v32 = *(_QWORD *)(*((_QWORD *)this + 15) + 40LL);
    v33 = v32 + 360;
    if ( i >= *(_DWORD *)(v32 + 560) )
      break;
    v34 = *(struct _RTL_CRITICAL_SECTION **)(v32 + 64);
    EnterCriticalSection(v34);
    if ( CTPtrArray<CDShowStream,20>::operator[](v33, i) )
    {
      v35 = *(struct IMFMediaType **)CTPtrArray<CDShowStream,20>::operator[](v33, i);
      LeaveCriticalSection(v34);
    }
    else
    {
      LeaveCriticalSection(v34);
      v35 = 0;
    }
    if ( a3 != (struct CDShowSource *)-184LL && *((int *)a3 + 54) > 0 )
    {
      v11 = MediaSubTypeTransform(v35);
      if ( v11 < 0 )
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext(v36);
          if ( *((_DWORD *)v38 + 499) != v11 )
            CallStackContext::TraceFailure(v38, "CDShowStream::CDShowStream", 126, v11);
        }
        if ( g_wppLevels )
        {
          v39 = 16;
          goto LABEL_71;
        }
        goto LABEL_72;
      }
    }
    if ( !(unsigned int)CTEntryArray<IMFMediaType *>::SetSize(&v58, v12 + 1) )
    {
      v41 = CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v41 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v41);
        if ( *((_DWORD *)v42 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v42, "CDShowStream::CDShowStream", 130, -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids,
          this,
          -2147024882);
      goto LABEL_72;
    }
    apMediaTypes = v58;
    v58[v12] = v35;
    if ( v35 )
      ((void (__fastcall *)(struct IMFMediaType *))v35->lpVtbl->AddRef)(v35);
    v12 = v59;
  }
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      18,
      &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids,
      this,
      *((_DWORD *)this + 34),
      v12);
  v11 = MFCreateStreamDescriptor(*((_DWORD *)this + 34), v12, apMediaTypes, (IMFStreamDescriptor **)this + 16);
  if ( v11 < 0 )
  {
    v43 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext(v43);
      if ( *((_DWORD *)v45 + 499) != v11 )
        CallStackContext::TraceFailure(v45, "CDShowStream::CDShowStream", 141, v11);
    }
    if ( g_wppLevels )
    {
      v39 = 19;
LABEL_71:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids, this, v11);
    }
LABEL_72:
    v5 = a5;
    goto LABEL_73;
  }
  *((_DWORD *)this + 46) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 15) + 40LL) + 584LL);
  if ( *(int *)(*((_QWORD *)this + 14) + 216LL) <= 0 )
  {
    v48 = (CSampleRequestQueue *)operator new(0x558u);
    if ( v48 )
    {
      v47 = CSampleRequestQueue::CSampleRequestQueue(v48, this, a5);
      goto LABEL_101;
    }
  }
  else
  {
    v46 = (CSampleRequestQueueProtected *)operator new(0x590u);
    if ( v46 )
    {
      v47 = CSampleRequestQueueProtected::CSampleRequestQueueProtected(v46, this, a5);
      goto LABEL_101;
    }
  }
  v47 = 0;
LABEL_101:
  *((_QWORD *)this + 18) = v47;
  v5 = a5;
  v11 = *a5;
  if ( *a5 < 0 )
  {
    v49 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v50;
      if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      {
        v49 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v49 + 8) )
    {
      v51 = CallStackTracing::GetThreadRelativeContext(v49);
      if ( *((_DWORD *)v51 + 499) != v11 )
        CallStackContext::TraceFailure(v51, "CDShowStream::CDShowStream", 155, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_73;
    v16 = 20;
    goto LABEL_14;
  }
  if ( !v47 )
  {
    v52 = CallStackTracing::s_wpInstance;
    v11 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext(v52);
      if ( *((_DWORD *)v54 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v54, "CDShowStream::CDShowStream", 159, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids,
        this,
        -2147024882);
    goto LABEL_73;
  }
  if ( *(int *)(*((_QWORD *)this + 14) + 216LL) > 0 )
  {
    if ( v12 )
    {
      v55 = *apMediaTypes;
    }
    else
    {
      v55 = 0;
      v10 = 0;
    }
    v56 = -v10;
    v57 = (int *)((unsigned __int64)v55 & -(__int64)(v56 != 0));
    a5 = v57;
    if ( v57 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v57 + 8LL))((unsigned __int64)v55 & -(__int64)(v56 != 0));
    if ( (int)GetStreamTypeForMFMediaType((struct IMFMediaType *)v57, (unsigned int *)this + 50) < 0 )
      *((_DWORD *)this + 50) = -1;
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&a5);
  }
  if ( v11 )
    goto LABEL_73;
LABEL_74:
  *v5 = v11;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v62);
  CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>(&v58);
  return this;
}

```

## disassembly

```asm
0x18004ce6c  mov     [rsp-38h+arg_10], rbx
0x18004ce71  mov     [rsp-38h+arg_18], r9
0x18004ce76  push    rbp
0x18004ce77  push    rsi
0x18004ce78  push    rdi
0x18004ce79  push    r12
0x18004ce7b  push    r13
0x18004ce7d  push    r14
0x18004ce7f  push    r15
0x18004ce81  mov     rbp, rsp
0x18004ce84  sub     rsp, 50h
0x18004ce88  mov     r15, [rbp+arg_20]
0x18004ce8c  mov     edi, edx
0x18004ce8e  mov     rsi, rcx
0x18004ce91  mov     rdx, r15; int *
0x18004ce94  add     rcx, 8; this
0x18004ce98  mov     r13, r8
0x18004ce9b  call    ??0CDSSourceObjectBase@@QEAA@PEAJ@Z; CDSSourceObjectBase::CDSSourceObjectBase(long *)
0x18004cea0  lea     r9, [rsi+68h]
0x18004cea4  mov     r14d, 1
0x18004ceaa  mov     dword ptr [r9], 44734D73h
0x18004ceb1  mov     dword ptr [r9+4], 11h
0x18004ceb9  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, r14b
0x18004cec0  jz      short loc_18004CEDE
0x18004cec2  lea     r8, [rbp+arg_8]
0x18004cec6  mov     [rbp+arg_8], 734D7344h
0x18004cecd  lea     rdx, Object_Create
0x18004ced4  mov     byte ptr [rsp+50h+var_30], 11h
0x18004ced9  call    McTemplateU0s4pu_EventWriteTransfer
0x18004cede  xor     ebx, ebx
0x18004cee0  mov     [rsi+88h], edi
0x18004cee6  mov     edi, [r15]
0x18004cee9  lea     rax, ??_7CDShowStream@@6BIMFMediaStream@@@; const CDShowStream::`vftable'{for `IMFMediaStream'}
0x18004cef0  mov     [rsi], rax
0x18004cef3  lea     rdx, aCdshowstreamCd; "CDShowStream::CDShowStream"
0x18004cefa  lea     rax, ??_7CDShowStream@@6BCDSSourceObjectBase@@@; const CDShowStream::`vftable'{for `CDSSourceObjectBase'}
0x18004cf01  mov     [rsi+70h], rbx
0x18004cf05  mov     [rsi+8], rax
0x18004cf09  lea     r8d, [rbx+54h]; int
0x18004cf0d  lea     rax, ??_7CDShowStream@@6BIMFVideoSampleAllocatorNotify@@@; const CDShowStream::`vftable'{for `IMFVideoSampleAllocatorNotify'}
0x18004cf14  mov     [rsi+78h], rbx
0x18004cf18  mov     [rsi+50h], rax
0x18004cf1c  lea     rcx, [rbp+arg_8]; this
0x18004cf20  lea     rax, ??_7CDShowStream@@6BIMFQualityAdvise2@@@; const CDShowStream::`vftable'{for `IMFQualityAdvise2'}
0x18004cf27  mov     [rsi+80h], rbx
0x18004cf2e  mov     [rsi+58h], rax
0x18004cf32  mov     r12d, ebx
0x18004cf35  lea     rax, ??_7CDShowStream@@6BIMFGetService@@@; const CDShowStream::`vftable'{for `IMFGetService'}
0x18004cf3c  mov     [rsi+90h], rbx
0x18004cf43  mov     [rsi+60h], rax
0x18004cf47  mov     [rsi+98h], rbx
0x18004cf4e  mov     [rsi+0A0h], rbx
0x18004cf55  mov     [rsi+0A8h], ebx
0x18004cf5b  mov     [rsi+0ACh], r14
0x18004cf62  mov     [rsi+0B4h], rbx
0x18004cf69  mov     [rsi+0C0h], rbx
0x18004cf70  mov     dword ptr [rsi+0C8h], 0FFFFFFFFh
0x18004cf7a  mov     [rbp+apMediaTypes], rbx
0x18004cf7e  mov     [rbp+var_20], rbx
0x18004cf82  mov     [rbp+var_14], rbx
0x18004cf86  mov     [rbp+var_18], ebx
0x18004cf89  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004cf8e  test    edi, edi
0x18004cf90  jns     loc_18004D02E
0x18004cf96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cf9d  test    rcx, rcx
0x18004cfa0  jnz     short loc_18004CFE9
0x18004cfa2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cfa9  nop     dword ptr [rax+rax+00h]
0x18004cfae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfb5  mov     rcx, rax
0x18004cfb8  test    rax, rax
0x18004cfbb  jz      short loc_18004CFDB
0x18004cfbd  mov     rax, [rax]
0x18004cfc0  mov     edx, 7F0h
0x18004cfc5  mov     rax, [rax+8]
0x18004cfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfce  test    eax, eax
0x18004cfd0  jz      short loc_18004CFDB
0x18004cfd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfd9  jmp     short loc_18004CFE9
0x18004cfdb  lea     rcx, qword_1800EB130; this
0x18004cfe2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfe9  cmp     [rcx+8], bl
0x18004cfec  jz      short loc_18004D013
0x18004cfee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cff3  cmp     [rax+7CCh], edi
0x18004cff9  jz      short loc_18004D013
0x18004cffb  mov     r9d, edi; int
0x18004cffe  lea     rdx, aCdshowstreamCd; "CDShowStream::CDShowStream"
0x18004d005  mov     r8d, 54h ; 'T'; int
0x18004d00b  mov     rcx, rax; this
0x18004d00e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d013  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18004d01a  jb      loc_18004D3E0
0x18004d020  mov     edx, 0Ch
0x18004d025  mov     [rsp+50h+var_30], edi
0x18004d029  jmp     loc_18004D737
0x18004d02e  mov     [rsi+70h], r13
0x18004d032  test    r13, r13
0x18004d035  jz      short loc_18004D03C
0x18004d037  lock add [r13+28h], r14d
0x18004d03c  mov     rax, [rbp+arg_18]
0x18004d040  mov     [rsi+78h], rax
0x18004d044  test    rax, rax
0x18004d047  jz      short loc_18004D059
0x18004d049  mov     rcx, [rax+8]
0x18004d04d  mov     rax, [rcx]
0x18004d050  mov     rax, [rax+8]
0x18004d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d059  xor     r9d, r9d; lpName
0x18004d05c  xor     r8d, r8d; bInitialState
0x18004d05f  mov     edx, r14d; bManualReset
0x18004d062  xor     ecx, ecx; lpEventAttributes
0x18004d064  call    cs:__imp_CreateEventW
0x18004d06b  nop     dword ptr [rax+rax+00h]
0x18004d070  mov     [rsi+98h], rax
0x18004d077  test    rax, rax
0x18004d07a  jnz     loc_18004D137
0x18004d080  call    cs:__imp_GetLastError
0x18004d087  nop     dword ptr [rax+rax+00h]
0x18004d08c  mov     edi, eax
0x18004d08e  test    eax, eax
0x18004d090  jle     short loc_18004D09B
0x18004d092  movzx   edi, ax
0x18004d095  or      edi, 80070000h
0x18004d09b  test    edi, edi
0x18004d09d  jns     loc_18004D137
0x18004d0a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0aa  test    rcx, rcx
0x18004d0ad  jnz     short loc_18004D0F6
0x18004d0af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d0b6  nop     dword ptr [rax+rax+00h]
0x18004d0bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0c2  mov     rcx, rax
0x18004d0c5  test    rax, rax
0x18004d0c8  jz      short loc_18004D0E8
0x18004d0ca  mov     rax, [rax]
0x18004d0cd  mov     edx, 7F0h
0x18004d0d2  mov     rax, [rax+8]
0x18004d0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0db  test    eax, eax
0x18004d0dd  jz      short loc_18004D0E8
0x18004d0df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0e6  jmp     short loc_18004D0F6
0x18004d0e8  lea     rcx, qword_1800EB130; this
0x18004d0ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0f6  cmp     [rcx+8], bl
0x18004d0f9  jz      short loc_18004D120
0x18004d0fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d100  cmp     [rax+7CCh], edi
0x18004d106  jz      short loc_18004D120
0x18004d108  mov     r9d, edi; int
0x18004d10b  lea     rdx, aCdshowstreamCd; "CDShowStream::CDShowStream"
0x18004d112  mov     r8d, 64h ; 'd'; int
0x18004d118  mov     rcx, rax; this
0x18004d11b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d120  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18004d127  jb      loc_18004D3E0
0x18004d12d  mov     edx, 0Dh
0x18004d132  jmp     loc_18004D025
0x18004d137  xor     r9d, r9d; lpName
0x18004d13a  xor     r8d, r8d; bInitialState
0x18004d13d  mov     edx, r14d; bManualReset
0x18004d140  xor     ecx, ecx; lpEventAttributes
0x18004d142  call    cs:__imp_CreateEventW
0x18004d149  nop     dword ptr [rax+rax+00h]
0x18004d14e  mov     [rsi+0A0h], rax
0x18004d155  test    rax, rax
0x18004d158  jnz     loc_18004D215
0x18004d15e  call    cs:__imp_GetLastError
0x18004d165  nop     dword ptr [rax+rax+00h]
0x18004d16a  mov     edi, eax
0x18004d16c  test    eax, eax
0x18004d16e  jle     short loc_18004D179
0x18004d170  movzx   edi, ax
0x18004d173  or      edi, 80070000h
0x18004d179  test    edi, edi
0x18004d17b  jns     loc_18004D215
0x18004d181  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d188  test    rcx, rcx
0x18004d18b  jnz     short loc_18004D1D4
0x18004d18d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d194  nop     dword ptr [rax+rax+00h]
0x18004d199  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1a0  mov     rcx, rax
0x18004d1a3  test    rax, rax
0x18004d1a6  jz      short loc_18004D1C6
0x18004d1a8  mov     rax, [rax]
0x18004d1ab  mov     edx, 7F0h
0x18004d1b0  mov     rax, [rax+8]
0x18004d1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1b9  test    eax, eax
0x18004d1bb  jz      short loc_18004D1C6
0x18004d1bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1c4  jmp     short loc_18004D1D4
0x18004d1c6  lea     rcx, qword_1800EB130; this
0x18004d1cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1d4  cmp     [rcx+8], bl
0x18004d1d7  jz      short loc_18004D1FE
0x18004d1d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d1de  cmp     [rax+7CCh], edi
0x18004d1e4  jz      short loc_18004D1FE
0x18004d1e6  mov     r9d, edi; int
0x18004d1e9  lea     rdx, aCdshowstreamCd; "CDShowStream::CDShowStream"
0x18004d1f0  mov     r8d, 6Fh ; 'o'; int
0x18004d1f6  mov     rcx, rax; this
0x18004d1f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d1fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18004d205  jb      loc_18004D3E0
0x18004d20b  mov     edx, 0Eh
0x18004d210  jmp     loc_18004D025
0x18004d215  cmp     cs:byte_1800EACCB, 8
0x18004d21c  mov     rbx, [rbp+arg_18]
0x18004d220  jb      short loc_18004D24B
0x18004d222  mov     rax, [rbx+28h]
0x18004d226  mov     r9, rsi
0x18004d229  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d230  mov     [rsp+50h+var_28], rax
0x18004d235  mov     eax, [rsi+88h]
0x18004d23b  mov     [rsp+50h+var_30], eax
0x18004d23f  mov     rcx, [rcx+88h]
0x18004d246  call    WPP_SF_qdq
0x18004d24b  mov     rcx, [rbx+28h]; this
0x18004d24f  mov     rdx, rsi; struct CDShowStream *
0x18004d252  call    ?SetMFStream@CDSSampleSinkInputPin@@QEAAXPEAVCDShowStream@@@Z; CDSSampleSinkInputPin::SetMFStream(CDShowStream *)
0x18004d257  xor     r15d, r15d
0x18004d25a  mov     rax, [rsi+78h]
0x18004d25e  mov     rdi, [rax+28h]
0x18004d262  lea     rbx, [rdi+168h]
0x18004d269  cmp     r15d, [rbx+0C8h]
0x18004d270  jnb     loc_18004D485
0x18004d276  mov     rdi, [rdi+40h]
0x18004d27a  mov     rcx, rdi; lpCriticalSection
0x18004d27d  call    cs:__imp_EnterCriticalSection
0x18004d284  nop     dword ptr [rax+rax+00h]
0x18004d289  mov     edx, r15d
0x18004d28c  mov     rcx, rbx
0x18004d28f  call    ??A?$CTPtrArray@VCDShowStream@@$0BE@@@QEBAPEAVCDShowStream@@K@Z; CTPtrArray<CDShowStream,20>::operator[](ulong)
0x18004d294  test    rax, rax
0x18004d297  jz      short loc_18004D2B8
0x18004d299  mov     edx, r15d
0x18004d29c  mov     rcx, rbx
0x18004d29f  call    ??A?$CTPtrArray@VCDShowStream@@$0BE@@@QEBAPEAVCDShowStream@@K@Z; CTPtrArray<CDShowStream,20>::operator[](ulong)
0x18004d2a4  mov     rcx, rdi; lpCriticalSection
0x18004d2a7  mov     rbx, [rax]
0x18004d2aa  call    cs:__imp_LeaveCriticalSection
0x18004d2b1  nop     dword ptr [rax+rax+00h]
0x18004d2b6  jmp     short loc_18004D2C9
0x18004d2b8  mov     rcx, rdi; lpCriticalSection
0x18004d2bb  call    cs:__imp_LeaveCriticalSection
0x18004d2c2  nop     dword ptr [rax+rax+00h]
0x18004d2c7  xor     ebx, ebx
0x18004d2c9  lea     rax, [r13+0B8h]
0x18004d2d0  test    rax, rax
0x18004d2d3  jz      short loc_18004D2ED
0x18004d2d5  cmp     dword ptr [r13+0D8h], 0
0x18004d2dd  jle     short loc_18004D2ED
0x18004d2df  mov     rcx, rbx; struct IMFMediaType *
0x18004d2e2  call    ?MediaSubTypeTransform@@YAJPEAUIMFMediaType@@@Z; MediaSubTypeTransform(IMFMediaType *)
0x18004d2e7  mov     edi, eax
0x18004d2e9  test    eax, eax
0x18004d2eb  js      short loc_18004D332
0x18004d2ed  lea     edx, [r12+1]
0x18004d2f2  lea     rcx, [rbp+var_20]
0x18004d2f6  call    ?SetSize@?$CTEntryArray@PEAUIMFMediaType@@@@QEAAHKK@Z; CTEntryArray<IMFMediaType *>::SetSize(ulong,ulong)
0x18004d2fb  test    eax, eax
0x18004d2fd  jz      loc_18004D420
0x18004d303  mov     rcx, [rbp+var_20]
0x18004d307  mov     eax, r12d
0x18004d30a  mov     [rbp+apMediaTypes], rcx
0x18004d30e  mov     [rcx+rax*8], rbx
0x18004d312  test    rbx, rbx
0x18004d315  jz      short loc_18004D326
0x18004d317  mov     rax, [rbx]
0x18004d31a  mov     rcx, rbx
0x18004d31d  mov     rax, [rax+8]
0x18004d321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d326  mov     r12d, [rbp+var_18]
0x18004d32a  add     r15d, r14d
0x18004d32d  jmp     loc_18004D25A
0x18004d332  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d339  test    rcx, rcx
0x18004d33c  jnz     short loc_18004D385
0x18004d33e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d345  nop     dword ptr [rax+rax+00h]
0x18004d34a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d351  mov     rcx, rax
0x18004d354  test    rax, rax
0x18004d357  jz      short loc_18004D377
0x18004d359  mov     rax, [rax]
0x18004d35c  mov     edx, 7F0h
0x18004d361  mov     rax, [rax+8]
0x18004d365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d36a  test    eax, eax
0x18004d36c  jz      short loc_18004D377
0x18004d36e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d375  jmp     short loc_18004D385
0x18004d377  lea     rcx, qword_1800EB130; this
0x18004d37e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
