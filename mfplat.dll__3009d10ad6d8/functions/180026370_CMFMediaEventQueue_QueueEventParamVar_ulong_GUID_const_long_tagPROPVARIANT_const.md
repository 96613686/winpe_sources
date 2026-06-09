# CMFMediaEventQueue::QueueEventParamVar(ulong,_GUID const &,long,tagPROPVARIANT const *)

- ea: `0x180026370`
- end: `0x180026a8d`
- name: `?QueueEventParamVar@CMFMediaEventQueue@@UEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z`
- size: `1821`
- prototype: `int(CMFMediaEventQueue *__hidden this, unsigned int, const struct _GUID *, int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000d454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x180026370`
- `0x180027880`
- `0x180048304`
- `0x180048bbc`
- `0x180055704`
- `0x180138c34`
- `0x180196954`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002652f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002652f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800264e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026609`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800264e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026609`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800263d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026650`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800263d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026650`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026665`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800264c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800264c9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800264dc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800264dc`

## pseudocode

```c
__int64 __fastcall CMFMediaEventQueue::QueueEventParamVar(
        CMFMediaEventQueue *this,
        unsigned int a2,
        const struct _GUID *a3,
        int a4,
        const struct tagPROPVARIANT *pvarSrc)
{
  char *v5; // r15
  CallStackTracing *v9; // rdi
  CallStackContext *p_m_context; // rbx
  DWORD LastError; // esi
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v14; // rax
  struct _GUID v15; // xmm6
  int Instance; // esi
  __int64 v17; // rbx
  int v18; // edi
  _QWORD *v19; // r12
  __int64 v20; // rcx
  unsigned int v21; // edx
  unsigned int v22; // ecx
  _QWORD *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  CallStackTracing *v27; // rdi
  CallStackContext *v28; // rbx
  DWORD v29; // r14d
  CallStackContext *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  CallStackTracing *v34; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  const char *v40; // rax
  int v41; // edx
  int v42; // r8d
  int v43[4]; // [rsp+30h] [rbp-38h] BYREF
  struct _GUID v44; // [rsp+40h] [rbp-28h] BYREF
  struct CMediaEventPooled *v45; // [rsp+B0h] [rbp+48h] BYREF

  v5 = (char *)this - 120;
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
    {
      p_m_context = Value;
    }
    else if ( !GetLastError() )
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
      v37 = v36->AllocateNewContext(v36);
      if ( v37 )
        p_m_context = (CallStackContext *)v37;
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
    v40 = MFTRACE_STRING_FROM_MET(a2);
    WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v41, v42, (_DWORD)v5, (__int64)v40, a4);
  }
  if ( *((_DWORD *)v5 + 12) )
  {
    Instance = -1072873851;
  }
  else
  {
    v15 = *a3;
    v44 = *a3;
    EnterCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
    Instance = -1072873851;
    v17 = (__int64)&stru_1801FC158.m_pHead[-5] & -(__int64)(stru_1801FC158.m_pHead != 0);
    v45 = (struct CMediaEventPooled *)v17;
    if ( v17 )
    {
      stru_1801FC158.m_pHead = *(CPooledObject **)(((__int64)&stru_1801FC158.m_pHead[-5]
                                                  & -(__int64)(stru_1801FC158.m_pHead != 0))
                                                 + 0x80);
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      *(_QWORD *)(v17 + 136) = &stru_1801FC158;
      *(_DWORD *)(v17 + 60) = a2;
      v19 = (_QWORD *)(v17 + 112);
      v20 = *(_QWORD *)(v17 + 112);
      *(_DWORD *)(v17 + 80) = a4;
      *(struct _GUID *)(v17 + 64) = v15;
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        *v19 = 0;
      }
      if ( a4 < 0 && a4 != -2147023441 && a4 != -1072875780 && a4 != -1072873851 && a4 != -2147024882 )
      {
        s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)(v17 + 112));
        if ( !*v19 )
        {
          s_pErrorInfoHandler->Capture(s_pErrorInfoHandler, a4);
          s_pErrorInfoHandler->Get(s_pErrorInfoHandler, (IRestrictedErrorInfo **)(v17 + 112));
        }
      }
      PropVariantClear((PROPVARIANT *)(v17 + 88));
      if ( pvarSrc )
        PropVariantCopy((PROPVARIANT *)(v17 + 88), (const PROPVARIANT *)pvarSrc);
    }
    else
    {
      v18 = CMediaEventPooled::CreateInstance(a2, &v44, a4, pvarSrc, &v45);
      if ( v18 >= 0 && (v17 = (__int64)v45) != 0 )
      {
        if ( stru_1801FC158.m_dwCount < stru_1801FC158.m_dwMaxSize && stru_1801FC158.m_fEnabled )
        {
          v45->m_pPool = &stru_1801FC158;
          ++stru_1801FC158.m_dwCount;
        }
      }
      else
      {
        v17 = 0;
        v18 = -2147024882;
      }
    }
    LeaveCriticalSection(&stru_1801FC158.m_csPool.m_CritSec);
    if ( v18 < 0 )
    {
      Instance = v18;
    }
    else
    {
      LODWORD(v45) = 0;
      v43[0] = 0;
      if ( v17
        && (*(int (__fastcall **)(__int64, struct CMediaEventPooled **))(*(_QWORD *)v17 + 264LL))(v17, &v45) >= 0
        && (_DWORD)v45 == 1
        && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 280LL))(v17, v43) >= 0 )
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
          if ( v43[0] < 0 && ThreadRelativeContext->m_result != v43[0] )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMediaEventGenerator::QueueEvent", 458, v43[0]);
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
      if ( !*((_DWORD *)v5 + 12) )
      {
        if ( (unsigned __int8)byte_1801FD28B >= 0x10u )
          MFTRACE_MEDIA_EVENT_IMPL(v22, v21, (struct IMFMediaEvent *)v17);
        EnterCriticalSection(&stru_1801FC1A0.m_csPool.m_CritSec);
        v23 = (_QWORD *)((__int64)&stru_1801FC1A0.m_pHead[-5].m_pPool & -(__int64)(stru_1801FC1A0.m_pHead != 0));
        *(_QWORD *)&v44.Data1 = v23;
        if ( v23 )
        {
          v24 = (__int64)&stru_1801FC1A0.m_pHead[-5].m_pPool & -(__int64)(stru_1801FC1A0.m_pHead != 0);
          stru_1801FC1A0.m_pHead = *(CPooledObject **)(v24 + 0x70);
          Instance = 0;
          (*(void (__fastcall **)(__int64))(*v23 + 8LL))(v24);
          v23[15] = &stru_1801FC1A0;
          v25 = v23[18];
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          v23[18] = v17;
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
        }
        else
        {
          Instance = CEventResult::CreateInstance((struct IMFMediaEvent *)v17, (struct CEventResult **)&v44);
          if ( Instance >= 0 && (v23 = *(_QWORD **)&v44.Data1) != 0 )
          {
            CObjectPool::TrackObject(&stru_1801FC1A0, (struct CPooledObject *)(*(_QWORD *)&v44.Data1 + 104LL));
          }
          else
          {
            v23 = 0;
            Instance = -2147024882;
          }
        }
        LeaveCriticalSection(&stru_1801FC1A0.m_csPool.m_CritSec);
        if ( Instance >= 0 )
        {
          v26 = (_QWORD *)*((_QWORD *)v5 + 9);
          v23[16] = v5 + 64;
          v23[17] = v26;
          *v26 = v23 + 16;
          ++*((_DWORD *)v5 + 14);
          *((_QWORD *)v5 + 9) = v23 + 16;
          Instance = CMFMediaEventGenerator::CheckDispatchEvent((CMFMediaEventGenerator *)v5);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 20, &WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids, v5, Instance);
  v27 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v28 = &CallStackTracing::s_wpInstance->m_context;
    v29 = GetLastError();
    v30 = (CallStackContext *)TlsGetValue(v27->m_dwTLSIndex);
    if ( v30 )
    {
      v28 = v30;
    }
    else if ( !GetLastError() )
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
      v39 = v38->AllocateNewContext(v38);
      if ( v39 )
        v28 = (CallStackContext *)v39;
    }
    SetLastError(v29);
    v31 = v28->m_dwDepth;
    if ( v31 )
    {
      v32 = v31 - 1;
      v28->m_dwDepth = v32;
      if ( !v32 )
      {
        v28->m_dwDepth = 0;
        *(_QWORD *)&v28->m_instanceId = 0;
        v28->m_result = 0;
        v28->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v28->m_dwErrorsInContext = 0;
        v28->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180026370  push    rbp
0x180026372  push    rbx
0x180026373  push    rsi
0x180026374  push    rdi
0x180026375  push    r12
0x180026377  push    r13
0x180026379  push    r14
0x18002637b  push    r15
0x18002637d  mov     rbp, rsp
0x180026380  sub     rsp, 68h
0x180026384  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002638c  lea     r15, [rcx-78h]
0x180026390  lea     rcx, stru_1801FC290
0x180026397  movaps  [rsp+68h+var_18], xmm6
0x18002639c  mov     r14d, r9d
0x18002639f  lea     rbx, stru_1801F8A30
0x1800263a6  mov     r13, r8
0x1800263a9  mov     r12d, edx
0x1800263ac  jz      loc_18002675A
0x1800263b2  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800263b9  lea     rcx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x1800263c0  cmp     byte ptr [rdi+8], 0
0x1800263c4  jz      short loc_18002641C
0x1800263c6  lea     rbx, [rdi+0D0h]
0x1800263cd  call    cs:__imp_GetLastError
0x1800263d3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800263d6  mov     esi, eax
0x1800263d8  call    cs:__imp_TlsGetValue
0x1800263de  test    rax, rax
0x1800263e1  jz      loc_1800268C1
0x1800263e7  mov     rbx, rax
0x1800263ea  mov     ecx, esi; dwErrCode
0x1800263ec  call    cs:__imp_SetLastError
0x1800263f2  mov     eax, [rbx+7C4h]
0x1800263f8  lea     rcx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x1800263ff  cmp     eax, [rbx+7C8h]
0x180026405  jnb     short loc_180026416
0x180026407  add     rax, rax
0x18002640a  mov     [rbx+rax*8], rcx
0x18002640e  mov     dword ptr [rbx+rax*8+8], 16Eh
0x180026416  inc     dword ptr [rbx+7C4h]
0x18002641c  cmp     cs:byte_1801FD28B, 10h
0x180026423  jnb     loc_180026A35
0x180026429  cmp     dword ptr [r15+30h], 0
0x18002642e  jnz     loc_180026A62
0x180026434  movups  xmm6, xmmword ptr [r13+0]
0x180026439  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x180026440  movaps  xmmword ptr [rbp+var_28.Data1], xmm6
0x180026444  call    cs:__imp_EnterCriticalSection
0x18002644a  mov     rax, cs:stru_1801FC158.m_pHead
0x180026451  mov     esi, 0C00D3E85h
0x180026456  lea     rcx, [rax-78h]
0x18002645a  neg     rax
0x18002645d  sbb     rbx, rbx
0x180026460  and     rbx, rcx
0x180026463  mov     [rbp+arg_0], rbx
0x180026467  jz      loc_1800266DA
0x18002646d  mov     rax, [rbx+80h]
0x180026474  xor     r13d, r13d
0x180026477  mov     cs:stru_1801FC158.m_pHead, rax
0x18002647e  mov     rcx, rbx
0x180026481  mov     rax, [rbx]
0x180026484  mov     edi, r13d
0x180026487  mov     rax, [rax+8]
0x18002648b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026490  lea     rax, stru_1801FC158
0x180026497  mov     [rbx+88h], rax
0x18002649e  mov     [rbx+3Ch], r12d
0x1800264a2  lea     r12, [rbx+70h]
0x1800264a6  mov     rcx, [r12]
0x1800264aa  mov     [rbx+50h], r14d
0x1800264ae  movdqu  xmmword ptr [rbx+40h], xmm6
0x1800264b3  test    rcx, rcx
0x1800264b6  jnz     loc_180026745
0x1800264bc  test    r14d, r14d
0x1800264bf  js      loc_180026797
0x1800264c5  lea     rcx, [rbx+58h]; pvar
0x1800264c9  call    cs:__imp_PropVariantClear
0x1800264cf  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x1800264d3  test    rdx, rdx
0x1800264d6  jz      short loc_1800264E2
0x1800264d8  lea     rcx, [rbx+58h]; pvarDest
0x1800264dc  call    cs:__imp_PropVariantCopy
0x1800264e2  lea     rcx, stru_1801FC158.m_csPool; lpCriticalSection
0x1800264e9  call    cs:__imp_LeaveCriticalSection
0x1800264ef  test    edi, edi
0x1800264f1  js      loc_1800266D3
0x1800264f7  mov     dword ptr [rbp+arg_0], r13d
0x1800264fb  mov     [rbp+var_38], r13d
0x1800264ff  test    rbx, rbx
0x180026502  jz      short loc_180026528
0x180026504  mov     rax, [rbx]
0x180026507  lea     rdx, [rbp+arg_0]
0x18002650b  mov     rcx, rbx
0x18002650e  mov     rax, [rax+108h]
0x180026515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002651a  test    eax, eax
0x18002651c  js      short loc_180026528
0x18002651e  cmp     dword ptr [rbp+arg_0], 1
0x180026522  jz      loc_180026850
0x180026528  lea     r14, [r15+8]
0x18002652c  mov     rcx, r14; lpCriticalSection
0x18002652f  call    cs:__imp_EnterCriticalSection
0x180026535  cmp     [r15+30h], r13d
0x180026539  jnz     loc_180026606
0x18002653f  cmp     cs:byte_1801FD28B, 10h
0x180026546  jnb     loc_180026A6F
0x18002654c  lea     rcx, stru_1801FC1A0.m_csPool; lpCriticalSection
0x180026553  call    cs:__imp_EnterCriticalSection
0x180026559  mov     rax, cs:stru_1801FC1A0.m_pHead
0x180026560  lea     rcx, [rax-68h]
0x180026564  neg     rax
0x180026567  sbb     rdi, rdi
0x18002656a  and     rdi, rcx
0x18002656d  mov     qword ptr [rbp+var_28.Data1], rdi
0x180026571  jz      loc_180026818
0x180026577  mov     rax, [rdi+70h]
0x18002657b  mov     rcx, rdi
0x18002657e  mov     cs:stru_1801FC1A0.m_pHead, rax
0x180026585  mov     esi, r13d
0x180026588  mov     rax, [rdi]
0x18002658b  mov     rax, [rax+8]
0x18002658f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026594  lea     rcx, stru_1801FC1A0
0x18002659b  mov     [rdi+78h], rcx
0x18002659f  mov     rcx, [rdi+90h]
0x1800265a6  test    rcx, rcx
0x1800265a9  jnz     loc_180026A7C
0x1800265af  mov     [rdi+90h], rbx
0x1800265b6  test    rbx, rbx
0x1800265b9  jz      short loc_1800265CA
0x1800265bb  mov     rax, [rbx]
0x1800265be  mov     rcx, rbx
0x1800265c1  mov     rax, [rax+8]
0x1800265c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265ca  lea     rcx, stru_1801FC1A0.m_csPool; lpCriticalSection
0x1800265d1  call    cs:__imp_LeaveCriticalSection
0x1800265d7  test    esi, esi
0x1800265d9  js      short loc_180026606
0x1800265db  lea     rdx, [rdi+80h]
0x1800265e2  lea     rcx, [r15+40h]
0x1800265e6  mov     rax, [rcx+8]
0x1800265ea  mov     [rdx], rcx
0x1800265ed  mov     [rdx+8], rax
0x1800265f1  mov     [rax], rdx
0x1800265f4  inc     dword ptr [r15+38h]
0x1800265f8  mov     [rcx+8], rdx
0x1800265fc  mov     rcx, r15; this
0x1800265ff  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x180026604  mov     esi, eax
0x180026606  mov     rcx, r14; lpCriticalSection
0x180026609  call    cs:__imp_LeaveCriticalSection
0x18002660f  test    rbx, rbx
0x180026612  jz      short loc_180026623
0x180026614  mov     rax, [rbx]
0x180026617  mov     rcx, rbx
0x18002661a  mov     rax, [rax+10h]
0x18002661e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026623  cmp     cs:byte_1801FD28B, 20h ; ' '
0x18002662a  jnb     loc_1800269C4
0x180026630  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026637  cmp     [rdi+8], r13b
0x18002663b  jz      short loc_1800266BB
0x18002663d  lea     rbx, [rdi+0D0h]
0x180026644  call    cs:__imp_GetLastError
0x18002664a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002664d  mov     r14d, eax
0x180026650  call    cs:__imp_TlsGetValue
0x180026656  test    rax, rax
0x180026659  jz      loc_1800268F6
0x18002665f  mov     rbx, rax
0x180026662  mov     ecx, r14d; dwErrCode
0x180026665  call    cs:__imp_SetLastError
0x18002666b  mov     eax, [rbx+7C4h]
0x180026671  test    eax, eax
0x180026673  jz      short loc_1800266BB
0x180026675  sub     eax, 1
0x180026678  mov     [rbx+7C4h], eax
0x18002667e  jnz     short loc_1800266BB
0x180026680  mov     [rbx+7C4h], r13d
0x180026687  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002668e  mov     qword ptr [rbx+7E0h], 0
0x180026699  mov     [rbx+7CCh], r13d
0x1800266a0  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800266a8  mov     [rbx+7E8h], r13d
0x1800266af  call    cs:__imp_GetCurrentThreadId
0x1800266b5  mov     [rbx+7C0h], eax
0x1800266bb  movaps  xmm6, [rsp+68h+var_18]
0x1800266c0  mov     eax, esi
0x1800266c2  add     rsp, 68h
0x1800266c6  pop     r15
0x1800266c8  pop     r14
0x1800266ca  pop     r13
0x1800266cc  pop     r12
0x1800266ce  pop     rdi
0x1800266cf  pop     rsi
0x1800266d0  pop     rbx
0x1800266d1  pop     rbp
0x1800266d2  retn
0x1800266d3  mov     esi, edi
0x1800266d5  jmp     loc_18002660F
0x1800266da  mov     r9, [rbp+pvarSrc]; struct tagPROPVARIANT *
0x1800266de  lea     rax, [rbp+arg_0]
0x1800266e2  mov     r8d, r14d; int
0x1800266e5  mov     [rsp+68h+var_48], rax; struct CMediaEventPooled **
0x1800266ea  lea     rdx, [rbp+var_28]; struct _GUID *
0x1800266ee  mov     ecx, r12d; unsigned int
0x1800266f1  call    ?CreateInstance@CMediaEventPooled@@SAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@PEAPEAV1@@Z; CMediaEventPooled::CreateInstance(ulong,_GUID const &,long,tagPROPVARIANT const *,CMediaEventPooled * *)
0x1800266f6  xor     r13d, r13d
0x1800266f9  mov     edi, eax
0x1800266fb  test    eax, eax
0x1800266fd  js      loc_18002678A
0x180026703  mov     rbx, [rbp+arg_0]
0x180026707  test    rbx, rbx
0x18002670a  jz      short loc_18002678A
0x18002670c  mov     ecx, cs:stru_1801FC158.m_dwMaxSize
0x180026712  cmp     cs:stru_1801FC158.m_dwCount, ecx
0x180026718  jnb     loc_1800264E2
0x18002671e  mov     ecx, cs:stru_1801FC158.m_fEnabled
0x180026724  test    ecx, ecx
0x180026726  jz      loc_1800264E2
0x18002672c  lea     rax, stru_1801FC158
0x180026733  mov     [rbx+88h], rax
0x18002673a  inc     cs:stru_1801FC158.m_dwCount
0x180026740  jmp     loc_1800264E2
0x180026745  mov     rax, [rcx]
0x180026748  mov     rax, [rax+10h]
0x18002674c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026751  mov     [r12], r13
0x180026755  jmp     loc_1800264BC
0x18002675a  mov     rax, cs:stru_1801FC290.__vftable
0x180026761  mov     edx, 7F0h
0x180026766  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002676d  mov     rax, [rax+8]
0x180026771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026776  test    eax, eax
0x180026778  jnz     loc_1800263B2
0x18002677e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026785  jmp     loc_1800263B2
0x18002678a  mov     rbx, r13
0x18002678d  mov     edi, 8007000Eh
0x180026792  jmp     loc_1800264E2
0x180026797  cmp     r14d, 800705AFh
0x18002679e  jz      loc_1800264C5
0x1800267a4  cmp     r14d, 0C00D36FCh
0x1800267ab  jz      loc_1800264C5
0x1800267b1  cmp     r14d, esi
0x1800267b4  jz      loc_1800264C5
0x1800267ba  cmp     r14d, 8007000Eh
0x1800267c1  jz      loc_1800264C5
0x1800267c7  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x1800267ce  mov     rdx, r12
0x1800267d1  mov     rax, [rcx]
0x1800267d4  mov     rax, [rax+8]
0x1800267d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267dd  cmp     [r12], r13
0x1800267e1  jnz     loc_1800264C5
0x1800267e7  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x1800267ee  mov     edx, r14d
0x1800267f1  mov     rax, [rcx]
0x1800267f4  mov     rax, [rax+10h]
0x1800267f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267fd  mov     rcx, cs:?s_pErrorInfoHandler@@3PEAUBaseErrorInfoHandler@@EA; BaseErrorInfoHandler * s_pErrorInfoHandler
0x180026804  mov     rdx, r12
0x180026807  mov     rax, [rcx]
0x18002680a  mov     rax, [rax+8]
0x18002680e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026813  jmp     loc_1800264C5
0x180026818  lea     rdx, [rbp+var_28]; struct CEventResult **
0x18002681c  mov     rcx, rbx; struct IMFMediaEvent *
0x18002681f  call    ?CreateInstance@CEventResult@@SAJPEAUIMFMediaEvent@@PEAPEAV1@@Z; CEventResult::CreateInstance(IMFMediaEvent *,CEventResult * *)
0x180026824  mov     esi, eax
0x180026826  test    eax, eax
0x180026828  js      loc_18002692B
0x18002682e  mov     rdi, qword ptr [rbp+var_28.Data1]
0x180026832  test    rdi, rdi
0x180026835  jz      loc_18002692B
0x18002683b  lea     rdx, [rdi+68h]; struct CPooledObject *
0x18002683f  lea     rcx, stru_1801FC1A0; this
0x180026846  call    ?TrackObject@CObjectPool@@QEAAXPEAVCPooledObject@@@Z; CObjectPool::TrackObject(CPooledObject *)
0x18002684b  jmp     loc_1800265CA
0x180026850  mov     rax, [rbx]
0x180026853  lea     rdx, [rbp+var_38]
0x180026857  mov     rcx, rbx
0x18002685a  mov     rax, [rax+118h]
0x180026861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026866  test    eax, eax
0x180026868  js      loc_180026528
0x18002686e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180026875  test    rcx, rcx
0x180026878  jz      loc_180026938
0x18002687e  cmp     [rcx+8], r13b
0x180026882  jz      loc_180026528
0x180026888  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002688d  mov     r9d, [rbp+var_38]; int
0x180026891  test    r9d, r9d
0x180026894  jns     loc_180026528
0x18002689a  cmp     [rax+7CCh], r9d
0x1800268a1  jz      loc_180026528
0x1800268a7  mov     r8d, 1CAh; int
  ... truncated ...
```
