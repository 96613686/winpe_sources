# CMFDXGIDeviceManager::TestDevice(void *)

- ea: `0x180022310`
- end: `0x180022a8c`
- name: `?TestDevice@CMFDXGIDeviceManager@@UEAAJPEAX@Z`
- size: `1916`
- prototype: `__int64 __fastcall(CMFDXGIDeviceManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180022310`
- `0x180022aa0`
- `0x180024390`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002232b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002232b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225a0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022371`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022424`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800224a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022535`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022371`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022424`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800224a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180022535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800224bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002254a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800224bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002254a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002249a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002275a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002249a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002275a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022796`

## pseudocode

```c
__int64 __fastcall CMFDXGIDeviceManager::TestDevice(CMFDXGIDeviceManager *this, void *a2)
{
  CallStackTracing *v4; // rdi
  _QWORD *p_m_context; // rsi
  DWORD LastError; // ebp
  _QWORD *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ebp
  void ***i; // rax
  void **v12; // rbp
  CallStackTracing *v13; // rdi
  CallStackContext *v14; // rsi
  DWORD v15; // r14d
  CallStackContext *v16; // rax
  __int64 m_dwDepth; // rax
  __int64 v18; // rax
  CallStackTracing *v19; // rdi
  CallStackContext *v20; // rsi
  DWORD v21; // r14d
  CallStackContext *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  CallStackTracing *v25; // rdi
  CallStackContext *v26; // rsi
  DWORD v27; // r14d
  CallStackContext *v28; // rax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v32; // rdx
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  CallStackTracing *v37; // rcx
  __int64 v38; // rax
  CallStackTracing *v39; // rcx
  __int64 v40; // rax
  CallStackTracing *v41; // rcx
  __int64 v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v45; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
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
    Value = TlsGetValue(v4->m_dwTLSIndex);
    if ( Value )
    {
      p_m_context = Value;
    }
    else if ( !GetLastError() )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v36 = v35->AllocateNewContext(v35);
      if ( v36 )
        p_m_context = (_QWORD *)v36;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)p_m_context + 497);
    if ( (unsigned int)v8 < *((_DWORD *)p_m_context + 498) )
    {
      v9 = 2 * v8;
      p_m_context[v9] = "CMFDXGIDeviceManager::TestDevice";
      LODWORD(p_m_context[v9 + 1]) = 561;
    }
    ++*((_DWORD *)p_m_context + 497);
  }
  v10 = CMFDXGIDeviceManager::InternalCheckDeviceInitialized(this);
  if ( v10 >= 0 )
  {
    for ( i = (void ***)*((_QWORD *)this + 65); ; i = (void ***)i[1] )
    {
      v12 = 0;
      if ( !i )
        break;
      v12 = *i;
      if ( **i == a2 )
        break;
    }
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    v13 = CallStackTracing::s_wpInstance;
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v14 = &CallStackTracing::s_wpInstance->m_context;
      v15 = GetLastError();
      v16 = (CallStackContext *)TlsGetValue(v13->m_dwTLSIndex);
      if ( v16 )
      {
        v14 = v16;
      }
      else if ( !GetLastError() )
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
        v40 = v39->AllocateNewContext(v39);
        if ( v40 )
          v14 = (CallStackContext *)v40;
      }
      SetLastError(v15);
      m_dwDepth = v14->m_dwDepth;
      if ( (unsigned int)m_dwDepth < v14->m_dwMaxDepth )
      {
        v18 = m_dwDepth;
        v14->m_rgInfo[v18].m_pszFunction = "CMFDXGIDeviceManager::InternalTestDevice";
        v14->m_rgInfo[v18].m_lineNumber = 537;
      }
      ++v14->m_dwDepth;
    }
    if ( v12 )
    {
      if ( *((_DWORD *)v12 + 2) )
      {
        v10 = 0;
        goto LABEL_23;
      }
      v10 = -2147217407;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( ThreadRelativeContext->m_result != -2147217407 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFDXGIDeviceManager::InternalTestDevice",
            542,
            -2147217407);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v34 = 42;
        goto LABEL_97;
      }
    }
    else
    {
      v10 = -2147024890;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v33->m_result != -2147024890 )
          CallStackContext::TraceFailure(v33, "CMFDXGIDeviceManager::InternalTestDevice", 537, -2147024890);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v34 = 41;
LABEL_97:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids, this, v10);
      }
    }
LABEL_23:
    v19 = CallStackTracing::s_wpInstance;
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v20 = &CallStackTracing::s_wpInstance->m_context;
      v21 = GetLastError();
      v22 = (CallStackContext *)TlsGetValue(v19->m_dwTLSIndex);
      if ( v22 )
      {
        v20 = v22;
      }
      else if ( !GetLastError() )
      {
        v41 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v41 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        v42 = v41->AllocateNewContext(v41);
        if ( v42 )
          v20 = (CallStackContext *)v42;
      }
      SetLastError(v21);
      v23 = v20->m_dwDepth;
      if ( v23 )
      {
        v24 = v23 - 1;
        v20->m_dwDepth = v24;
        if ( !v24 )
        {
          v20->m_dwDepth = 0;
          *(_QWORD *)&v20->m_instanceId = 0;
          v20->m_result = 0;
          v20->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
          v20->m_dwErrorsInContext = 0;
          v20->m_dwThreadID = GetCurrentThreadId();
        }
      }
    }
    if ( v10 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v45->m_result != v10 )
          CallStackContext::TraceFailure(v45, "CMFDXGIDeviceManager::TestDevice", 562, v10);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v32 = 44;
        goto LABEL_106;
      }
    }
    goto LABEL_30;
  }
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v43 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( v43->m_result != v10 )
      CallStackContext::TraceFailure(v43, "CMFDXGIDeviceManager::TestDevice", 561, v10);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v32 = 43;
LABEL_106:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, &WPP_bc86c1f11e9132d36b686fc60142a3a8_Traceguids, this, v10);
  }
LABEL_30:
  v25 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v26 = &CallStackTracing::s_wpInstance->m_context;
    v27 = GetLastError();
    v28 = (CallStackContext *)TlsGetValue(v25->m_dwTLSIndex);
    if ( v28 )
    {
      v26 = v28;
    }
    else if ( !GetLastError() )
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
      v38 = v37->AllocateNewContext(v37);
      if ( v38 )
        v26 = (CallStackContext *)v38;
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
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022310  push    rbx
0x180022312  push    rbp
0x180022313  push    rsi
0x180022314  push    rdi
0x180022315  push    r12
0x180022317  push    r13
0x180022319  push    r14
0x18002231b  push    r15
0x18002231d  sub     rsp, 38h
0x180022321  mov     r15, rcx
0x180022324  mov     r14, rdx
0x180022327  add     rcx, 20h ; ' '; lpCriticalSection
0x18002232b  call    cs:__imp_EnterCriticalSection
0x180022331  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022338  lea     rsi, stru_1801F8A30
0x18002233f  xor     r12d, r12d
0x180022342  lea     r13, stru_1801FC290
0x180022349  test    rdi, rdi
0x18002234c  jz      loc_1800225EE
0x180022352  lea     rcx, aCmfdxgidevicem_41; "CMFDXGIDeviceManager::TestDevice"
0x180022359  cmp     [rdi+8], r12b
0x18002235d  jz      short loc_1800223BC
0x18002235f  lea     rsi, [rdi+0D0h]
0x180022366  call    cs:__imp_GetLastError
0x18002236c  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002236f  mov     ebp, eax
0x180022371  call    cs:__imp_TlsGetValue
0x180022377  test    rax, rax
0x18002237a  jz      loc_1800226F0
0x180022380  mov     rsi, rax
0x180022383  mov     ecx, ebp; dwErrCode
0x180022385  call    cs:__imp_SetLastError
0x18002238b  mov     eax, [rsi+7C4h]
0x180022391  lea     rcx, aCmfdxgidevicem_41; "CMFDXGIDeviceManager::TestDevice"
0x180022398  cmp     eax, [rsi+7C8h]
0x18002239e  jnb     short loc_1800223AF
0x1800223a0  add     rax, rax
0x1800223a3  mov     [rsi+rax*8], rcx
0x1800223a7  mov     dword ptr [rsi+rax*8+8], 231h
0x1800223af  inc     dword ptr [rsi+7C4h]
0x1800223b5  lea     rsi, stru_1801F8A30
0x1800223bc  mov     rcx, r15; this
0x1800223bf  call    ?InternalCheckDeviceInitialized@CMFDXGIDeviceManager@@IEAAJXZ; CMFDXGIDeviceManager::InternalCheckDeviceInitialized(void)
0x1800223c4  mov     ebp, eax
0x1800223c6  test    eax, eax
0x1800223c8  js      loc_1800225B9
0x1800223ce  mov     rax, [r15+208h]
0x1800223d5  jmp     short loc_1800223E4
0x1800223d7  mov     rbp, [rax]
0x1800223da  cmp     [rbp+0], r14
0x1800223de  jz      short loc_1800223EC
0x1800223e0  mov     rax, [rax+8]
0x1800223e4  mov     rbp, r12
0x1800223e7  test    rax, rax
0x1800223ea  jnz     short loc_1800223D7
0x1800223ec  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x1800223f3  jz      loc_180022621
0x1800223f9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022400  lea     r14, aCmfdxgidevicem_14; "CMFDXGIDeviceManager::InternalTestDevic"...
0x180022407  cmp     [rdi+8], r12b
0x18002240b  jz      loc_180022840
0x180022411  lea     rsi, [rdi+0D0h]
0x180022418  call    cs:__imp_GetLastError
0x18002241e  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180022421  mov     r14d, eax
0x180022424  call    cs:__imp_TlsGetValue
0x18002242a  test    rax, rax
0x18002242d  jz      loc_18002275A
0x180022433  mov     rsi, rax
0x180022436  lea     rdi, stru_1801F8A30
0x18002243d  mov     ecx, r14d; dwErrCode
0x180022440  call    cs:__imp_SetLastError
0x180022446  mov     eax, [rsi+7C4h]
0x18002244c  lea     r14, aCmfdxgidevicem_14; "CMFDXGIDeviceManager::InternalTestDevic"...
0x180022453  cmp     eax, [rsi+7C8h]
0x180022459  jnb     short loc_18002246A
0x18002245b  add     rax, rax
0x18002245e  mov     [rsi+rax*8], r14
0x180022462  mov     dword ptr [rsi+rax*8+8], 219h
0x18002246a  inc     dword ptr [rsi+7C4h]
0x180022470  test    rbp, rbp
0x180022473  jz      loc_180022654
0x180022479  cmp     [rbp+8], r12d
0x18002247d  jz      loc_180022946
0x180022483  mov     ebp, r12d
0x180022486  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002248d  cmp     [rdi+8], r12b
0x180022491  jz      short loc_18002250D
0x180022493  lea     rsi, [rdi+0D0h]
0x18002249a  call    cs:__imp_GetLastError
0x1800224a0  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800224a3  mov     r14d, eax
0x1800224a6  call    cs:__imp_TlsGetValue
0x1800224ac  test    rax, rax
0x1800224af  jz      loc_180022796
0x1800224b5  mov     rsi, rax
0x1800224b8  mov     ecx, r14d; dwErrCode
0x1800224bb  call    cs:__imp_SetLastError
0x1800224c1  mov     eax, [rsi+7C4h]
0x1800224c7  test    eax, eax
0x1800224c9  jz      short loc_18002250D
0x1800224cb  sub     eax, 1
0x1800224ce  mov     [rsi+7C4h], eax
0x1800224d4  jnz     short loc_18002250D
0x1800224d6  mov     [rsi+7C4h], r12d
0x1800224dd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800224e4  mov     [rsi+7E0h], r12
0x1800224eb  mov     [rsi+7CCh], r12d
0x1800224f2  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x1800224fa  mov     [rsi+7E8h], r12d
0x180022501  call    cs:__imp_GetCurrentThreadId
0x180022507  mov     [rsi+7C0h], eax
0x18002250d  test    ebp, ebp
0x18002250f  js      loc_1800229E6
0x180022515  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002251c  cmp     [rdi+8], r12b
0x180022520  jz      short loc_18002259C
0x180022522  lea     rsi, [rdi+0D0h]
0x180022529  call    cs:__imp_GetLastError
0x18002252f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180022532  mov     r14d, eax
0x180022535  call    cs:__imp_TlsGetValue
0x18002253b  test    rax, rax
0x18002253e  jz      loc_180022725
0x180022544  mov     rsi, rax
0x180022547  mov     ecx, r14d; dwErrCode
0x18002254a  call    cs:__imp_SetLastError
0x180022550  mov     eax, [rsi+7C4h]
0x180022556  test    eax, eax
0x180022558  jz      short loc_18002259C
0x18002255a  sub     eax, 1
0x18002255d  mov     [rsi+7C4h], eax
0x180022563  jnz     short loc_18002259C
0x180022565  mov     [rsi+7C4h], r12d
0x18002256c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180022573  mov     [rsi+7E0h], r12
0x18002257a  mov     [rsi+7CCh], r12d
0x180022581  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x180022589  mov     [rsi+7E8h], r12d
0x180022590  call    cs:__imp_GetCurrentThreadId
0x180022596  mov     [rsi+7C0h], eax
0x18002259c  lea     rcx, [r15+20h]; lpCriticalSection
0x1800225a0  call    cs:__imp_LeaveCriticalSection
0x1800225a6  mov     eax, ebp
0x1800225a8  add     rsp, 38h
0x1800225ac  pop     r15
0x1800225ae  pop     r14
0x1800225b0  pop     r13
0x1800225b2  pop     r12
0x1800225b4  pop     rdi
0x1800225b5  pop     rsi
0x1800225b6  pop     rbp
0x1800225b7  pop     rbx
0x1800225b8  retn
0x1800225b9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x1800225c0  jz      loc_1800226BD
0x1800225c6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800225cd  cmp     [rdi+8], r12b
0x1800225d1  jnz     loc_180022915
0x1800225d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800225de  jb      loc_180022515
0x1800225e4  mov     edx, 2Bh ; '+'
0x1800225e9  jmp     loc_180022A3F
0x1800225ee  mov     rax, cs:stru_1801FC290.__vftable
0x1800225f5  mov     edx, 7F0h
0x1800225fa  mov     rcx, r13
0x1800225fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180022604  mov     rax, [rax+8]
0x180022608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002260d  test    eax, eax
0x18002260f  jz      loc_1800226AE
0x180022615  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002261c  jmp     loc_180022352
0x180022621  mov     rax, cs:stru_1801FC290.__vftable
0x180022628  mov     edx, 7F0h
0x18002262d  mov     rcx, r13
0x180022630  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180022637  mov     rax, [rax+8]
0x18002263b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022640  test    eax, eax
0x180022642  jnz     loc_1800223F9
0x180022648  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002264f  jmp     loc_1800223F9
0x180022654  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18002265b  mov     ebp, 80070006h
0x180022660  jz      loc_1800227CB
0x180022666  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002266d  cmp     [rdi+8], r12b
0x180022671  jz      short loc_180022697
0x180022673  mov     rcx, rdi; this
0x180022676  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002267b  cmp     [rax+7CCh], ebp
0x180022681  jz      short loc_180022697
0x180022683  mov     r9d, ebp; int
0x180022686  mov     r8d, 219h; int
0x18002268c  mov     rdx, r14; char *
0x18002268f  mov     rcx, rax; this
0x180022692  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022697  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002269e  jb      loc_180022486
0x1800226a4  mov     edx, 29h ; ')'
0x1800226a9  jmp     loc_18002299D
0x1800226ae  mov     rdi, rsi
0x1800226b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800226b8  jmp     loc_180022352
0x1800226bd  mov     rcx, cs:stru_1801FC290.__vftable
0x1800226c4  mov     edx, 7F0h
0x1800226c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800226d0  mov     rax, [rcx+8]
0x1800226d4  mov     rcx, r13
0x1800226d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226dc  test    eax, eax
0x1800226de  jnz     loc_1800225C6
0x1800226e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800226eb  jmp     loc_1800225C6
0x1800226f0  call    cs:__imp_GetLastError
0x1800226f6  test    eax, eax
0x1800226f8  jnz     loc_180022383
0x1800226fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022705  test    rcx, rcx
0x180022708  jz      loc_1800227FE
0x18002270e  mov     rax, [rcx]
0x180022711  mov     rax, [rax]
0x180022714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022719  test    rax, rax
0x18002271c  cmovnz  rsi, rax
0x180022720  jmp     loc_180022383
0x180022725  call    cs:__imp_GetLastError
0x18002272b  test    eax, eax
0x18002272d  jnz     loc_180022547
0x180022733  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002273a  test    rcx, rcx
0x18002273d  jz      loc_1800228BB
0x180022743  mov     rax, [rcx]
0x180022746  mov     rax, [rax]
0x180022749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002274e  test    rax, rax
0x180022751  cmovnz  rsi, rax
0x180022755  jmp     loc_180022547
0x18002275a  call    cs:__imp_GetLastError
0x180022760  test    eax, eax
0x180022762  jnz     loc_180022436
0x180022768  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002276f  test    rcx, rcx
0x180022772  jz      loc_18002284C
0x180022778  lea     rdi, stru_1801F8A30
0x18002277f  mov     rax, [rcx]
0x180022782  mov     rax, [rax]
0x180022785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002278a  test    rax, rax
0x18002278d  cmovnz  rsi, rax
0x180022791  jmp     loc_18002243D
0x180022796  call    cs:__imp_GetLastError
0x18002279c  test    eax, eax
0x18002279e  jnz     loc_1800224B8
0x1800227a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800227ab  test    rcx, rcx
0x1800227ae  jz      loc_180022885
0x1800227b4  mov     rax, [rcx]
0x1800227b7  mov     rax, [rax]
0x1800227ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227bf  test    rax, rax
0x1800227c2  cmovnz  rsi, rax
0x1800227c6  jmp     loc_1800224B8
0x1800227cb  mov     rax, cs:stru_1801FC290.__vftable
0x1800227d2  mov     edx, 7F0h
0x1800227d7  mov     rcx, r13
0x1800227da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800227e1  mov     rax, [rax+8]
0x1800227e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ea  test    eax, eax
0x1800227ec  jnz     loc_180022666
0x1800227f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800227f9  jmp     loc_180022666
0x1800227fe  mov     rax, cs:stru_1801FC290.__vftable
0x180022805  mov     edx, 7F0h
0x18002280a  mov     rcx, r13
0x18002280d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180022814  mov     rax, [rax+8]
0x180022818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002281d  test    eax, eax
0x18002281f  jnz     short loc_180022834
0x180022821  lea     rcx, stru_1801F8A30
0x180022828  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002282f  jmp     loc_18002270E
0x180022834  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002283b  jmp     loc_18002270E
0x180022840  lea     rdi, stru_1801F8A30
0x180022847  jmp     loc_180022470
0x18002284c  mov     rax, cs:stru_1801FC290.__vftable
0x180022853  mov     edx, 7F0h
0x180022858  mov     rcx, r13
0x18002285b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180022862  mov     rax, [rax+8]
0x180022866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002286b  lea     rdi, stru_1801F8A30
0x180022872  test    eax, eax
0x180022874  jnz     short loc_1800228F1
0x180022876  mov     rcx, rdi
0x180022879  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
