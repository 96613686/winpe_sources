# CMFMediaEventGenerator::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)

- ea: `0x180026aa0`
- end: `0x1800272d4`
- name: `?QueueEvent@CMFMediaEventGenerator@@QEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z`
- size: `2100`
- prototype: `__int64 __usercall@<rax>(CMFMediaEventGenerator *__hidden this@<rcx>, unsigned int@<edx>, const struct _GUID *@<r8>, int@<r9d>, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028880`

## callees

- `0x18000d454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x180026aa0`
- `0x180027880`
- `0x18004845c`
- `0x180048bbc`
- `0x180055704`
- `0x18011fff0`
- `0x180138c34`
- `0x180196954`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026c7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026c12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026cf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027172`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026b0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026d8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026b0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026d8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026de6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026da1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002707a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002707a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270b1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026bee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026ec1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026bee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026ec1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026c05`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026c05`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026ed8`

## pseudocode

```c
__int64 __fastcall CMFMediaEventGenerator::QueueEvent(
        CMFMediaEventGenerator *this,
        unsigned int a2,
        const struct _GUID *a3,
        int a4,
        const struct tagPROPVARIANT *pvarSrc)
{
  CallStackTracing *v9; // rbx
  CallStackContext *p_m_context; // rdi
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v14; // rax
  __int128 v15; // xmm6
  struct IMFMediaEvent *v16; // rbx
  IMFMediaEvent_vtbl *v17; // rcx
  unsigned int v18; // ebp
  IMFMediaEvent_vtbl *v19; // rax
  unsigned int v20; // edx
  unsigned int v21; // ecx
  struct CEventResult *p_m_pPool; // rdi
  IMFMediaEvent *m_pEvent; // rcx
  _LIST_ENTRY *v24; // rax
  CallStackTracing *v25; // rbx
  CallStackContext *v26; // rdi
  DWORD v27; // esi
  CallStackContext *v28; // rax
  unsigned int v29; // eax
  unsigned int v30; // eax
  CMFMediaEvent *v32; // rax
  IMFMediaEvent_vtbl *v33; // rcx
  CallStackTracing *v34; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rcx
  const char *v38; // rax
  int v39; // edx
  int v40; // r8d
  int v41; // [rsp+30h] [rbp-48h] BYREF
  struct CEventResult *v42; // [rsp+38h] [rbp-40h] BYREF
  int v43; // [rsp+80h] [rbp+8h] BYREF

  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  v9 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    p_m_context = &CallStackTracing::s_wpInstance->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v9->m_dwTLSIndex);
    if ( Value )
      goto LABEL_4;
    if ( !GetLastError() )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v36 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      Value = (CallStackContext *)v36->AllocateNewContext(v36);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v14 = m_dwDepth;
      p_m_context->m_rgInfo[v14].m_pszFunction = "CMFMediaEventGenerator::QueueEvent";
      p_m_context->m_rgInfo[v14].m_lineNumber = 366;
    }
    ++p_m_context->m_dwDepth;
  }
  if ( (unsigned __int8)byte_1801FD28B >= 0x10u )
  {
    v38 = MFTRACE_STRING_FROM_MET(a2);
    WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v39, v40, (_DWORD)this, (__int64)v38, a4);
  }
  if ( *((_DWORD *)this + 12) )
  {
    v18 = -1072873851;
    goto LABEL_33;
  }
  v15 = (__int128)*a3;
  EnterCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
  v16 = (struct IMFMediaEvent *)&stru_1801FC158.m_pHead[-5];
  if ( !stru_1801FC158.m_pHead )
    v16 = 0;
  if ( v16 )
  {
    stru_1801FC158.m_pHead = (CPooledObject *)v16[16].__vftable;
    v16->AddRef(v16);
    v16[17].__vftable = (IMFMediaEvent_vtbl *)&stru_1801FC158;
    v17 = v16[14].__vftable;
    HIDWORD(v16[7].__vftable) = a2;
    LODWORD(v16[10].__vftable) = a4;
    *(_OWORD *)&v16[8].__vftable = v15;
    if ( v17 )
    {
      (*((void (__fastcall **)(IMFMediaEvent_vtbl *))v17->QueryInterface + 2))(v17);
      v16[14].__vftable = 0;
    }
    v18 = -1072873851;
    if ( a4 < 0 && a4 != -2147023441 && a4 != -1072875780 && a4 != -1072873851 && a4 != -2147024882 )
    {
      s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v16[14]);
      if ( !v16[14].__vftable )
      {
        s_pErrorInfoHandler->Capture(s_pErrorInfoHandler, a4);
        s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v16[14]);
      }
    }
    PropVariantClear((PROPVARIANT *)&v16[11].__vftable);
    if ( pvarSrc )
      PropVariantCopy((PROPVARIANT *)&v16[11].__vftable, (const PROPVARIANT *)pvarSrc);
  }
  else
  {
    v32 = (CMFMediaEvent *)operator new(0x98u);
    v16 = v32;
    if ( !v32 )
    {
      LeaveCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
      v18 = -2147024882;
      goto LABEL_33;
    }
    CMFMediaEvent::CMFMediaEvent(v32);
    v16[16].__vftable = 0;
    v16[17].__vftable = 0;
    v16->__vftable = (IMFMediaEvent_vtbl *)&CMediaEventPooled::`vftable'{for `CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>'};
    v16[6].__vftable = (IMFMediaEvent_vtbl *)&CMediaEventPooled::`vftable'{for `CPoolableObject'};
    v16[15].__vftable = (IMFMediaEvent_vtbl *)&CMediaEventPooled::`vftable';
    LODWORD(v16[18].__vftable) = 0;
    v33 = v16[14].__vftable;
    HIDWORD(v16[7].__vftable) = a2;
    LODWORD(v16[10].__vftable) = a4;
    *(_OWORD *)&v16[8].__vftable = v15;
    if ( v33 )
    {
      (*((void (__fastcall **)(IMFMediaEvent_vtbl *))v33->QueryInterface + 2))(v33);
      v16[14].__vftable = 0;
    }
    v18 = -1072873851;
    if ( a4 < 0 && a4 != -2147023441 && a4 != -1072875780 && a4 != -1072873851 && a4 != -2147024882 )
    {
      s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v16[14]);
      if ( !v16[14].__vftable )
      {
        s_pErrorInfoHandler->Capture(s_pErrorInfoHandler, a4);
        s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)&v16[14]);
      }
    }
    PropVariantClear((PROPVARIANT *)&v16[11].__vftable);
    if ( pvarSrc )
      PropVariantCopy((PROPVARIANT *)&v16[11].__vftable, (const PROPVARIANT *)pvarSrc);
    if ( stru_1801FC158.m_dwCount < stru_1801FC158.m_dwMaxSize && stru_1801FC158.m_fEnabled )
    {
      v16[17].__vftable = (IMFMediaEvent_vtbl *)&stru_1801FC158;
      ++stru_1801FC158.m_dwCount;
    }
  }
  LeaveCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
  v41 = 0;
  v19 = v16->__vftable;
  v43 = 0;
  if ( v19->GetType(v16, (unsigned int *)&v43) >= 0 && v43 == 1 && v16->GetStatus(v16, &v41) >= 0 )
  {
    v34 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v34 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v34->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v34);
      if ( v41 < 0 && ThreadRelativeContext->m_result != v41 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMediaEventGenerator::QueueEvent", 458, v41);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !*((_DWORD *)this + 12) )
  {
    if ( (unsigned __int8)byte_1801FD28B >= 0x10u )
      MFTRACE_MEDIA_EVENT_IMPL(v21, v20, v16);
    EnterCriticalSection(&stru_1801FC1A0.m_csPool.m_CritSec);
    if ( stru_1801FC1A0.m_pHead )
    {
      p_m_pPool = (struct CEventResult *)&stru_1801FC1A0.m_pHead[-5].m_pPool;
      v42 = (struct CEventResult *)&stru_1801FC1A0.m_pHead[-5].m_pPool;
      if ( stru_1801FC1A0.m_pHead != (CPooledObject *)104 )
      {
        stru_1801FC1A0.m_pHead = p_m_pPool->m_pNext;
        p_m_pPool->AddRef(p_m_pPool);
        p_m_pPool->m_pPool = &stru_1801FC1A0;
        m_pEvent = p_m_pPool->m_pEvent;
        if ( m_pEvent )
          m_pEvent->Release(m_pEvent);
        p_m_pPool->m_pEvent = v16;
        if ( v16 )
          v16->AddRef(v16);
        goto LABEL_30;
      }
    }
    else
    {
      v42 = 0;
    }
    if ( (int)CEventResult::CreateInstance(v16, &v42) >= 0 )
    {
      p_m_pPool = v42;
      if ( v42 )
      {
        CObjectPool::TrackObject(&stru_1801FC1A0, &v42->CPooledObject);
LABEL_30:
        LeaveCriticalSection(&stru_1801FC1A0.m_csPool.m_CritSec);
        v24 = (_LIST_ENTRY *)*((_QWORD *)this + 9);
        p_m_pPool->m_List.Blink = v24;
        p_m_pPool->m_List.Flink = (_LIST_ENTRY *)((char *)this + 64);
        v24->Flink = &p_m_pPool->m_List;
        ++*((_DWORD *)this + 14);
        *((_QWORD *)this + 9) = &p_m_pPool->m_List;
        v18 = CMFMediaEventGenerator::CheckDispatchEvent(this);
        goto LABEL_31;
      }
    }
    LeaveCriticalSection(&stru_1801FC1A0.m_csPool.m_CritSec);
    v18 = -2147024882;
  }
LABEL_31:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v16 )
    v16->Release(v16);
LABEL_33:
  if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 20, &WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids, this, v18);
  v25 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v26 = &CallStackTracing::s_wpInstance->m_context;
    v27 = GetLastError();
    v28 = (CallStackContext *)TlsGetValue(v25->m_dwTLSIndex);
    if ( v28 )
      goto LABEL_37;
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
      v28 = (CallStackContext *)v37->AllocateNewContext(v37);
      if ( v28 )
LABEL_37:
        v26 = v28;
    }
    SetLastError(v27);
    v29 = v26->m_dwDepth;
    if ( v29 )
    {
      v30 = v29 - 1;
      v26->m_dwDepth = v30;
      if ( !v30 )
      {
        v26->m_dwDepth = 0;
        *(_QWORD *)&v26->m_instanceId = 0;
        v26->m_result = 0;
        v26->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v26->m_dwErrorsInContext = 0;
        v26->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180026aa0  mov     rax, rsp
0x180026aa3  push    rbx
0x180026aa4  push    rbp
0x180026aa5  push    rsi
0x180026aa6  push    r12
0x180026aa8  sub     rsp, 58h
0x180026aac  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ab4  lea     rbx, stru_1801F8A30
0x180026abb  mov     [rax+18h], r13
0x180026abf  mov     rsi, rcx
0x180026ac2  mov     [rax+20h], r14
0x180026ac6  lea     rcx, stru_1801FC290
0x180026acd  mov     [rax-28h], r15
0x180026ad1  mov     r14d, r9d
0x180026ad4  mov     r15d, edx
0x180026ad7  mov     rbp, r8
0x180026ada  jz      loc_180026F2C
0x180026ae0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ae7  lea     r13, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x180026aee  mov     [rsp+78h+arg_8], rdi
0x180026af6  cmp     byte ptr [rbx+8], 0
0x180026afa  jz      short loc_180026B4D
0x180026afc  lea     rdi, [rbx+0D0h]
0x180026b03  call    cs:__imp_GetLastError
0x180026b09  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180026b0c  mov     r12d, eax
0x180026b0f  call    cs:__imp_TlsGetValue
0x180026b15  test    rax, rax
0x180026b18  jz      loc_18002707A
0x180026b1e  mov     rdi, rax
0x180026b21  mov     ecx, r12d; dwErrCode
0x180026b24  call    cs:__imp_SetLastError
0x180026b2a  mov     eax, [rdi+7C4h]
0x180026b30  cmp     eax, [rdi+7C8h]
0x180026b36  jnb     short loc_180026B47
0x180026b38  add     rax, rax
0x180026b3b  mov     [rdi+rax*8], r13
0x180026b3f  mov     dword ptr [rdi+rax*8+8], 16Eh
0x180026b47  inc     dword ptr [rdi+7C4h]
0x180026b4d  cmp     cs:byte_1801FD28B, 10h
0x180026b54  jnb     loc_18002727F
0x180026b5a  xor     r12d, r12d
0x180026b5d  cmp     [rsi+30h], r12d
0x180026b61  jnz     loc_1800272AC
0x180026b67  movaps  [rsp+78h+var_38], xmm6
0x180026b6c  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x180026b73  movups  xmm6, xmmword ptr [rbp+0]
0x180026b77  call    cs:__imp_EnterCriticalSection
0x180026b7d  mov     rcx, cs:stru_1801FC158.m_pHead
0x180026b84  test    rcx, rcx
0x180026b87  lea     rbx, [rcx-78h]
0x180026b8b  cmovz   rbx, r12
0x180026b8f  test    rbx, rbx
0x180026b92  jz      loc_180026E43
0x180026b98  mov     rax, [rbx+80h]
0x180026b9f  mov     rcx, rbx
0x180026ba2  mov     cs:stru_1801FC158.m_pHead, rax
0x180026ba9  mov     rax, [rbx]
0x180026bac  mov     rax, [rax+8]
0x180026bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bb5  lea     rax, stru_1801FC158
0x180026bbc  mov     [rbx+88h], rax
0x180026bc3  mov     rcx, [rbx+70h]
0x180026bc7  mov     [rbx+3Ch], r15d
0x180026bcb  mov     [rbx+50h], r14d
0x180026bcf  movups  xmmword ptr [rbx+40h], xmm6
0x180026bd3  test    rcx, rcx
0x180026bd6  jnz     loc_180026F17
0x180026bdc  mov     ebp, 0C00D3E85h
0x180026be1  test    r14d, r14d
0x180026be4  js      loc_180026F73
0x180026bea  lea     rcx, [rbx+58h]; pvar
0x180026bee  call    cs:__imp_PropVariantClear
0x180026bf4  mov     rdx, [rsp+78h+pvarSrc]; pvarSrc
0x180026bfc  test    rdx, rdx
0x180026bff  jz      short loc_180026C0B
0x180026c01  lea     rcx, [rbx+58h]; pvarDest
0x180026c05  call    cs:__imp_PropVariantCopy
0x180026c0b  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x180026c12  call    cs:__imp_LeaveCriticalSection
0x180026c18  mov     eax, r12d
0x180026c1b  lea     rdx, [rsp+78h+arg_0]
0x180026c23  mov     [rsp+78h+var_48], eax
0x180026c27  mov     ecx, r12d
0x180026c2a  mov     rax, [rbx]
0x180026c2d  mov     [rsp+78h+arg_0], ecx
0x180026c34  mov     rcx, rbx
0x180026c37  mov     rax, [rax+108h]
0x180026c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c43  test    eax, eax
0x180026c45  js      short loc_180026C55
0x180026c47  cmp     [rsp+78h+arg_0], 1
0x180026c4f  jz      loc_18002700B
0x180026c55  lea     rcx, [rsi+8]; lpCriticalSection
0x180026c59  call    cs:__imp_EnterCriticalSection
0x180026c5f  cmp     [rsi+30h], r12d
0x180026c63  jnz     loc_180026D29
0x180026c69  cmp     cs:byte_1801FD28B, 10h
0x180026c70  jnb     loc_1800272B6
0x180026c76  lea     rcx, stru_1801FC1A0.m_csPool; lpCriticalSection
0x180026c7d  call    cs:__imp_EnterCriticalSection
0x180026c83  mov     rdi, cs:stru_1801FC1A0.m_pHead
0x180026c8a  test    rdi, rdi
0x180026c8d  jz      loc_180026E06
0x180026c93  add     rdi, 0FFFFFFFFFFFFFF98h
0x180026c97  mov     [rsp+78h+var_40], rdi
0x180026c9c  jz      loc_180026E0B
0x180026ca2  mov     rax, [rdi+70h]
0x180026ca6  mov     rcx, rdi
0x180026ca9  mov     cs:stru_1801FC1A0.m_pHead, rax
0x180026cb0  mov     rax, [rdi]
0x180026cb3  mov     rax, [rax+8]
0x180026cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cbc  lea     rcx, stru_1801FC1A0
0x180026cc3  mov     [rdi+78h], rcx
0x180026cc7  mov     rcx, [rdi+90h]
0x180026cce  test    rcx, rcx
0x180026cd1  jnz     loc_1800272C3
0x180026cd7  mov     [rdi+90h], rbx
0x180026cde  test    rbx, rbx
0x180026ce1  jz      short loc_180026CF2
0x180026ce3  mov     rax, [rbx]
0x180026ce6  mov     rcx, rbx
0x180026ce9  mov     rax, [rax+8]
0x180026ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cf2  lea     rcx, stru_1801FC1A0.m_csPool; lpCriticalSection
0x180026cf9  call    cs:__imp_LeaveCriticalSection
0x180026cff  mov     rax, [rsi+48h]
0x180026d03  lea     rdx, [rdi+80h]
0x180026d0a  lea     rcx, [rsi+40h]
0x180026d0e  mov     [rdx+8], rax
0x180026d12  mov     [rdx], rcx
0x180026d15  mov     [rax], rdx
0x180026d18  inc     dword ptr [rsi+38h]
0x180026d1b  mov     [rcx+8], rdx
0x180026d1f  mov     rcx, rsi; this
0x180026d22  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x180026d27  mov     ebp, eax
0x180026d29  lea     rcx, [rsi+8]; lpCriticalSection
0x180026d2d  call    cs:__imp_LeaveCriticalSection
0x180026d33  test    rbx, rbx
0x180026d36  jz      short loc_180026D47
0x180026d38  mov     rax, [rbx]
0x180026d3b  mov     rcx, rbx
0x180026d3e  mov     rax, [rax+10h]
0x180026d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d47  movaps  xmm6, [rsp+78h+var_38]
0x180026d4c  mov     r15, [rsp+78h+var_28]
0x180026d51  mov     r14, [rsp+78h+arg_18]
0x180026d59  mov     r13, [rsp+78h+arg_10]
0x180026d61  cmp     cs:byte_1801FD28B, 20h ; ' '
0x180026d68  jnb     loc_1800271C8
0x180026d6e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026d75  cmp     [rbx+8], r12b
0x180026d79  jz      short loc_180026DF2
0x180026d7b  lea     rdi, [rbx+0D0h]
0x180026d82  call    cs:__imp_GetLastError
0x180026d88  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180026d8b  mov     esi, eax
0x180026d8d  call    cs:__imp_TlsGetValue
0x180026d93  test    rax, rax
0x180026d96  jz      loc_1800270B1
0x180026d9c  mov     rdi, rax
0x180026d9f  mov     ecx, esi; dwErrCode
0x180026da1  call    cs:__imp_SetLastError
0x180026da7  mov     eax, [rdi+7C4h]
0x180026dad  test    eax, eax
0x180026daf  jz      short loc_180026DF2
0x180026db1  sub     eax, 1
0x180026db4  mov     [rdi+7C4h], eax
0x180026dba  jnz     short loc_180026DF2
0x180026dbc  mov     [rdi+7C4h], r12d
0x180026dc3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180026dca  mov     [rdi+7E0h], r12
0x180026dd1  mov     [rdi+7CCh], r12d
0x180026dd8  movups  xmmword ptr [rdi+7D0h], xmm0
0x180026ddf  mov     [rdi+7E8h], r12d
0x180026de6  call    cs:__imp_GetCurrentThreadId
0x180026dec  mov     [rdi+7C0h], eax
0x180026df2  mov     rdi, [rsp+78h+arg_8]
0x180026dfa  mov     eax, ebp
0x180026dfc  add     rsp, 58h
0x180026e00  pop     r12
0x180026e02  pop     rsi
0x180026e03  pop     rbp
0x180026e04  pop     rbx
0x180026e05  retn
0x180026e06  mov     [rsp+78h+var_40], r12
0x180026e0b  lea     rdx, [rsp+78h+var_40]; struct CEventResult **
0x180026e10  mov     rcx, rbx; struct IMFMediaEvent *
0x180026e13  call    ?CreateInstance@CEventResult@@SAJPEAUIMFMediaEvent@@PEAPEAV1@@Z; CEventResult::CreateInstance(IMFMediaEvent *,CEventResult * *)
0x180026e18  test    eax, eax
0x180026e1a  js      loc_18002716B
0x180026e20  mov     rdi, [rsp+78h+var_40]
0x180026e25  test    rdi, rdi
0x180026e28  jz      loc_18002716B
0x180026e2e  lea     rdx, [rdi+68h]; struct CPooledObject *
0x180026e32  lea     rcx, stru_1801FC1A0; this
0x180026e39  call    ?TrackObject@CObjectPool@@QEAAXPEAVCPooledObject@@@Z; CObjectPool::TrackObject(CPooledObject *)
0x180026e3e  jmp     loc_180026CF2
0x180026e43  mov     ecx, 98h; Size
0x180026e48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026e4d  mov     rbx, rax
0x180026e50  test    rax, rax
0x180026e53  jz      loc_180026F5C
0x180026e59  mov     rcx, rax; this
0x180026e5c  call    ??0CMFMediaEvent@@QEAA@XZ; CMFMediaEvent::CMFMediaEvent(void)
0x180026e61  mov     [rbx+80h], r12
0x180026e68  lea     rax, ??_7CMediaEventPooled@@6B?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@@; const CMediaEventPooled::`vftable'{for `CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>'}
0x180026e6f  mov     [rbx+88h], r12
0x180026e76  mov     [rbx], rax
0x180026e79  lea     rax, ??_7CMediaEventPooled@@6BCPoolableObject@@@; const CMediaEventPooled::`vftable'{for `CPoolableObject'}
0x180026e80  mov     [rbx+30h], rax
0x180026e84  lea     rax, ??_7CMediaEventPooled@@6B@; const CMediaEventPooled::`vftable'
0x180026e8b  mov     [rbx+78h], rax
0x180026e8f  mov     [rbx+90h], r12d
0x180026e96  mov     rcx, [rbx+70h]
0x180026e9a  mov     [rbx+3Ch], r15d
0x180026e9e  mov     [rbx+50h], r14d
0x180026ea2  movups  xmmword ptr [rbx+40h], xmm6
0x180026ea6  test    rcx, rcx
0x180026ea9  jnz     loc_180026FF6
0x180026eaf  mov     ebp, 0C00D3E85h
0x180026eb4  test    r14d, r14d
0x180026eb7  js      loc_1800270E8
0x180026ebd  lea     rcx, [rbx+58h]; pvar
0x180026ec1  call    cs:__imp_PropVariantClear
0x180026ec7  mov     rdx, [rsp+78h+pvarSrc]; pvarSrc
0x180026ecf  test    rdx, rdx
0x180026ed2  jz      short loc_180026EDE
0x180026ed4  lea     rcx, [rbx+58h]; pvarDest
0x180026ed8  call    cs:__imp_PropVariantCopy
0x180026ede  mov     eax, cs:stru_1801FC158.m_dwMaxSize
0x180026ee4  cmp     cs:stru_1801FC158.m_dwCount, eax
0x180026eea  jnb     loc_180026C0B
0x180026ef0  mov     eax, cs:stru_1801FC158.m_fEnabled
0x180026ef6  test    eax, eax
0x180026ef8  jz      loc_180026C0B
0x180026efe  lea     rax, stru_1801FC158
0x180026f05  mov     [rbx+88h], rax
0x180026f0c  inc     cs:stru_1801FC158.m_dwCount
0x180026f12  jmp     loc_180026C0B
0x180026f17  mov     rax, [rcx]
0x180026f1a  mov     rax, [rax+10h]
0x180026f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f23  mov     [rbx+70h], r12
0x180026f27  jmp     loc_180026BDC
0x180026f2c  mov     rax, cs:stru_1801FC290.__vftable
0x180026f33  mov     edx, 7F0h
0x180026f38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026f3f  mov     rax, [rax+8]
0x180026f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f48  test    eax, eax
0x180026f4a  jnz     loc_180026AE0
0x180026f50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026f57  jmp     loc_180026AE0
0x180026f5c  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x180026f63  call    cs:__imp_LeaveCriticalSection
0x180026f69  mov     ebp, 8007000Eh
0x180026f6e  jmp     loc_180026D47
0x180026f73  cmp     r14d, 800705AFh
0x180026f7a  jz      loc_180026BEA
0x180026f80  cmp     r14d, 0C00D36FCh
0x180026f87  jz      loc_180026BEA
0x180026f8d  cmp     r14d, ebp
0x180026f90  jz      loc_180026BEA
0x180026f96  cmp     r14d, 8007000Eh
0x180026f9d  jz      loc_180026BEA
0x180026fa3  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x180026faa  lea     rdx, [rbx+70h]
0x180026fae  mov     rax, [rcx]
0x180026fb1  mov     rax, [rax+8]
0x180026fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fba  cmp     [rbx+70h], r12
0x180026fbe  jnz     loc_180026BEA
0x180026fc4  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x180026fcb  mov     edx, r14d
0x180026fce  mov     rax, [rcx]
0x180026fd1  mov     rax, [rax+10h]
0x180026fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fda  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x180026fe1  lea     rdx, [rbx+70h]
0x180026fe5  mov     rax, [rcx]
0x180026fe8  mov     rax, [rax+8]
0x180026fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ff1  jmp     loc_180026BEA
0x180026ff6  mov     rax, [rcx]
0x180026ff9  mov     rax, [rax+10h]
0x180026ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027002  mov     [rbx+70h], r12
0x180027006  jmp     loc_180026EAF
0x18002700b  mov     rax, [rbx]
0x18002700e  lea     rdx, [rsp+78h+var_48]
0x180027013  mov     rcx, rbx
0x180027016  mov     rax, [rax+118h]
0x18002701d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027022  test    eax, eax
0x180027024  js      loc_180026C55
0x18002702a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180027031  test    rcx, rcx
  ... truncated ...
```
