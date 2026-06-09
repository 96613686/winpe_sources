# CMFDX11Allocator::OnInvokeDelete(IMFAsyncResult *)

- ea: `0x180052b20`
- end: `0x1800536a4`
- name: `?OnInvokeDelete@CMFDX11Allocator@@UEAAJPEAUIMFAsyncResult@@@Z`
- size: `2948`
- prototype: `__int64 __fastcall(CMFDX11Allocator *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180052b00`

## callees

- `0x180006c78`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x18004f050`
- `0x180052b20`
- `0x1800536ac`
- `0x1801200d0`
- `0x1801250c8`
- `0x180125108`
- `0x1801a8e38`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052c24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052c24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052ef6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053017`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053017`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052b82`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052f70`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052b82`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180052f70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052f85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800530e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053652`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180053652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053644`

## string_xrefs

- `0x180052b66`: `CMFDX11Allocator::OnInvokeDelete`

## pseudocode

```c
__int64 __fastcall CMFDX11Allocator::OnInvokeDelete(struct _RTL_CRITICAL_SECTION *this, struct IMFAsyncResult *a2)
{
  CallStackTracing *v2; // rsi
  CallStackContext *p_m_context; // rbx
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v9; // rax
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  int v12; // esi
  unsigned __int8 CTRLGUID_MF_PLATFORM; // dl
  _RTL_CRITICAL_SECTION_DEBUG *i; // rcx
  _RTL_CRITICAL_SECTION_DEBUG *CriticalSection; // r9
  _LIST_ENTRY *Flink; // r8
  int v17; // esi
  _RTL_CRITICAL_SECTION_DEBUG *v18; // rdx
  _RTL_CRITICAL_SECTION_DEBUG *j; // rcx
  unsigned __int64 v20; // r8
  struct IMFSample *v21; // r15
  _QWORD *p_Type; // rcx
  unsigned __int64 SpinCount; // rax
  unsigned __int64 v24; // rcx
  IMFAsyncResult_vtbl *v25; // rcx
  IMFAsyncResult_vtbl *v26; // rcx
  __int64 v27; // rcx
  _RTL_CRITICAL_SECTION_DEBUG *v28; // rcx
  CallStackTracing *v29; // rdi
  CallStackContext *v30; // rbx
  DWORD v31; // r14d
  CallStackContext *v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // eax
  void *v36; // rcx
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rcx
  CallStackTracing *v39; // rcx
  __int64 v40; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  CallStackTracing *v50; // rcx
  struct CallStackContext *v51; // rax
  int v52; // eax
  SIZE_T v53; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v55; // r9
  unsigned int k; // r8d
  __int64 v57; // rax
  struct IMFSample *v58; // [rsp+30h] [rbp-40h] BYREF
  _RTL_CRITICAL_SECTION_DEBUG *v59; // [rsp+38h] [rbp-38h] BYREF
  __int64 v60; // [rsp+40h] [rbp-30h] BYREF
  __int64 v61; // [rsp+48h] [rbp-28h] BYREF
  __int128 v62; // [rsp+50h] [rbp-20h] BYREF

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v2 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v2->m_fEnabled )
  {
    p_m_context = &v2->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v2->m_dwTLSIndex);
    if ( Value )
      goto LABEL_4;
    if ( !GetLastError() )
    {
      v37 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      Value = (CallStackContext *)v37->AllocateNewContext(v37);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v9 = m_dwDepth;
      p_m_context->m_rgInfo[v9].m_pszFunction = "CMFDX11Allocator::OnInvokeDelete";
      p_m_context->m_rgInfo[v9].m_lineNumber = 1437;
    }
    ++p_m_context->m_dwDepth;
  }
  v10 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))&this[36].LockCount;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  if ( v10 )
  {
    v12 = 0;
    if ( (**v10)(v10, &GUID_189819f1_1db6_4b57_be54_1821339b85f7, &v61) >= 0 )
    {
      if ( a2
        && a2->GetState(a2, (IUnknown **)&v59) >= 0
        && (**(int (__fastcall ***)(_RTL_CRITICAL_SECTION_DEBUG *, GUID *, struct IMFSample **))&v59->Type)(
             v59,
             &GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4,
             &v58) >= 0 )
      {
        v52 = WaitForD3D12BufferRelease(v58);
        v12 = v52;
        if ( v52 < 0 && g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            97,
            &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids,
            this,
            v52);
      }
      else if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids, this);
      }
      ComSmartPtr<IUnknown>::operator=(&v59);
      ComSmartPtr<IPropertyStore>::operator=(&v58, 0);
    }
    v11 = this + 1;
    EnterCriticalSection(this + 1);
    if ( v12 < 0 )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v39->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v39);
        if ( ThreadRelativeContext->m_result != v12 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFDX11Allocator::OnInvokeDelete", 1475, v12);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_55;
      v40 = 99;
LABEL_147:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids, this, v12);
      goto LABEL_55;
    }
  }
  else
  {
    v11 = this + 1;
    EnterCriticalSection(this + 1);
  }
  if ( !a2 )
  {
    v42 = CallStackTracing::s_wpInstance;
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v42 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v42 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v42->m_fEnabled )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( v43->m_result != -2147467261 )
        CallStackContext::TraceFailure(v43, "CMFDX11Allocator::OnInvokeDelete", 1476, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_55;
    v40 = 100;
    goto LABEL_147;
  }
  v12 = a2->GetState(a2, (IUnknown **)&v59);
  if ( v12 < 0 )
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
      if ( v45->m_result != v12 )
        CallStackContext::TraceFailure(v45, "CMFDX11Allocator::OnInvokeDelete", 1477, v12);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_55;
    v40 = 101;
    goto LABEL_147;
  }
  v12 = (**(__int64 (__fastcall ***)(_RTL_CRITICAL_SECTION_DEBUG *, GUID *, struct IMFSample **))&v59->Type)(
          v59,
          &GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4,
          &v58);
  if ( v12 < 0 )
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
    if ( v46->m_fEnabled )
    {
      v47 = CallStackTracing::GetThreadRelativeContext(v46);
      if ( v47->m_result != v12 )
        CallStackContext::TraceFailure(v47, "CMFDX11Allocator::OnInvokeDelete", 1482, v12);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_55;
    v40 = 103;
    goto LABEL_147;
  }
  CTRLGUID_MF_PLATFORM = g_wppLevels.CTRLGUID_MF_PLATFORM;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 8u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids, this, v58);
    CTRLGUID_MF_PLATFORM = g_wppLevels.CTRLGUID_MF_PLATFORM;
  }
  for ( i = this[35].DebugInfo; i; i = (_RTL_CRITICAL_SECTION_DEBUG *)i->CriticalSection )
  {
    CriticalSection = (_RTL_CRITICAL_SECTION_DEBUG *)i->CriticalSection;
    if ( *(_RTL_CRITICAL_SECTION_DEBUG **)&i->Type == v59 )
    {
      if ( i == this[35].DebugInfo )
        this[35].DebugInfo = CriticalSection;
      else
        i->ProcessLocksList.Flink->Blink = (_LIST_ENTRY *)CriticalSection;
      Flink = i->ProcessLocksList.Flink;
      if ( i == *(_RTL_CRITICAL_SECTION_DEBUG **)&this[35].LockCount )
        *(_QWORD *)&this[35].LockCount = Flink;
      else
        i->CriticalSection->OwningThread = Flink;
      i->CriticalSection = (_RTL_CRITICAL_SECTION *)this[24].OwningThread;
      this[24].OwningThread = i;
      --LODWORD(this[35].OwningThread);
      if ( CTRLGUID_MF_PLATFORM >= 8u )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids, this, v58);
      v12 = 0;
      goto LABEL_55;
    }
  }
  if ( CTRLGUID_MF_PLATFORM >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids, this, v58);
  v12 = v58->QueryInterface(v58, &GUID_6dc5a5a6_e640_4328_9c05_41a2c952d409, (void **)&v60);
  if ( v12 < 0 )
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
    if ( v48->m_fEnabled )
    {
      v49 = CallStackTracing::GetThreadRelativeContext(v48);
      if ( v49->m_result != v12 )
        CallStackContext::TraceFailure(v49, "CMFDX11Allocator::OnInvokeDelete", 1502, v12);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v40 = 108;
      goto LABEL_147;
    }
  }
  else
  {
    v17 = v58->GetGUID(v58, &MFSampleExtension_MDLCacheCookie, (_GUID *)&v62);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 32LL))(v60);
    if ( v17 >= 0 )
      v58->SetGUID(v58, &MFSampleExtension_MDLCacheCookie, (const _GUID *)&v62);
    v18 = v59;
    for ( j = (_RTL_CRITICAL_SECTION_DEBUG *)this[23].SpinCount; j; j = (_RTL_CRITICAL_SECTION_DEBUG *)j->CriticalSection )
    {
      v20 = (unsigned __int64)j->CriticalSection;
      if ( *(_RTL_CRITICAL_SECTION_DEBUG **)&j->Type == v59 )
      {
        if ( j == (_RTL_CRITICAL_SECTION_DEBUG *)this[23].SpinCount )
          this[23].SpinCount = v20;
        else
          j->ProcessLocksList.Flink->Blink = (_LIST_ENTRY *)v20;
        v18 = (_RTL_CRITICAL_SECTION_DEBUG *)j->ProcessLocksList.Flink;
        if ( j == this[24].DebugInfo )
          this[24].DebugInfo = v18;
        else
          j->CriticalSection->OwningThread = v18;
        j->CriticalSection = *(_RTL_CRITICAL_SECTION **)&this[13].LockCount;
        *(_QWORD *)&this[13].LockCount = j;
        --this[24].LockCount;
        break;
      }
    }
    v21 = v58;
    if ( this[2].DebugInfo )
      goto LABEL_41;
    v53 = 24LL * (unsigned int)(LODWORD(this[2].OwningThread) - 1) + 32;
    ProcessHeap = GetProcessHeap();
    v55 = HeapAlloc(ProcessHeap, 0, v53);
    if ( v55 )
    {
      for ( k = 0; k < LODWORD(this[2].OwningThread); this[2].DebugInfo = v18 )
      {
        v57 = k++;
        v18 = (_RTL_CRITICAL_SECTION_DEBUG *)&v55[2 * v57 + 1 + v57];
        v18->CriticalSection = (_RTL_CRITICAL_SECTION *)this[2].DebugInfo;
      }
      *v55 = *(_QWORD *)&this[2].LockCount;
      *(_QWORD *)&this[2].LockCount = v55;
LABEL_41:
      p_Type = &this[2].DebugInfo->Type;
      v12 = 0;
      this[2].DebugInfo = (_RTL_CRITICAL_SECTION_DEBUG *)p_Type[1];
      *p_Type = v21;
      p_Type[1] = 0;
      p_Type[2] = this[12].SpinCount;
      SpinCount = this[12].SpinCount;
      if ( SpinCount )
        *(_QWORD *)(SpinCount + 8) = p_Type;
      else
        this[12].LockSemaphore = p_Type;
      ++LODWORD(this[13].DebugInfo);
      this[12].SpinCount = (unsigned __int64)p_Type;
      ++HIDWORD(this[35].SpinCount);
      if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
        McTemplateU0ppdd_EventWriteTransfer(
          HIDWORD(this[35].SpinCount),
          (unsigned int)Mem2DAlloc_Buffer_End,
          (_DWORD)v58,
          (_DWORD)this,
          HIDWORD(this[35].SpinCount),
          (char)this[35].LockSemaphore);
      v24 = this[39].SpinCount;
      v58 = 0;
      if ( v24 )
      {
        (*(void (__fastcall **)(unsigned __int64, _RTL_CRITICAL_SECTION_DEBUG *))(*(_QWORD *)v24 + 24LL))(v24, v18);
      }
      else if ( LODWORD(this[38].DebugInfo) )
      {
        v36 = (void *)this[36].SpinCount;
        LODWORD(this[38].DebugInfo) = 0;
        SetEvent(v36);
      }
      v25 = a2[10].__vftable;
      if ( v25 )
        (*((void (__fastcall **)(IMFAsyncResult_vtbl *))v25->QueryInterface + 2))(v25);
      v26 = a2[11].__vftable;
      a2[10].__vftable = 0;
      if ( v26 )
        (*((void (__fastcall **)(IMFAsyncResult_vtbl *))v26->QueryInterface + 2))(v26);
      v27 = v60;
      a2[11].__vftable = 0;
      if ( v27 )
      {
        v60 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(_RTL_CRITICAL_SECTION_DEBUG *))(*(_QWORD *)&v28->Type + 16LL))(v28);
      }
      goto LABEL_55;
    }
    v50 = CallStackTracing::s_wpInstance;
    v12 = -2147024882;
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
      v51 = CallStackTracing::GetThreadRelativeContext(v50);
      if ( v51->m_result != -2147024882 )
        CallStackContext::TraceFailure(v51, "CMFDX11Allocator::OnInvokeDelete", 1530, -2147024882);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v40 = 111;
      goto LABEL_147;
    }
  }
LABEL_55:
  LeaveCriticalSection(v11);
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v59 )
    (*(void (__fastcall **)(_RTL_CRITICAL_SECTION_DEBUG *))(*(_QWORD *)&v59->Type + 16LL))(v59);
  if ( v58 )
    v58->Release(v58);
  v29 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v30 = &CallStackTracing::s_wpInstance->m_context;
    v31 = GetLastError();
    v32 = (CallStackContext *)TlsGetValue(v29->m_dwTLSIndex);
    if ( v32 )
      goto LABEL_65;
    if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v32 = (CallStackContext *)v38->AllocateNewContext(v38);
      if ( v32 )
LABEL_65:
        v30 = v32;
    }
    SetLastError(v31);
    v33 = v30->m_dwDepth;
    if ( v33 )
    {
      v34 = v33 - 1;
      v30->m_dwDepth = v34;
      if ( !v34 )
      {
        v30->m_dwDepth = 0;
        *(_QWORD *)&v30->m_instanceId = 0;
        v30->m_result = 0;
        v30->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v30->m_dwErrorsInContext = 0;
        v30->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180052b20  mov     [rsp-38h+arg_10], rbx
0x180052b25  push    rbp
0x180052b26  push    rsi
0x180052b27  push    rdi
0x180052b28  push    r12
0x180052b2a  push    r13
0x180052b2c  push    r14
0x180052b2e  push    r15
0x180052b30  mov     rbp, rsp
0x180052b33  sub     rsp, 70h
0x180052b37  mov     rax, cs:__security_cookie
0x180052b3e  xor     rax, rsp
0x180052b41  mov     [rbp+var_10], rax
0x180052b45  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052b4c  lea     r15, stru_1801FC290
0x180052b53  mov     r14, rdx
0x180052b56  mov     rdi, rcx
0x180052b59  test    rsi, rsi
0x180052b5c  jz      loc_180053070
0x180052b62  cmp     byte ptr [rsi+8], 0
0x180052b66  lea     r13, aCmfdx11allocat_16; "CMFDX11Allocator::OnInvokeDelete"
0x180052b6d  jz      short loc_180052BC7
0x180052b6f  lea     rbx, [rsi+0D0h]
0x180052b76  call    cs:__imp_GetLastError
0x180052b7c  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180052b7f  mov     r15d, eax
0x180052b82  call    cs:__imp_TlsGetValue
0x180052b88  test    rax, rax
0x180052b8b  jz      loc_1800530B2
0x180052b91  mov     rbx, rax
0x180052b94  mov     ecx, r15d; dwErrCode
0x180052b97  call    cs:__imp_SetLastError
0x180052b9d  mov     eax, [rbx+7C4h]
0x180052ba3  lea     r15, stru_1801FC290
0x180052baa  cmp     eax, [rbx+7C8h]
0x180052bb0  jnb     short loc_180052BC1
0x180052bb2  add     rax, rax
0x180052bb5  mov     [rbx+rax*8], r13
0x180052bb9  mov     dword ptr [rbx+rax*8+8], 59Dh
0x180052bc1  inc     dword ptr [rbx+7C4h]
0x180052bc7  mov     rcx, [rdi+5A8h]
0x180052bce  xor     r12d, r12d
0x180052bd1  mov     [rbp+var_40], r12
0x180052bd5  xorps   xmm0, xmm0
0x180052bd8  mov     [rbp+var_38], r12
0x180052bdc  mov     [rbp+var_30], r12
0x180052be0  mov     [rbp+var_28], r12
0x180052be4  movups  [rbp+var_20], xmm0
0x180052be8  test    rcx, rcx
0x180052beb  jnz     short loc_180052BFC
0x180052bed  lea     rbx, [rdi+28h]
0x180052bf1  mov     rcx, rbx; lpCriticalSection
0x180052bf4  call    cs:__imp_EnterCriticalSection
0x180052bfa  jmp     short loc_180052C32
0x180052bfc  mov     rax, [rcx]
0x180052bff  lea     r8, [rbp+var_28]
0x180052c03  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x180052c0a  mov     esi, r12d
0x180052c0d  mov     rax, [rax]
0x180052c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c15  test    eax, eax
0x180052c17  jns     loc_18005351A
0x180052c1d  lea     rbx, [rdi+28h]
0x180052c21  mov     rcx, rbx; lpCriticalSection
0x180052c24  call    cs:__imp_EnterCriticalSection
0x180052c2a  test    esi, esi
0x180052c2c  js      loc_1800531CA
0x180052c32  test    r14, r14
0x180052c35  jz      loc_180053250
0x180052c3b  mov     rax, [r14]
0x180052c3e  lea     rdx, [rbp+var_38]
0x180052c42  mov     rcx, r14
0x180052c45  mov     rax, [rax+18h]
0x180052c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c4e  mov     esi, eax
0x180052c50  test    eax, eax
0x180052c52  js      loc_1800532DB
0x180052c58  mov     rcx, [rbp+var_38]
0x180052c5c  lea     r8, [rbp+var_40]
0x180052c60  lea     rdx, _GUID_c40a00f2_b93a_4d80_ae8c_5a1c634f58e4
0x180052c67  mov     rax, [rcx]
0x180052c6a  mov     rax, [rax]
0x180052c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c72  mov     esi, eax
0x180052c74  test    eax, eax
0x180052c76  js      loc_180053361
0x180052c7c  movzx   edx, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x180052c83  cmp     dl, 8
0x180052c86  jnb     loc_1800535D2
0x180052c8c  mov     rax, [rdi+578h]
0x180052c93  mov     r8, [rbp+var_38]
0x180052c97  mov     rcx, rax
0x180052c9a  test    rcx, rcx
0x180052c9d  jz      loc_180052D26
0x180052ca3  mov     r9, [rcx+8]
0x180052ca7  cmp     [rcx], r8
0x180052caa  jnz     loc_180053060
0x180052cb0  cmp     rcx, rax
0x180052cb3  jz      loc_180053022
0x180052cb9  mov     rax, [rcx+10h]
0x180052cbd  mov     [rax+8], r9
0x180052cc1  mov     r8, [rcx+10h]
0x180052cc5  cmp     rcx, [rdi+580h]
0x180052ccc  jnz     loc_180053046
0x180052cd2  mov     [rdi+580h], r8
0x180052cd9  mov     rax, [rdi+3D0h]
0x180052ce0  mov     [rcx+8], rax
0x180052ce4  mov     [rdi+3D0h], rcx
0x180052ceb  dec     dword ptr [rdi+588h]
0x180052cf1  cmp     dl, 8
0x180052cf4  jb      short loc_180052D1E
0x180052cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180052cfd  lea     r8, WPP_ba017baebdd33e3699b8b83fd5fc9597_Traceguids
0x180052d04  mov     rax, [rbp+var_40]
0x180052d08  mov     edx, 6Ah ; 'j'
0x180052d0d  mov     r9, rdi
0x180052d10  mov     [rsp+70h+var_50], rax
0x180052d15  mov     rcx, [rcx+10h]
0x180052d19  call    WPP_SF_qq
0x180052d1e  mov     esi, r12d
0x180052d21  jmp     loc_180052EF3
0x180052d26  cmp     dl, 10h
0x180052d29  jnb     loc_180053606
0x180052d2f  mov     rcx, [rbp+var_40]
0x180052d33  lea     r8, [rbp+var_30]
0x180052d37  lea     rdx, _GUID_6dc5a5a6_e640_4328_9c05_41a2c952d409
0x180052d3e  mov     rax, [rcx]
0x180052d41  mov     rax, [rax]
0x180052d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d49  mov     esi, eax
0x180052d4b  test    eax, eax
0x180052d4d  js      loc_1800533E7
0x180052d53  mov     rcx, [rbp+var_40]
0x180052d57  lea     r8, [rbp+var_20]
0x180052d5b  lea     rdx, MFSampleExtension_MDLCacheCookie
0x180052d62  mov     rax, [rcx]
0x180052d65  mov     rax, [rax+50h]
0x180052d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d6e  mov     r8, [rbp+var_30]
0x180052d72  mov     esi, eax
0x180052d74  mov     rcx, [r8]
0x180052d77  mov     rax, [rcx+20h]
0x180052d7b  mov     rcx, r8
0x180052d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d83  test    esi, esi
0x180052d85  js      short loc_180052DA5
0x180052d87  mov     rcx, [rbp+var_40]
0x180052d8b  lea     r8, [rbp+var_20]
0x180052d8f  lea     rdx, MFSampleExtension_MDLCacheCookie
0x180052d96  mov     rax, [rcx]
0x180052d99  mov     rax, [rax+0C0h]
0x180052da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052da5  mov     rax, [rdi+3B8h]
0x180052dac  mov     rdx, [rbp+var_38]
0x180052db0  mov     rcx, rax
0x180052db3  test    rcx, rcx
0x180052db6  jz      short loc_180052E06
0x180052db8  mov     r8, [rcx+8]
0x180052dbc  cmp     [rcx], rdx
0x180052dbf  jnz     loc_180053068
0x180052dc5  cmp     rcx, rax
0x180052dc8  jz      loc_18005303A
0x180052dce  mov     rax, [rcx+10h]
0x180052dd2  mov     [rax+8], r8
0x180052dd6  mov     rdx, [rcx+10h]
0x180052dda  cmp     rcx, [rdi+3C0h]
0x180052de1  jnz     loc_180053053
0x180052de7  mov     [rdi+3C0h], rdx
0x180052dee  mov     rax, [rdi+210h]
0x180052df5  mov     [rcx+8], rax
0x180052df9  mov     [rdi+210h], rcx
0x180052e00  dec     dword ptr [rdi+3C8h]
0x180052e06  mov     r15, [rbp+var_40]
0x180052e0a  cmp     [rdi+50h], r12
0x180052e0e  jz      loc_180053633
0x180052e14  mov     rcx, [rdi+50h]
0x180052e18  mov     esi, r12d
0x180052e1b  mov     rax, [rcx+8]
0x180052e1f  mov     [rdi+50h], rax
0x180052e23  mov     [rcx], r15
0x180052e26  mov     [rcx+8], r12
0x180052e2a  mov     rax, [rdi+200h]
0x180052e31  mov     [rcx+10h], rax
0x180052e35  mov     rax, [rdi+200h]
0x180052e3c  test    rax, rax
0x180052e3f  jz      loc_18005302E
0x180052e45  mov     [rax+8], rcx
0x180052e49  inc     dword ptr [rdi+208h]
0x180052e4f  mov     [rdi+200h], rcx
0x180052e56  inc     dword ptr [rdi+59Ch]
0x180052e5c  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180052e63  mov     ecx, [rdi+59Ch]
0x180052e69  jnz     loc_180053118
0x180052e6f  mov     rcx, [rdi+638h]
0x180052e76  mov     [rbp+var_40], r12
0x180052e7a  test    rcx, rcx
0x180052e7d  jz      loc_180052FFC
0x180052e83  mov     rax, [rcx]
0x180052e86  mov     rax, [rax+18h]
0x180052e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e8f  mov     rcx, [r14+50h]
0x180052e93  test    rcx, rcx
0x180052e96  jz      short loc_180052EA4
0x180052e98  mov     rax, [rcx]
0x180052e9b  mov     rax, [rax+10h]
0x180052e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ea4  mov     rcx, [r14+58h]
0x180052ea8  mov     [r14+50h], r12
0x180052eac  test    rcx, rcx
0x180052eaf  jz      short loc_180052EBD
0x180052eb1  mov     rax, [rcx]
0x180052eb4  mov     rax, [rax+10h]
0x180052eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ebd  mov     rcx, [rbp+var_30]
0x180052ec1  mov     [r14+58h], r12
0x180052ec5  test    rcx, rcx
0x180052ec8  jz      short loc_180052EDA
0x180052eca  mov     [rbp+var_30], r12
0x180052ece  mov     rax, [rcx]
0x180052ed1  mov     rax, [rax+10h]
0x180052ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052eda  mov     rcx, [rbp+var_38]
0x180052ede  test    rcx, rcx
0x180052ee1  jz      short loc_180052EF3
0x180052ee3  mov     [rbp+var_38], r12
0x180052ee7  mov     rax, [rcx]
0x180052eea  mov     rax, [rax+10h]
0x180052eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ef3  mov     rcx, rbx; lpCriticalSection
0x180052ef6  call    cs:__imp_LeaveCriticalSection
0x180052efc  mov     rcx, [rbp+var_28]
0x180052f00  test    rcx, rcx
0x180052f03  jz      short loc_180052F11
0x180052f05  mov     rax, [rcx]
0x180052f08  mov     rax, [rax+10h]
0x180052f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f11  mov     rcx, [rbp+var_30]
0x180052f15  test    rcx, rcx
0x180052f18  jz      short loc_180052F26
0x180052f1a  mov     rax, [rcx]
0x180052f1d  mov     rax, [rax+10h]
0x180052f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f26  mov     rcx, [rbp+var_38]
0x180052f2a  test    rcx, rcx
0x180052f2d  jz      short loc_180052F3B
0x180052f2f  mov     rax, [rcx]
0x180052f32  mov     rax, [rax+10h]
0x180052f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f3b  mov     rcx, [rbp+var_40]
0x180052f3f  test    rcx, rcx
0x180052f42  jz      short loc_180052F50
0x180052f44  mov     rax, [rcx]
0x180052f47  mov     rax, [rax+10h]
0x180052f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f50  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f57  cmp     [rdi+8], r12b
0x180052f5b  jz      short loc_180052FD6
0x180052f5d  lea     rbx, [rdi+0D0h]
0x180052f64  call    cs:__imp_GetLastError
0x180052f6a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180052f6d  mov     r14d, eax
0x180052f70  call    cs:__imp_TlsGetValue
0x180052f76  test    rax, rax
0x180052f79  jz      loc_1800530E5
0x180052f7f  mov     rbx, rax
0x180052f82  mov     ecx, r14d; dwErrCode
0x180052f85  call    cs:__imp_SetLastError
0x180052f8b  mov     eax, [rbx+7C4h]
0x180052f91  test    eax, eax
0x180052f93  jz      short loc_180052FD6
0x180052f95  sub     eax, 1
0x180052f98  mov     [rbx+7C4h], eax
0x180052f9e  jnz     short loc_180052FD6
0x180052fa0  mov     [rbx+7C4h], r12d
0x180052fa7  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180052fae  mov     [rbx+7E0h], r12
0x180052fb5  mov     [rbx+7CCh], r12d
0x180052fbc  movups  xmmword ptr [rbx+7D0h], xmm0
0x180052fc3  mov     [rbx+7E8h], r12d
0x180052fca  call    cs:__imp_GetCurrentThreadId
0x180052fd0  mov     [rbx+7C0h], eax
0x180052fd6  mov     eax, esi
0x180052fd8  mov     rcx, [rbp+var_10]
0x180052fdc  xor     rcx, rsp; StackCookie
0x180052fdf  call    __security_check_cookie
0x180052fe4  mov     rbx, [rsp+70h+arg_10]
0x180052fec  add     rsp, 70h
0x180052ff0  pop     r15
0x180052ff2  pop     r14
0x180052ff4  pop     r13
0x180052ff6  pop     r12
0x180052ff8  pop     rdi
0x180052ff9  pop     rsi
0x180052ffa  pop     rbp
0x180052ffb  retn
0x180052ffc  cmp     [rdi+5F0h], r12d
0x180053003  jz      loc_180052E8F
0x180053009  mov     rcx, [rdi+5C0h]; hEvent
0x180053010  mov     [rdi+5F0h], r12d
0x180053017  call    cs:__imp_SetEvent
  ... truncated ...
```
