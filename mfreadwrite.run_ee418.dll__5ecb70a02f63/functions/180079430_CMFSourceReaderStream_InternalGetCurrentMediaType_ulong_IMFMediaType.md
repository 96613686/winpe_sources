# CMFSourceReaderStream::InternalGetCurrentMediaType(ulong,IMFMediaType * *)

- ea: `0x180079430`
- end: `0x180079e76`
- name: `?InternalGetCurrentMediaType@CMFSourceReaderStream@@AEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `2630`
- prototype: `__int64 __fastcall(CMFSourceReaderStream *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `11`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180016be0`
- `0x1800471a0`
- `0x180047e88`
- `0x180078130`
- `0x18007a720`
- `0x18007ad5c`
- `0x1800941a4`
- `0x18009fe00`
- `0x1800b8020`
- `0x1800c3d30`
- `0x1800d5070`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x180014a60`
- `0x1800252a0`
- `0x180079410`
- `0x180079430`
- `0x18007a6c4`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180079584`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007947b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007947b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007975f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007982c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800798ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079a63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079ba9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079cd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079e1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007975f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007982c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800798ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079a63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079ba9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079cd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079c85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079dce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800796fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800797d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007988c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079a09`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079b4f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079c7a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079dc3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800796fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800797d2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007988c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079a09`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079b4f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079c7a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180079dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007961c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007971f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800797f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800798ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007999e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079a2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079ae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079b70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079d3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079de4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007961c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007971f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800797f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800798ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007999e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079a2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079ae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079b70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079d3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079de4`
- `MFPlat!MFCreateMediaType` at `0x180079545`
- `MFPlat!MFCreateMediaType` at `0x180079545`

## string_xrefs

- `0x18007944f`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079778`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x18007983f`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079906`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079a76`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079bbc`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079ce7`: `CMFSourceReaderStream::InternalGetCurrentMediaType`
- `0x180079e30`: `CMFSourceReaderStream::InternalGetCurrentMediaType`

## pseudocode

```c
__int64 __fastcall CMFSourceReaderStream::InternalGetCurrentMediaType(
        CMFSourceReaderStream *this,
        unsigned int a2,
        struct IMFMediaType **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  int v7; // esi
  struct IMFMediaType *v8; // rbx
  struct IMFMediaType *v9; // rcx
  HRESULT v10; // edi
  unsigned int *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  CallStackTracing *v19; // rsi
  CallStackTracing *v20; // rax
  __int64 v21; // rdx
  CallStackTracing *v22; // rbx
  CallStackTracing *v23; // rbx
  CallStackContext *v24; // rsi
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  CallStackTracing *v29; // rbx
  CallStackTracing *v30; // rax
  __int64 v31; // rax
  CallStackContext *v32; // r12
  DWORD v33; // r13d
  CallStackContext *v34; // rax
  __int64 v35; // rdx
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 v38; // rax
  CallStackContext *v39; // rsi
  DWORD v40; // r12d
  CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  CallStackTracing *v44; // rbx
  CallStackTracing *v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  CallStackTracing *v49; // rsi
  CallStackTracing *v50; // rax
  CallStackContext *v51; // r12
  DWORD v52; // r13d
  CallStackContext *v53; // rax
  __int64 v54; // rdx
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  CallStackTracing *v60; // rsi
  CallStackTracing *v61; // rax
  CallStackContext *v62; // r12
  DWORD v63; // r13d
  CallStackContext *v64; // rax
  __int64 v65; // rdx
  CallStackTracing *v66; // rcx
  CallStackTracing *v67; // rax
  __int64 v68; // rax
  CallStackTracing *v69; // rsi
  CallStackTracing *v70; // rax
  CallStackContext *v71; // r12
  DWORD v72; // r13d
  CallStackContext *v73; // rax
  __int64 v74; // rdx
  CallStackTracing *v75; // rcx
  CallStackTracing *v76; // rax
  __int64 v77; // rax
  CallStackTracing *v78; // rsi
  CallStackTracing *v79; // rax
  CallStackContext *v80; // r12
  DWORD v81; // r13d
  CallStackContext *v82; // rax
  __int64 v83; // rdx
  CallStackTracing *v84; // rcx
  CallStackTracing *v85; // rax
  __int64 v86; // rax
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-10h] BYREF
  struct CMFSourceReaderStream::CSourceReaderStreamInfo *v88; // [rsp+80h] [rbp+40h] BYREF
  struct IMFMediaType *v89; // [rsp+98h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v88,
    "CMFSourceReaderStream::InternalGetCurrentMediaType",
    3770);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v88 = 0;
  v89 = 0;
  ppMFType = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 23) )
  {
    v23 = CallStackTracing::s_wpInstance;
    v10 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v23 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v24 = (CallStackTracing *)((char *)v23 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v23 + 3));
      if ( Value )
      {
        v24 = Value;
      }
      else if ( !GetLastError() )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v28, v27);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
        if ( v31 )
          v24 = (CallStackContext *)v31;
      }
      SetLastError(LastError);
      v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      if ( *((_DWORD *)v24 + 499) != -1072873851 )
        CallStackContext::TraceFailure(v24, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3783, -1072873851);
    }
    if ( g_wppLevels )
    {
      v21 = 348;
      goto LABEL_160;
    }
    goto LABEL_18;
  }
  v7 = (*(__int64 (__fastcall **)(CMFSourceReaderStream *, _QWORD))(*(_QWORD *)this + 64LL))(this, a2);
  if ( v7 && *((_DWORD *)this + 46) )
  {
    CMFSourceReaderStream::CSourceReaderStreamInfo::GetInternalMediaType(
      *((CMFSourceReaderStream::CSourceReaderStreamInfo **)this + 202),
      &v89);
    if ( !v89 )
    {
      v19 = CallStackTracing::s_wpInstance;
      v10 = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v32 = (CallStackTracing *)((char *)v19 + 208);
        v33 = GetLastError();
        v34 = (CallStackContext *)TlsGetValue(*((_DWORD *)v19 + 3));
        if ( v34 )
        {
          v32 = v34;
        }
        else if ( !GetLastError() )
        {
          v36 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v38 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
          if ( v38 )
            v32 = (CallStackContext *)v38;
        }
        SetLastError(v33);
        if ( *((_DWORD *)v32 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v32, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3794, -2147418113);
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      }
      if ( g_wppLevels )
      {
        v21 = 349;
LABEL_160:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_1e4a582d86dd358662df8db49e1fb4d7_Traceguids, this, v10);
        goto LABEL_18;
      }
      goto LABEL_18;
    }
LABEL_15:
    v10 = MFCreateMediaType(&ppMFType);
    if ( v10 < 0 )
    {
      v69 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12);
        CallStackTracing::s_wpInstance = v70;
        if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
        {
          v69 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v69 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v69 + 8) )
      {
        v71 = (CallStackTracing *)((char *)v69 + 208);
        v72 = GetLastError();
        v73 = (CallStackContext *)TlsGetValue(*((_DWORD *)v69 + 3));
        if ( v73 )
        {
          v71 = v73;
        }
        else if ( !GetLastError() )
        {
          v75 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
            CallStackTracing::s_wpInstance = v76;
            if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
            {
              v75 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v75 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v77 = (**(__int64 (__fastcall ***)(CallStackTracing *))v75)(v75);
          if ( v77 )
            v71 = (CallStackContext *)v77;
        }
        SetLastError(v72);
        if ( *((_DWORD *)v71 + 499) != v10 )
          CallStackContext::TraceFailure(v71, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3848, v10);
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      }
      if ( g_wppLevels )
      {
        v21 = 353;
        goto LABEL_160;
      }
    }
    else
    {
      v10 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v89->lpVtbl->CopyAllItems)(v89, ppMFType);
      if ( v10 >= 0 )
      {
        *a3 = ppMFType;
        ppMFType = 0;
        goto LABEL_18;
      }
      v78 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v15, v14);
        CallStackTracing::s_wpInstance = v79;
        if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
        {
          v78 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v78 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v78 + 8) )
      {
        v80 = (CallStackTracing *)((char *)v78 + 208);
        v81 = GetLastError();
        v82 = (CallStackContext *)TlsGetValue(*((_DWORD *)v78 + 3));
        if ( v82 )
        {
          v80 = v82;
        }
        else if ( !GetLastError() )
        {
          v84 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83);
            CallStackTracing::s_wpInstance = v85;
            if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
            {
              v84 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v84 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v86 = (**(__int64 (__fastcall ***)(CallStackTracing *))v84)(v84);
          if ( v86 )
            v80 = (CallStackContext *)v86;
        }
        SetLastError(v81);
        if ( *((_DWORD *)v80 + 499) != v10 )
          CallStackContext::TraceFailure(v80, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3850, v10);
        v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      }
      if ( g_wppLevels )
      {
        v21 = 354;
        goto LABEL_160;
      }
    }
    goto LABEL_18;
  }
  if ( !*((_QWORD *)this + 204) )
  {
    if ( (unsigned int)CMFSourceReaderStream::IsUsingCapturePlugin(this) )
      v8 = (struct IMFMediaType *)*((_QWORD *)this + 207);
    else
      v8 = (struct IMFMediaType *)*((_QWORD *)this + 159);
    v9 = v89;
    if ( v89 != v8 )
    {
      if ( v8 )
      {
        ((void (__fastcall *)(struct IMFMediaType *))v8->lpVtbl->AddRef)(v8);
        v9 = v89;
      }
      if ( v9 )
        ((void (__fastcall *)(struct IMFMediaType *))v9->lpVtbl->Release)(v9);
      v89 = v8;
    }
    goto LABEL_15;
  }
  v10 = CMFSourceReaderStream::LookupStreamInfo(this, a2, &v88);
  if ( v10 >= 0 )
  {
    v11 = (unsigned int *)v88;
    if ( v7 || (*((_BYTE *)v88 + 12) & 1) != 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType **))(**((_QWORD **)this + 204) + 72LL))(
             *((_QWORD *)this + 204),
             *((unsigned int *)v88 + 1),
             &v89) < 0 )
      {
        CMFSourceReaderStream::CSourceReaderStreamInfo::GetInternalMediaType(
          (CMFSourceReaderStream::CSourceReaderStreamInfo *)v11,
          &v89);
        if ( !v89 )
        {
          v60 = CallStackTracing::s_wpInstance;
          v10 = -1072861856;
          if ( !CallStackTracing::s_wpInstance )
          {
            v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v59, v58);
            CallStackTracing::s_wpInstance = v61;
            if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
            {
              v60 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v60 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v62 = (CallStackTracing *)((char *)v60 + 208);
            v63 = GetLastError();
            v64 = (CallStackContext *)TlsGetValue(*((_DWORD *)v60 + 3));
            if ( v64 )
            {
              v62 = v64;
            }
            else if ( !GetLastError() )
            {
              v66 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65);
                CallStackTracing::s_wpInstance = v67;
                if ( v67
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
                {
                  v66 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v66 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v68 = (**(__int64 (__fastcall ***)(CallStackTracing *))v66)(v66);
              if ( v68 )
                v62 = (CallStackContext *)v68;
            }
            SetLastError(v63);
            if ( *((_DWORD *)v62 + 499) != -1072861856 )
              CallStackContext::TraceFailure(
                v62,
                "CMFSourceReaderStream::InternalGetCurrentMediaType",
                3823,
                -1072861856);
            v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
          }
          if ( g_wppLevels )
          {
            v21 = 351;
            goto LABEL_160;
          }
          goto LABEL_18;
        }
      }
    }
    else
    {
      CMFSourceReaderStream::CSourceReaderStreamInfo::GetInternalMediaType(v88, &v89);
      if ( !v89 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IMFMediaType **))(**((_QWORD **)this + 204)
                                                                                        + 64LL))(
                *((_QWORD *)this + 204),
                v11[1],
                0,
                &v89);
        if ( v10 < 0 )
        {
          v49 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v48, v47);
            CallStackTracing::s_wpInstance = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v49 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v49 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v49 + 8) )
          {
            v51 = (CallStackTracing *)((char *)v49 + 208);
            v52 = GetLastError();
            v53 = (CallStackContext *)TlsGetValue(*((_DWORD *)v49 + 3));
            if ( v53 )
            {
              v51 = v53;
            }
            else if ( !GetLastError() )
            {
              v55 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                CallStackTracing::s_wpInstance = v56;
                if ( v56
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
                {
                  v55 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v55 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
              if ( v57 )
                v51 = (CallStackContext *)v57;
            }
            SetLastError(v52);
            if ( *((_DWORD *)v51 + 499) != v10 )
              CallStackContext::TraceFailure(v51, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3840, v10);
            v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
          }
          if ( g_wppLevels )
          {
            v21 = 352;
            goto LABEL_160;
          }
          goto LABEL_18;
        }
      }
    }
    goto LABEL_15;
  }
  v22 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v22 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v39 = (CallStackTracing *)((char *)v22 + 208);
    v40 = GetLastError();
    v41 = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v41 )
    {
      v39 = v41;
    }
    else if ( !GetLastError() )
    {
      v44 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v43, v42);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v46 = (**(__int64 (__fastcall ***)(CallStackTracing *))v44)(v44);
      if ( v46 )
        v39 = (CallStackContext *)v46;
    }
    SetLastError(v40);
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
    if ( *((_DWORD *)v39 + 499) != v10 )
      CallStackContext::TraceFailure(v39, "CMFSourceReaderStream::InternalGetCurrentMediaType", 3809, v10);
  }
  if ( g_wppLevels )
  {
    v21 = 350;
    goto LABEL_160;
  }
LABEL_18:
  LeaveCriticalSection(v6);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  if ( v89 )
    ((void (__fastcall *)(struct IMFMediaType *))v89->lpVtbl->Release)(v89);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v88);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180079430  mov     [rsp-38h+arg_8], rbx
0x180079435  push    rbp
0x180079436  push    rsi
0x180079437  push    rdi
0x180079438  push    r12
0x18007943a  push    r13
0x18007943c  push    r14
0x18007943e  push    r15
0x180079440  mov     rbp, rsp
0x180079443  sub     rsp, 40h
0x180079447  mov     r14, r8
0x18007944a  mov     ebx, edx
0x18007944c  mov     r15, rcx
0x18007944f  lea     rdx, aCmfsourcereade_176; "CMFSourceReaderStream::InternalGetCurre"...
0x180079456  mov     r8d, 0EBAh; int
0x18007945c  lea     rcx, [rbp+arg_0]; this
0x180079460  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180079465  xor     r13d, r13d
0x180079468  lea     r12, [r15+30h]
0x18007946c  mov     rcx, r12; lpCriticalSection
0x18007946f  mov     [rbp+arg_0], r13
0x180079473  mov     [rbp+arg_18], r13
0x180079477  mov     [rbp+ppMFType], r13
0x18007947b  call    cs:__imp_EnterCriticalSection
0x180079481  cmp     [r15+5Ch], r13d
0x180079485  jnz     loc_1800796A1
0x18007948b  mov     rax, [r15]
0x18007948e  mov     edx, ebx
0x180079490  mov     rcx, r15
0x180079493  mov     rax, [rax+40h]
0x180079497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007949c  mov     esi, eax
0x18007949e  test    eax, eax
0x1800794a0  jnz     loc_1800795D7
0x1800794a6  mov     rcx, r15; this
0x1800794a9  cmp     [r15+660h], r13
0x1800794b0  jnz     short loc_1800794FE
0x1800794b2  call    ?IsUsingCapturePlugin@CMFSourceReaderStream@@AEAAHXZ; CMFSourceReaderStream::IsUsingCapturePlugin(void)
0x1800794b7  test    eax, eax
0x1800794b9  jnz     loc_180079E6A
0x1800794bf  mov     rbx, [r15+4F8h]
0x1800794c6  mov     rcx, [rbp+arg_18]
0x1800794ca  cmp     rcx, rbx
0x1800794cd  jz      short loc_180079541
0x1800794cf  test    rbx, rbx
0x1800794d2  jz      short loc_1800794E7
0x1800794d4  mov     rax, [rbx]
0x1800794d7  mov     rcx, rbx
0x1800794da  mov     rax, [rax+8]
0x1800794de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800794e3  mov     rcx, [rbp+arg_18]
0x1800794e7  test    rcx, rcx
0x1800794ea  jz      short loc_1800794F8
0x1800794ec  mov     rax, [rcx]
0x1800794ef  mov     rax, [rax+10h]
0x1800794f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800794f8  mov     [rbp+arg_18], rbx
0x1800794fc  jmp     short loc_180079541
0x1800794fe  lea     r8, [rbp+arg_0]; struct CMFSourceReaderStream::CSourceReaderStreamInfo **
0x180079502  mov     edx, ebx; unsigned int
0x180079504  call    ?LookupStreamInfo@CMFSourceReaderStream@@AEAAJKPEAPEAVCSourceReaderStreamInfo@1@@Z; CMFSourceReaderStream::LookupStreamInfo(ulong,CMFSourceReaderStream::CSourceReaderStreamInfo * *)
0x180079509  mov     edi, eax
0x18007950b  test    eax, eax
0x18007950d  js      loc_180079674
0x180079513  mov     rbx, [rbp+arg_0]
0x180079517  test    esi, esi
0x180079519  jz      loc_18007993E
0x18007951f  mov     rcx, [r15+660h]
0x180079526  lea     r8, [rbp+arg_18]
0x18007952a  mov     edx, [rbx+4]
0x18007952d  mov     rax, [rcx]
0x180079530  mov     rax, [rax+48h]
0x180079534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079539  test    eax, eax
0x18007953b  js      loc_180079AB0
0x180079541  lea     rcx, [rbp+ppMFType]; ppMFType
0x180079545  call    cs:__imp_MFCreateMediaType
0x18007954b  mov     edi, eax
0x18007954d  test    eax, eax
0x18007954f  js      loc_180079BF6
0x180079555  mov     rcx, [rbp+arg_18]
0x180079559  mov     rdx, [rbp+ppMFType]
0x18007955d  mov     rax, [rcx]
0x180079560  mov     rax, [rax+100h]
0x180079567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007956c  mov     edi, eax
0x18007956e  test    eax, eax
0x180079570  js      loc_180079D21
0x180079576  mov     rax, [rbp+ppMFType]
0x18007957a  mov     [r14], rax
0x18007957d  mov     [rbp+ppMFType], r13
0x180079581  mov     rcx, r12; lpCriticalSection
0x180079584  call    cs:__imp_LeaveCriticalSection
0x18007958a  mov     rcx, [rbp+ppMFType]
0x18007958e  test    rcx, rcx
0x180079591  jz      short loc_18007959F
0x180079593  mov     rax, [rcx]
0x180079596  mov     rax, [rax+10h]
0x18007959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007959f  mov     rcx, [rbp+arg_18]
0x1800795a3  test    rcx, rcx
0x1800795a6  jz      short loc_1800795B4
0x1800795a8  mov     rdx, [rcx]
0x1800795ab  mov     rax, [rdx+10h]
0x1800795af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795b4  lea     rcx, [rbp+arg_0]; this
0x1800795b8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800795bd  mov     rbx, [rsp+40h+arg_8]
0x1800795c5  mov     eax, edi
0x1800795c7  add     rsp, 40h
0x1800795cb  pop     r15
0x1800795cd  pop     r14
0x1800795cf  pop     r13
0x1800795d1  pop     r12
0x1800795d3  pop     rdi
0x1800795d4  pop     rsi
0x1800795d5  pop     rbp
0x1800795d6  retn
0x1800795d7  cmp     [r15+0B8h], r13d
0x1800795de  jz      loc_1800794A6
0x1800795e4  mov     rcx, [r15+650h]; this
0x1800795eb  lea     rdx, [rbp+arg_18]; struct IMFMediaType **
0x1800795ef  call    ?GetInternalMediaType@CSourceReaderStreamInfo@CMFSourceReaderStream@@QEAAXPEAPEAUIMFMediaType@@@Z; CMFSourceReaderStream::CSourceReaderStreamInfo::GetInternalMediaType(IMFMediaType * *)
0x1800795f4  cmp     [rbp+arg_18], r13
0x1800795f8  jnz     loc_180079541
0x1800795fe  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079605  lea     rbx, qword_18010C230
0x18007960c  mov     edi, 8000FFFFh
0x180079611  mov     r14d, 7F0h
0x180079617  test    rsi, rsi
0x18007961a  jnz     short loc_180079653
0x18007961c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079622  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079629  mov     rcx, rax
0x18007962c  test    rax, rax
0x18007962f  jz      loc_1800797B0
0x180079635  mov     rax, [rax]
0x180079638  mov     edx, r14d
0x18007963b  mov     rax, [rax+8]
0x18007963f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079644  test    eax, eax
0x180079646  jz      loc_1800797B0
0x18007964c  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079653  cmp     [rsi+8], r13b
0x180079657  jnz     loc_1800797BF
0x18007965d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079664  jb      loc_180079581
0x18007966a  mov     edx, 15Dh
0x18007966f  jmp     loc_180079D81
0x180079674  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007967b  test    rbx, rbx
0x18007967e  jz      short loc_1800796CF
0x180079680  cmp     [rbx+8], r13b
0x180079684  jnz     loc_180079879
0x18007968a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079691  jb      loc_180079581
0x180079697  mov     edx, 15Eh
0x18007969c  jmp     loc_180079D81
0x1800796a1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800796a8  mov     edi, 0C00D3E85h
0x1800796ad  test    rbx, rbx
0x1800796b0  jz      short loc_1800796DD
0x1800796b2  cmp     [rbx+8], r13b
0x1800796b6  jnz     short loc_1800796EB
0x1800796b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800796bf  jb      loc_180079581
0x1800796c5  mov     edx, 15Ch
0x1800796ca  jmp     loc_180079D81
0x1800796cf  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800796d4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800796db  jmp     short loc_180079680
0x1800796dd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800796e2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800796e9  jmp     short loc_1800796B2
0x1800796eb  lea     rsi, [rbx+0D0h]
0x1800796f2  call    cs:__imp_GetLastError
0x1800796f8  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800796fb  mov     r12d, eax
0x1800796fe  call    cs:__imp_TlsGetValue
0x180079704  test    rax, rax
0x180079707  jnz     short loc_180079759
0x180079709  call    cs:__imp_GetLastError
0x18007970f  test    eax, eax
0x180079711  jnz     short loc_18007975C
0x180079713  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007971a  test    rbx, rbx
0x18007971d  jnz     short loc_180079742
0x18007971f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079725  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007972c  mov     rcx, rax
0x18007972f  test    rax, rax
0x180079732  jnz     short loc_180079792
0x180079734  lea     rbx, qword_18010C230
0x18007973b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079742  mov     rax, [rbx]
0x180079745  mov     rcx, rbx
0x180079748  mov     rax, [rax]
0x18007974b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079750  test    rax, rax
0x180079753  cmovnz  rsi, rax
0x180079757  jmp     short loc_18007975C
0x180079759  mov     rsi, rax
0x18007975c  mov     ecx, r12d; dwErrCode
0x18007975f  call    cs:__imp_SetLastError
0x180079765  lea     r12, [r15+30h]
0x180079769  cmp     [rsi+7CCh], edi
0x18007976f  jz      loc_1800796B8
0x180079775  mov     r9d, edi; int
0x180079778  lea     rdx, aCmfsourcereade_176; "CMFSourceReaderStream::InternalGetCurre"...
0x18007977f  mov     r8d, 0EC7h; int
0x180079785  mov     rcx, rsi; this
0x180079788  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007978d  jmp     loc_1800796B8
0x180079792  mov     rax, [rax]
0x180079795  mov     edx, 7F0h
0x18007979a  mov     rax, [rax+8]
0x18007979e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797a3  test    eax, eax
0x1800797a5  jz      short loc_180079734
0x1800797a7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800797ae  jmp     short loc_180079742
0x1800797b0  mov     rsi, rbx
0x1800797b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800797ba  jmp     loc_180079653
0x1800797bf  lea     r12, [rsi+0D0h]
0x1800797c6  call    cs:__imp_GetLastError
0x1800797cc  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800797cf  mov     r13d, eax
0x1800797d2  call    cs:__imp_TlsGetValue
0x1800797d8  test    rax, rax
0x1800797db  jnz     short loc_180079826
0x1800797dd  call    cs:__imp_GetLastError
0x1800797e3  test    eax, eax
0x1800797e5  jnz     short loc_180079829
0x1800797e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800797ee  test    rcx, rcx
0x1800797f1  jnz     short loc_180079812
0x1800797f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800797f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079800  mov     rcx, rax
0x180079803  test    rax, rax
0x180079806  jnz     short loc_18007985D
0x180079808  mov     rcx, rbx
0x18007980b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079812  mov     rax, [rcx]
0x180079815  mov     rax, [rax]
0x180079818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007981d  test    rax, rax
0x180079820  cmovnz  r12, rax
0x180079824  jmp     short loc_180079829
0x180079826  mov     r12, rax
0x180079829  mov     ecx, r13d; dwErrCode
0x18007982c  call    cs:__imp_SetLastError
0x180079832  cmp     [r12+7CCh], edi
0x18007983a  jz      short loc_180079854
0x18007983c  mov     r9d, edi; int
0x18007983f  lea     rdx, aCmfsourcereade_176; "CMFSourceReaderStream::InternalGetCurre"...
0x180079846  mov     r8d, 0ED2h; int
0x18007984c  mov     rcx, r12; this
0x18007984f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079854  lea     r12, [r15+30h]
0x180079858  jmp     loc_18007965D
0x18007985d  mov     rax, [rax]
0x180079860  mov     edx, r14d
0x180079863  mov     rax, [rax+8]
0x180079867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007986c  test    eax, eax
0x18007986e  jz      short loc_180079808
0x180079870  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079877  jmp     short loc_180079812
0x180079879  lea     rsi, [rbx+0D0h]
0x180079880  call    cs:__imp_GetLastError
0x180079886  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180079889  mov     r12d, eax
0x18007988c  call    cs:__imp_TlsGetValue
0x180079892  test    rax, rax
0x180079895  jnz     short loc_1800798E7
0x180079897  call    cs:__imp_GetLastError
0x18007989d  test    eax, eax
0x18007989f  jnz     short loc_1800798EA
0x1800798a1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798a8  test    rbx, rbx
0x1800798ab  jnz     short loc_1800798D0
0x1800798ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800798b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798ba  mov     rcx, rax
0x1800798bd  test    rax, rax
0x1800798c0  jnz     short loc_180079920
0x1800798c2  lea     rbx, qword_18010C230
0x1800798c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798d0  mov     rax, [rbx]
0x1800798d3  mov     rcx, rbx
0x1800798d6  mov     rax, [rax]
0x1800798d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800798de  test    rax, rax
0x1800798e1  cmovnz  rsi, rax
0x1800798e5  jmp     short loc_1800798EA
0x1800798e7  mov     rsi, rax
0x1800798ea  mov     ecx, r12d; dwErrCode
0x1800798ed  call    cs:__imp_SetLastError
  ... truncated ...
```
