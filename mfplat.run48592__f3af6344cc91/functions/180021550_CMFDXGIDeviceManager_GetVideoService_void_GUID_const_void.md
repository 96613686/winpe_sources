# CMFDXGIDeviceManager::GetVideoService(void *,_GUID const &,void * *)

- ea: `0x180021550`
- end: `0x18002230a`
- name: `?GetVideoService@CMFDXGIDeviceManager@@UEAAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `3514`
- prototype: `__int64 __fastcall(CMFDXGIDeviceManager *__hidden this, void *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180024460`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180021550`
- `0x180022aa0`
- `0x180024390`
- `0x1800afc5c`
- `0x1800f4184`
- `0x18012fd9c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800215e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800217f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800217f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800215a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021655`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800216d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021820`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800215a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021655`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800216d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021744`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021886`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021744`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800215b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002166a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800216eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800215b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002166a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800216eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b3a`

## string_xrefs

- `0x180021589`: `CMFDXGIDeviceManager::GetVideoService`
- `0x180021a17`: `CMFDXGIDeviceManager::GetVideoService`
- `0x180021a69`: `CMFDXGIDeviceManager::GetVideoService`
- `0x180021fab`: `CMFDXGIDeviceManager::GetVideoService`
- `0x18002203f`: `CMFDXGIDeviceManager::GetVideoService`
- `0x1800220d2`: `CMFDXGIDeviceManager::GetVideoService`
- `0x180022165`: `CMFDXGIDeviceManager::GetVideoService`
- `0x1800221ef`: `CMFDXGIDeviceManager::GetVideoService`
- `0x18002221d`: `CMFDXGIDeviceManager::GetVideoService`

## pseudocode

```c
__int64 __fastcall CMFDXGIDeviceManager::GetVideoService(
        CMFDXGIDeviceManager *this,
        void *a2,
        const struct _GUID *a3,
        void **a4)
{
  CallStackTracing *v4; // rdi
  CallStackContext *p_m_context; // rbx
  DWORD LastError; // ebp
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v12; // rax
  int DX11DeviceFromDX12; // ebp
  void ***v14; // rax
  void **i; // rdi
  CallStackTracing *v16; // r14
  CallStackContext *v17; // rbp
  DWORD v18; // r15d
  CallStackContext *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  CallStackContext *v22; // rdi
  DWORD v23; // r15d
  CallStackContext *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  DWORD CurrentThreadId; // eax
  void ***v28; // rcx
  void **v29; // rdi
  int v30; // eax
  int v31; // ebp
  __int64 (__fastcall ***v32)(_QWORD, const struct _GUID *, void **); // rcx
  CallStackTracing *v33; // rdi
  CallStackContext *v34; // rbx
  DWORD v35; // esi
  CallStackContext *v36; // rax
  unsigned int v37; // eax
  unsigned int v38; // eax
  __int64 v40; // rdx
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rcx
  CallStackTracing *v48; // rcx
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v52; // rax
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 (__fastcall ***v61)(_QWORD, const struct _GUID *, void **); // rcx

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v4 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v4 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v4->m_fEnabled )
  {
    p_m_context = &v4->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v4->m_dwTLSIndex);
    if ( Value )
      goto LABEL_4;
    if ( !GetLastError() )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v46 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      Value = (CallStackContext *)v46->AllocateNewContext(v46);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v12 = m_dwDepth;
      p_m_context->m_rgInfo[v12].m_pszFunction = "CMFDXGIDeviceManager::GetVideoService";
      p_m_context->m_rgInfo[v12].m_lineNumber = 815;
    }
    ++p_m_context->m_dwDepth;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  DX11DeviceFromDX12 = CMFDXGIDeviceManager::InternalCheckDeviceInitialized(this);
  if ( DX11DeviceFromDX12 < 0 )
  {
    v50 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v50 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v50->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v50);
      if ( ThreadRelativeContext->m_result != DX11DeviceFromDX12 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFDXGIDeviceManager::GetVideoService",
          822,
          DX11DeviceFromDX12);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v40 = 57;
      goto LABEL_57;
    }
    goto LABEL_41;
  }
  v14 = (void ***)*((_QWORD *)this + 65);
  for ( i = 0; v14; i = 0 )
  {
    i = *v14;
    if ( **v14 == a2 )
      break;
    v14 = (void ***)v14[1];
  }
  v16 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v16 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v16->m_fEnabled )
  {
    v17 = &v16->m_context;
    v18 = GetLastError();
    v19 = (CallStackContext *)TlsGetValue(v16->m_dwTLSIndex);
    if ( v19 )
      goto LABEL_15;
    if ( !GetLastError() )
    {
      v47 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v47 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v19 = (CallStackContext *)v47->AllocateNewContext(v47);
      if ( v19 )
LABEL_15:
        v17 = v19;
    }
    SetLastError(v18);
    v20 = v17->m_dwDepth;
    v16 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v20 < v17->m_dwMaxDepth )
    {
      v21 = v20;
      v17->m_rgInfo[v21].m_pszFunction = "CMFDXGIDeviceManager::InternalTestDevice";
      v17->m_rgInfo[v21].m_lineNumber = 537;
    }
    ++v17->m_dwDepth;
  }
  if ( i )
  {
    if ( *((_DWORD *)i + 2) )
    {
      DX11DeviceFromDX12 = 0;
      goto LABEL_22;
    }
    DX11DeviceFromDX12 = -2147217407;
    if ( !v16 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v52 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v52->m_result != -2147217407 )
        CallStackContext::TraceFailure(v52, "CMFDXGIDeviceManager::InternalTestDevice", 542, -2147217407);
      v16 = CallStackTracing::s_wpInstance;
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v42 = 42;
      goto LABEL_141;
    }
  }
  else
  {
    DX11DeviceFromDX12 = -2147024890;
    if ( !v16 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v41 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v41->m_result != -2147024890 )
        CallStackContext::TraceFailure(v41, "CMFDXGIDeviceManager::InternalTestDevice", 537, -2147024890);
      v16 = CallStackTracing::s_wpInstance;
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v42 = 41;
LABEL_141:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v42,
        &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids,
        this,
        DX11DeviceFromDX12);
      v16 = CallStackTracing::s_wpInstance;
    }
  }
LABEL_22:
  if ( v16->m_fEnabled )
  {
    v22 = &v16->m_context;
    v23 = GetLastError();
    v24 = (CallStackContext *)TlsGetValue(v16->m_dwTLSIndex);
    if ( v24 )
      goto LABEL_24;
    if ( !GetLastError() )
    {
      v48 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v48 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v48 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v24 = (CallStackContext *)v48->AllocateNewContext(v48);
      if ( v24 )
LABEL_24:
        v22 = v24;
    }
    SetLastError(v23);
    v25 = v22->m_dwDepth;
    v16 = CallStackTracing::s_wpInstance;
    if ( v25 )
    {
      v26 = v25 - 1;
      v22->m_dwDepth = v26;
      if ( !v26 )
      {
        v22->m_dwDepth = 0;
        *(_QWORD *)&v22->m_instanceId = 0;
        v22->m_result = 0;
        v22->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v22->m_dwErrorsInContext = 0;
        CurrentThreadId = GetCurrentThreadId();
        v16 = CallStackTracing::s_wpInstance;
        v22->m_dwThreadID = CurrentThreadId;
      }
    }
  }
  if ( DX11DeviceFromDX12 < 0 )
  {
    if ( !v16 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v43->m_result != DX11DeviceFromDX12 )
        CallStackContext::TraceFailure(v43, "CMFDXGIDeviceManager::GetVideoService", 823, DX11DeviceFromDX12);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_41;
    v40 = 58;
LABEL_57:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v40,
      &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids,
      this,
      DX11DeviceFromDX12);
    goto LABEL_41;
  }
  v28 = (void ***)*((_QWORD *)this + 65);
  if ( !v28 )
  {
LABEL_53:
    DX11DeviceFromDX12 = -2147024890;
    if ( !v16 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v60 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v60->m_result != -2147024890 )
        CallStackContext::TraceFailure(v60, "CMFDXGIDeviceManager::GetVideoService", 826, -2147024890);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_41;
    v40 = 59;
    goto LABEL_57;
  }
  while ( 1 )
  {
    v29 = *v28;
    if ( **v28 == a2 )
      break;
    v28 = (void ***)v28[1];
    if ( !v28 )
      goto LABEL_53;
  }
  v30 = *((_DWORD *)v29 + 4);
  v31 = *((_DWORD *)this + 157);
  if ( v30 )
  {
    if ( v30 != v31 )
    {
      DX11DeviceFromDX12 = -2147024809;
      if ( !v16 )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        v53 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( v53->m_result != -2147024809 )
          CallStackContext::TraceFailure(v53, "CMFDXGIDeviceManager::GetVideoService", 857, -2147024809);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v40 = 62;
        goto LABEL_57;
      }
      goto LABEL_41;
    }
  }
  else
  {
    if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
    {
      WPP_SF_qqd(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        63,
        &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids,
        this,
        a2,
        *((_DWORD *)this + 157));
      v16 = CallStackTracing::s_wpInstance;
    }
    *((_DWORD *)v29 + 4) = v31;
  }
  if ( v31 != 1 )
  {
    if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
    {
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        68,
        &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids,
        this,
        a3->Data1,
        *((_DWORD *)this + 157));
      v16 = CallStackTracing::s_wpInstance;
    }
    v61 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 11);
    if ( v61 )
    {
      DX11DeviceFromDX12 = (**v61)(v61, a3, a4);
      if ( DX11DeviceFromDX12 < 0 )
      {
        v58 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v58 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v58->m_fEnabled )
        {
          v59 = CallStackTracing::GetThreadRelativeContext(v58);
          if ( v59->m_result != DX11DeviceFromDX12 )
            CallStackContext::TraceFailure(v59, "CMFDXGIDeviceManager::GetVideoService", 896, DX11DeviceFromDX12);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v40 = 70;
          goto LABEL_57;
        }
      }
    }
    else
    {
      DX11DeviceFromDX12 = -1072875845;
      if ( !v16 )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        v57 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( v57->m_result != -1072875845 )
          CallStackContext::TraceFailure(v57, "CMFDXGIDeviceManager::GetVideoService", 894, -1072875845);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v40 = 69;
        goto LABEL_57;
      }
    }
    goto LABEL_41;
  }
  if ( !*((_QWORD *)this + 10) )
  {
    DX11DeviceFromDX12 = CMFDXGIDeviceManager::GenerateDX11DeviceFromDX12(this);
    if ( DX11DeviceFromDX12 < 0 )
    {
      v54 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v54 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v54->m_fEnabled )
      {
        v55 = CallStackTracing::GetThreadRelativeContext(v54);
        if ( v55->m_result != DX11DeviceFromDX12 )
          CallStackContext::TraceFailure(v55, "CMFDXGIDeviceManager::GetVideoService", 876, DX11DeviceFromDX12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v40 = 64;
        goto LABEL_57;
      }
      goto LABEL_41;
    }
    v16 = CallStackTracing::s_wpInstance;
  }
  if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
  {
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      65,
      &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids,
      this,
      a3->Data1,
      *((_DWORD *)this + 157));
    v16 = CallStackTracing::s_wpInstance;
  }
  v32 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 10);
  if ( v32 )
  {
    DX11DeviceFromDX12 = (**v32)(v32, a3, a4);
    if ( DX11DeviceFromDX12 < 0 )
    {
      v44 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v44 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v44->m_fEnabled )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(v44);
        if ( v45->m_result != DX11DeviceFromDX12 )
          CallStackContext::TraceFailure(v45, "CMFDXGIDeviceManager::GetVideoService", 888, DX11DeviceFromDX12);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v40 = 67;
        goto LABEL_57;
      }
    }
  }
  else
  {
    DX11DeviceFromDX12 = -1072875845;
    if ( !v16 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v56 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v56->m_result != -1072875845 )
        CallStackContext::TraceFailure(v56, "CMFDXGIDeviceManager::GetVideoService", 886, -1072875845);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v40 = 66;
      goto LABEL_57;
    }
  }
LABEL_41:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v33 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v34 = &CallStackTracing::s_wpInstance->m_context;
    v35 = GetLastError();
    v36 = (CallStackContext *)TlsGetValue(v33->m_dwTLSIndex);
    if ( v36 )
      goto LABEL_43;
    if ( !GetLastError() )
    {
      v49 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v49 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v36 = (CallStackContext *)v49->AllocateNewContext(v49);
      if ( v36 )
LABEL_43:
        v34 = v36;
    }
    SetLastError(v35);
    v37 = v34->m_dwDepth;
    if ( v37 )
    {
      v38 = v37 - 1;
      v34->m_dwDepth = v38;
      if ( !v38 )
      {
        v34->m_dwDepth = 0;
        *(_QWORD *)&v34->m_instanceId = 0;
        v34->m_result = 0;
        v34->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v34->m_dwErrorsInContext = 0;
        v34->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)DX11DeviceFromDX12;
}

```

## disassembly

```asm
0x180021550  mov     [rsp+arg_18], r9
0x180021555  push    rbx
0x180021556  push    rbp
0x180021557  push    rsi
0x180021558  push    rdi
0x180021559  push    r12
0x18002155b  push    r13
0x18002155d  push    r14
0x18002155f  push    r15
0x180021561  sub     rsp, 38h
0x180021565  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002156c  lea     r15, stru_1801FC290
0x180021573  mov     r12, r8
0x180021576  mov     rsi, rdx
0x180021579  mov     r13, rcx
0x18002157c  test    rdi, rdi
0x18002157f  jz      loc_1800218A5
0x180021585  cmp     byte ptr [rdi+8], 0
0x180021589  lea     r14, aCmfdxgidevicem_25; "CMFDXGIDeviceManager::GetVideoService"
0x180021590  jz      short loc_1800215E1
0x180021592  lea     rbx, [rdi+0D0h]
0x180021599  call    cs:__imp_GetLastError
0x18002159f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800215a2  mov     ebp, eax
0x1800215a4  call    cs:__imp_TlsGetValue
0x1800215aa  test    rax, rax
0x1800215ad  jz      loc_180021A95
0x1800215b3  mov     rbx, rax
0x1800215b6  mov     ecx, ebp; dwErrCode
0x1800215b8  call    cs:__imp_SetLastError
0x1800215be  mov     eax, [rbx+7C4h]
0x1800215c4  cmp     eax, [rbx+7C8h]
0x1800215ca  jnb     short loc_1800215DB
0x1800215cc  add     rax, rax
0x1800215cf  mov     [rbx+rax*8], r14
0x1800215d3  mov     dword ptr [rbx+rax*8+8], 32Fh
0x1800215db  inc     dword ptr [rbx+7C4h]
0x1800215e1  lea     rcx, [r13+20h]; lpCriticalSection
0x1800215e5  call    cs:__imp_EnterCriticalSection
0x1800215eb  mov     rcx, r13; this
0x1800215ee  call    ?InternalCheckDeviceInitialized@CMFDXGIDeviceManager@@IEAAJXZ; CMFDXGIDeviceManager::InternalCheckDeviceInitialized(void)
0x1800215f3  mov     ebp, eax
0x1800215f5  test    eax, eax
0x1800215f7  js      loc_180021E4A
0x1800215fd  mov     rax, [r13+208h]
0x180021604  xor     edi, edi
0x180021606  test    rax, rax
0x180021609  jz      short loc_180021623
0x18002160b  nop     dword ptr [rax+rax+00h]
0x180021610  mov     rdi, [rax]
0x180021613  cmp     [rdi], rsi
0x180021616  jz      short loc_180021623
0x180021618  mov     rax, [rax+8]
0x18002161c  xor     edi, edi
0x18002161e  test    rax, rax
0x180021621  jnz     short loc_180021610
0x180021623  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002162a  test    r14, r14
0x18002162d  jz      loc_1800218D8
0x180021633  cmp     byte ptr [r14+8], 0
0x180021638  lea     r15, aCmfdxgidevicem_14; "CMFDXGIDeviceManager::InternalTestDevic"...
0x18002163f  jz      short loc_1800216A2
0x180021641  lea     rbp, [r14+0D0h]
0x180021648  call    cs:__imp_GetLastError
0x18002164e  mov     ecx, [r14+0Ch]; dwTlsIndex
0x180021652  mov     r15d, eax
0x180021655  call    cs:__imp_TlsGetValue
0x18002165b  test    rax, rax
0x18002165e  jz      loc_180021ACC
0x180021664  mov     rbp, rax
0x180021667  mov     ecx, r15d; dwErrCode
0x18002166a  call    cs:__imp_SetLastError
0x180021670  mov     eax, [rbp+7C4h]
0x180021676  lea     r15, aCmfdxgidevicem_14; "CMFDXGIDeviceManager::InternalTestDevic"...
0x18002167d  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021684  cmp     eax, [rbp+7C8h]
0x18002168a  jnb     short loc_18002169C
0x18002168c  add     rax, rax
0x18002168f  mov     [rbp+rax*8+0], r15
0x180021694  mov     dword ptr [rbp+rax*8+8], 219h
0x18002169c  inc     dword ptr [rbp+7C4h]
0x1800216a2  test    rdi, rdi
0x1800216a5  jz      loc_180021970
0x1800216ab  cmp     dword ptr [rdi+8], 0
0x1800216af  jz      loc_180021ED0
0x1800216b5  xor     ebp, ebp
0x1800216b7  cmp     byte ptr [r14+8], 0
0x1800216bc  jz      loc_180021757
0x1800216c2  lea     rdi, [r14+0D0h]
0x1800216c9  call    cs:__imp_GetLastError
0x1800216cf  mov     ecx, [r14+0Ch]; dwTlsIndex
0x1800216d3  mov     r15d, eax
0x1800216d6  call    cs:__imp_TlsGetValue
0x1800216dc  test    rax, rax
0x1800216df  jz      loc_180021B03
0x1800216e5  mov     rdi, rax
0x1800216e8  mov     ecx, r15d; dwErrCode
0x1800216eb  call    cs:__imp_SetLastError
0x1800216f1  mov     eax, [rdi+7C4h]
0x1800216f7  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800216fe  test    eax, eax
0x180021700  jz      short loc_180021757
0x180021702  sub     eax, 1
0x180021705  mov     [rdi+7C4h], eax
0x18002170b  jnz     short loc_180021757
0x18002170d  mov     dword ptr [rdi+7C4h], 0
0x180021717  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002171e  mov     qword ptr [rdi+7E0h], 0
0x180021729  mov     dword ptr [rdi+7CCh], 0
0x180021733  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002173a  mov     dword ptr [rdi+7E8h], 0
0x180021744  call    cs:__imp_GetCurrentThreadId
0x18002174a  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021751  mov     [rdi+7C0h], eax
0x180021757  test    ebp, ebp
0x180021759  js      loc_1800219ED
0x18002175f  mov     rcx, [r13+208h]
0x180021766  test    rcx, rcx
0x180021769  jz      loc_18002191B
0x18002176f  nop
0x180021770  mov     rdi, [rcx]
0x180021773  cmp     [rdi], rsi
0x180021776  jnz     loc_18002190B
0x18002177c  mov     eax, [rdi+10h]
0x18002177f  mov     ebp, [r13+274h]
0x180021786  test    eax, eax
0x180021788  jnz     loc_180021DDA
0x18002178e  cmp     cs:byte_1801FD28B, 20h ; ' '
0x180021795  jnb     loc_180022237
0x18002179b  mov     [rdi+10h], ebp
0x18002179e  cmp     ebp, 1
0x1800217a1  jnz     loc_18002228C
0x1800217a7  cmp     qword ptr [r13+50h], 0
0x1800217ac  jz      loc_18002226E
0x1800217b2  cmp     cs:byte_1801FD28B, 20h ; ' '
0x1800217b9  jnb     loc_180021C19
0x1800217bf  mov     rcx, [r13+50h]
0x1800217c3  test    rcx, rcx
0x1800217c6  jz      loc_180022056
0x1800217cc  mov     rax, [rcx]
0x1800217cf  mov     rdx, r12
0x1800217d2  mov     r8, [rsp+78h+arg_18]
0x1800217da  mov     rax, [rax]
0x1800217dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217e2  lea     r15, stru_1801FC290
0x1800217e9  mov     ebp, eax
0x1800217eb  test    eax, eax
0x1800217ed  js      loc_180021A43
0x1800217f3  lea     rcx, [r13+20h]; lpCriticalSection
0x1800217f7  call    cs:__imp_LeaveCriticalSection
0x1800217fd  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021804  cmp     byte ptr [rdi+8], 0
0x180021808  jz      loc_180021892
0x18002180e  lea     rbx, [rdi+0D0h]
0x180021815  call    cs:__imp_GetLastError
0x18002181b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002181e  mov     esi, eax
0x180021820  call    cs:__imp_TlsGetValue
0x180021826  test    rax, rax
0x180021829  jz      loc_180021B3A
0x18002182f  mov     rbx, rax
0x180021832  mov     ecx, esi; dwErrCode
0x180021834  call    cs:__imp_SetLastError
0x18002183a  mov     eax, [rbx+7C4h]
0x180021840  test    eax, eax
0x180021842  jz      short loc_180021892
0x180021844  sub     eax, 1
0x180021847  mov     [rbx+7C4h], eax
0x18002184d  jnz     short loc_180021892
0x18002184f  mov     dword ptr [rbx+7C4h], 0
0x180021859  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180021860  mov     qword ptr [rbx+7E0h], 0
0x18002186b  mov     dword ptr [rbx+7CCh], 0
0x180021875  movups  xmmword ptr [rbx+7D0h], xmm0
0x18002187c  mov     dword ptr [rbx+7E8h], 0
0x180021886  call    cs:__imp_GetCurrentThreadId
0x18002188c  mov     [rbx+7C0h], eax
0x180021892  mov     eax, ebp
0x180021894  add     rsp, 38h
0x180021898  pop     r15
0x18002189a  pop     r14
0x18002189c  pop     r13
0x18002189e  pop     r12
0x1800218a0  pop     rdi
0x1800218a1  pop     rsi
0x1800218a2  pop     rbp
0x1800218a3  pop     rbx
0x1800218a4  retn
0x1800218a5  mov     rax, cs:stru_1801FC290.__vftable
0x1800218ac  mov     edx, 7F0h
0x1800218b1  mov     rcx, r15
0x1800218b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800218bb  mov     rax, [rax+8]
0x1800218bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218c4  test    eax, eax
0x1800218c6  jz      loc_1800219C7
0x1800218cc  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800218d3  jmp     loc_180021585
0x1800218d8  mov     rax, cs:stru_1801FC290.__vftable
0x1800218df  mov     edx, 7F0h
0x1800218e4  mov     rcx, r15
0x1800218e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800218ee  mov     rax, [rax+8]
0x1800218f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218f7  test    eax, eax
0x1800218f9  jz      loc_1800219DA
0x1800218ff  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021906  jmp     loc_180021633
0x18002190b  mov     rax, [rcx+8]
0x18002190f  mov     rcx, rax
0x180021912  test    rax, rax
0x180021915  jnz     loc_180021770
0x18002191b  lea     r15, stru_1801FC290
0x180021922  mov     ebp, 80070006h
0x180021927  test    r14, r14
0x18002192a  jz      loc_180021B71
0x180021930  cmp     byte ptr [r14+8], 0
0x180021935  jnz     loc_180022206
0x18002193b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021942  jb      loc_1800217F3
0x180021948  mov     edx, 3Bh ; ';'
0x18002194d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021954  lea     r8, WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids
0x18002195b  mov     r9, r13
0x18002195e  mov     dword ptr [rsp+78h+var_58], ebp
0x180021962  mov     rcx, [rcx+10h]
0x180021966  call    WPP_SF_qD
0x18002196b  jmp     loc_1800217F3
0x180021970  mov     ebp, 80070006h
0x180021975  test    r14, r14
0x180021978  jz      loc_180021BA0
0x18002197e  cmp     byte ptr [r14+8], 0
0x180021983  jz      short loc_1800219B0
0x180021985  mov     rcx, r14; this
0x180021988  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002198d  cmp     [rax+7CCh], ebp
0x180021993  jz      short loc_1800219A9
0x180021995  mov     r9d, ebp; int
0x180021998  mov     r8d, 219h; int
0x18002199e  mov     rdx, r15; char *
0x1800219a1  mov     rcx, rax; this
0x1800219a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800219a9  mov     r14, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800219b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800219b7  jb      loc_1800216B7
0x1800219bd  mov     edx, 29h ; ')'
0x1800219c2  jmp     loc_180021F28
0x1800219c7  lea     rdi, stru_1801F8A30
0x1800219ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800219d5  jmp     loc_180021585
0x1800219da  lea     r14, stru_1801F8A30
0x1800219e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x1800219e8  jmp     loc_180021633
0x1800219ed  lea     r15, stru_1801FC290
0x1800219f4  test    r14, r14
0x1800219f7  jz      loc_180021BEA
0x1800219fd  cmp     byte ptr [r14+8], 0
0x180021a02  jz      short loc_180021A2C
0x180021a04  mov     rcx, r14; this
0x180021a07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021a0c  cmp     [rax+7CCh], ebp
0x180021a12  jz      short loc_180021A2C
0x180021a14  mov     r9d, ebp; int
0x180021a17  lea     rdx, aCmfdxgidevicem_25; "CMFDXGIDeviceManager::GetVideoService"
0x180021a1e  mov     r8d, 337h; int
0x180021a24  mov     rcx, rax; this
0x180021a27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021a2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021a33  jb      loc_1800217F3
0x180021a39  mov     edx, 3Ah ; ':'
0x180021a3e  jmp     loc_18002194D
0x180021a43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180021a4a  test    rcx, rcx
0x180021a4d  jz      loc_180021C80
0x180021a53  cmp     byte ptr [rcx+8], 0
0x180021a57  jz      short loc_180021A7E
0x180021a59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021a5e  cmp     [rax+7CCh], ebp
0x180021a64  jz      short loc_180021A7E
0x180021a66  mov     r9d, ebp; int
0x180021a69  lea     rdx, aCmfdxgidevicem_25; "CMFDXGIDeviceManager::GetVideoService"
0x180021a70  mov     r8d, 378h; int
0x180021a76  mov     rcx, rax; this
0x180021a79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021a7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021a85  jb      loc_1800217F3
0x180021a8b  mov     edx, 43h ; 'C'
0x180021a90  jmp     loc_18002194D
0x180021a95  call    cs:__imp_GetLastError
0x180021a9b  test    eax, eax
0x180021a9d  jnz     loc_1800215B6
0x180021aa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021aaa  test    rcx, rcx
0x180021aad  jz      loc_180021CC2
0x180021ab3  mov     rax, [rcx]
0x180021ab6  mov     rax, [rax]
0x180021ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021abe  test    rax, rax
0x180021ac1  jnz     loc_1800215B3
0x180021ac7  jmp     loc_1800215B6
  ... truncated ...
```
