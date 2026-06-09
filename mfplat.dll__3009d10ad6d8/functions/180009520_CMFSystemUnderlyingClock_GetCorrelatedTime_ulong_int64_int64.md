# CMFSystemUnderlyingClock::GetCorrelatedTime(ulong,__int64 *,__int64 *)

- ea: `0x180009520`
- end: `0x180009a86`
- name: `?GetCorrelatedTime@CMFSystemUnderlyingClock@@UEAAJKPEA_J0@Z`
- size: `1382`
- prototype: `__int64 __fastcall(CMFSystemUnderlyingClock *__hidden this, unsigned int, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180009520`
- `0x180009af0`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180127fdc`
- `0x1801282d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009609`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009609`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000957c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000969c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009731`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000957c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000969c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009789`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009745`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000984b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000984b`

## pseudocode

```c
__int64 __fastcall CMFSystemUnderlyingClock::GetCorrelatedTime(
        CMFSystemUnderlyingClock *this,
        int a2,
        __int64 *a3,
        __int64 *a4)
{
  CallStackTracing *v4; // rdi
  CallStackContext *p_m_context; // rbx
  DWORD LastError; // ebp
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v13; // rax
  int v14; // ebp
  LONGLONG v15; // rdi
  __int64 v16; // r8
  __int64 v17; // rbx
  CallStackTracing *v18; // rdi
  CallStackContext *v19; // rbx
  DWORD v20; // r14d
  CallStackContext *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  CallStackContext *v25; // rbx
  DWORD v26; // esi
  CallStackContext *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  CallStackTracing *v30; // rcx
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v34; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  CallStackScopeTrace v36; // [rsp+88h] [rbp+10h] BYREF

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
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v30 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      Value = (CallStackContext *)v30->AllocateNewContext(v30);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    v4 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v13 = m_dwDepth;
      p_m_context->m_rgInfo[v13].m_pszFunction = "CMFSystemUnderlyingClock::GetCorrelatedTime";
      p_m_context->m_rgInfo[v13].m_lineNumber = 983;
    }
    ++p_m_context->m_dwDepth;
  }
  if ( a2 )
  {
    if ( v4->m_fEnabled )
    {
      v25 = &v4->m_context;
      v26 = GetLastError();
      v27 = (CallStackContext *)TlsGetValue(v4->m_dwTLSIndex);
      if ( v27 )
        goto LABEL_27;
      if ( !GetLastError() )
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v32 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        v27 = (CallStackContext *)v32->AllocateNewContext(v32);
        if ( v27 )
LABEL_27:
          v25 = v27;
      }
      SetLastError(v26);
      v28 = v25->m_dwDepth;
      if ( v28 )
      {
        v29 = v28 - 1;
        v25->m_dwDepth = v29;
        if ( !v29 )
        {
          v25->m_dwDepth = 0;
          *(_QWORD *)&v25->m_instanceId = 0;
          v25->m_result = 0;
          v25->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
          v25->m_dwErrorsInContext = 0;
          v25->m_dwThreadID = GetCurrentThreadId();
        }
      }
    }
    return 3222117440LL;
  }
  else if ( a3 && a4 )
  {
    v14 = 0;
    if ( *((_DWORD *)this + 14)
      && (v34 = *(_QWORD *)this,
          *((_DWORD *)this + 14) = 0,
          v14 = (*(__int64 (__fastcall **)(CMFSystemUnderlyingClock *))(v34 + 64))(this),
          v14 < 0) )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( ThreadRelativeContext->m_result != v14 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFSystemUnderlyingClock::GetCorrelatedTime",
            1006,
            v14);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_00c2d7c8d70c351f27a565e25347ab72_Traceguids, this, v14);
    }
    else
    {
      PerformanceCount.QuadPart = 0;
      v15 = 0;
      if ( QueryPerformanceCounter(&PerformanceCount) )
        v15 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
      v17 = *((_QWORD *)this + 3)
          + (unsigned int)(int)((double)((int)v15 - *((_DWORD *)this + 8)) * *((double *)this + 5));
      if ( v17 < *((_QWORD *)this + 6) )
      {
        if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
          WPP_SF_qii(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, v16, this, v17, *((_QWORD *)this + 6));
        v17 = *((_QWORD *)this + 6);
      }
      if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
        WPP_SF_sqii(*((_QWORD *)WPP_GLOBAL_Control + 7));
      *((_QWORD *)this + 6) = v17;
      *a3 = v17;
      *a4 = v15;
    }
    v18 = CallStackTracing::s_wpInstance;
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v19 = &CallStackTracing::s_wpInstance->m_context;
      v20 = GetLastError();
      v21 = (CallStackContext *)TlsGetValue(v18->m_dwTLSIndex);
      if ( v21 )
        goto LABEL_20;
      if ( !GetLastError() )
      {
        v31 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v31 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        v21 = (CallStackContext *)v31->AllocateNewContext(v31);
        if ( v21 )
LABEL_20:
          v19 = v21;
      }
      SetLastError(v20);
      v22 = v19->m_dwDepth;
      if ( v22 )
      {
        v23 = v22 - 1;
        v19->m_dwDepth = v23;
        if ( !v23 )
        {
          v19->m_dwDepth = 0;
          *(_QWORD *)&v19->m_instanceId = 0;
          v19->m_result = 0;
          v19->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
          v19->m_dwErrorsInContext = 0;
          v19->m_dwThreadID = GetCurrentThreadId();
        }
      }
    }
    return (unsigned int)v14;
  }
  else
  {
    CallStackScopeTrace::~CallStackScopeTrace(&v36);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180009520  mov     [rsp+arg_10], rbx
0x180009525  push    rbp
0x180009526  push    rsi
0x180009527  push    rdi
0x180009528  push    r12
0x18000952a  push    r13
0x18000952c  push    r14
0x18000952e  push    r15
0x180009530  sub     rsp, 40h
0x180009534  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000953b  lea     rbp, stru_1801F8A30
0x180009542  lea     rbx, stru_1801FC290
0x180009549  mov     r15, r9
0x18000954c  mov     r12, r8
0x18000954f  mov     esi, edx
0x180009551  mov     r14, rcx
0x180009554  test    rdi, rdi
0x180009557  jz      loc_18000979F
0x18000955d  cmp     byte ptr [rdi+8], 0
0x180009561  lea     r13, aCmfsystemunder_2; "CMFSystemUnderlyingClock::GetCorrelated"...
0x180009568  jz      short loc_1800095CE
0x18000956a  lea     rbx, [rdi+0D0h]
0x180009571  call    cs:__imp_GetLastError
0x180009577  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18000957a  mov     ebp, eax
0x18000957c  call    cs:__imp_TlsGetValue
0x180009582  test    rax, rax
0x180009585  jz      loc_1800097DD
0x18000958b  mov     rbx, rax
0x18000958e  mov     ecx, ebp; dwErrCode
0x180009590  call    cs:__imp_SetLastError
0x180009596  mov     eax, [rbx+7C4h]
0x18000959c  lea     rbp, stru_1801F8A30
0x1800095a3  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800095aa  cmp     eax, [rbx+7C8h]
0x1800095b0  jnb     short loc_1800095C1
0x1800095b2  add     rax, rax
0x1800095b5  mov     [rbx+rax*8], r13
0x1800095b9  mov     dword ptr [rbx+rax*8+8], 3D7h
0x1800095c1  inc     dword ptr [rbx+7C4h]
0x1800095c7  lea     rbx, stru_1801FC290
0x1800095ce  test    esi, esi
0x1800095d0  jnz     loc_180009719
0x1800095d6  test    r12, r12
0x1800095d9  jz      loc_180009882
0x1800095df  test    r15, r15
0x1800095e2  jz      loc_180009882
0x1800095e8  xor     esi, esi
0x1800095ea  mov     ebp, esi
0x1800095ec  cmp     [r14+38h], esi
0x1800095f0  jnz     loc_180009A0C
0x1800095f6  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x1800095fe  mov     qword ptr [rsp+78h+PerformanceCount], rsi
0x180009606  mov     rdi, rsi
0x180009609  call    cs:__imp_QueryPerformanceCounter
0x18000960f  test    eax, eax
0x180009611  jz      short loc_180009639
0x180009613  mov     rcx, qword ptr [rsp+78h+PerformanceCount]
0x18000961b  xor     r9d, r9d; d
0x18000961e  sub     rcx, cs:qword_1801FCD08; a
0x180009625  mov     edx, 989680h; b
0x18000962a  mov     r8, cs:c; c
0x180009631  call    MFllMulDiv
0x180009636  mov     rdi, rax
0x180009639  mov     rax, [r14+30h]
0x18000963d  xorps   xmm0, xmm0
0x180009640  mov     rcx, rdi
0x180009643  sub     rcx, [r14+20h]
0x180009647  cvtsi2sd xmm0, rcx
0x18000964c  mulsd   xmm0, qword ptr [r14+28h]
0x180009652  cvttsd2si rbx, xmm0
0x180009657  add     rbx, [r14+18h]
0x18000965b  cmp     rbx, rax
0x18000965e  jl      loc_180009A2E
0x180009664  cmp     cs:byte_1801FD289, 10h
0x18000966b  jnb     loc_180009A62
0x180009671  mov     [r14+30h], rbx
0x180009675  mov     [r12], rbx
0x180009679  mov     [r15], rdi
0x18000967c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009683  cmp     [rdi+8], sil
0x180009687  jz      short loc_1800096FF
0x180009689  lea     rbx, [rdi+0D0h]
0x180009690  call    cs:__imp_GetLastError
0x180009696  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180009699  mov     r14d, eax
0x18000969c  call    cs:__imp_TlsGetValue
0x1800096a2  test    rax, rax
0x1800096a5  jz      loc_180009814
0x1800096ab  mov     rbx, rax
0x1800096ae  mov     ecx, r14d; dwErrCode
0x1800096b1  call    cs:__imp_SetLastError
0x1800096b7  mov     eax, [rbx+7C4h]
0x1800096bd  test    eax, eax
0x1800096bf  jz      short loc_1800096FF
0x1800096c1  sub     eax, 1
0x1800096c4  mov     [rbx+7C4h], eax
0x1800096ca  jnz     short loc_1800096FF
0x1800096cc  mov     [rbx+7C4h], esi
0x1800096d2  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800096d9  mov     [rbx+7E0h], rsi
0x1800096e0  mov     [rbx+7CCh], esi
0x1800096e6  movups  xmmword ptr [rbx+7D0h], xmm0
0x1800096ed  mov     [rbx+7E8h], esi
0x1800096f3  call    cs:__imp_GetCurrentThreadId
0x1800096f9  mov     [rbx+7C0h], eax
0x1800096ff  mov     eax, ebp
0x180009701  mov     rbx, [rsp+78h+arg_10]
0x180009709  add     rsp, 40h
0x18000970d  pop     r15
0x18000970f  pop     r14
0x180009711  pop     r13
0x180009713  pop     r12
0x180009715  pop     rdi
0x180009716  pop     rsi
0x180009717  pop     rbp
0x180009718  retn
0x180009719  cmp     byte ptr [rdi+8], 0
0x18000971d  jz      short loc_180009795
0x18000971f  lea     rbx, [rdi+0D0h]
0x180009726  call    cs:__imp_GetLastError
0x18000972c  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18000972f  mov     esi, eax
0x180009731  call    cs:__imp_TlsGetValue
0x180009737  test    rax, rax
0x18000973a  jz      loc_18000984B
0x180009740  mov     rbx, rax
0x180009743  mov     ecx, esi; dwErrCode
0x180009745  call    cs:__imp_SetLastError
0x18000974b  mov     eax, [rbx+7C4h]
0x180009751  test    eax, eax
0x180009753  jz      short loc_180009795
0x180009755  sub     eax, 1
0x180009758  mov     [rbx+7C4h], eax
0x18000975e  jnz     short loc_180009795
0x180009760  xor     esi, esi
0x180009762  mov     [rbx+7C4h], esi
0x180009768  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000976f  mov     [rbx+7E0h], rsi
0x180009776  mov     [rbx+7CCh], esi
0x18000977c  movups  xmmword ptr [rbx+7D0h], xmm0
0x180009783  mov     [rbx+7E8h], esi
0x180009789  call    cs:__imp_GetCurrentThreadId
0x18000978f  mov     [rbx+7C0h], eax
0x180009795  mov     eax, 0C00D9C40h
0x18000979a  jmp     loc_180009701
0x18000979f  mov     rax, cs:stru_1801FC290.__vftable
0x1800097a6  mov     edx, 7F0h
0x1800097ab  mov     rcx, rbx
0x1800097ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097b5  mov     rax, [rax+8]
0x1800097b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097be  test    eax, eax
0x1800097c0  jz      short loc_1800097CE
0x1800097c2  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097c9  jmp     loc_18000955D
0x1800097ce  mov     rdi, rbp
0x1800097d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097d8  jmp     loc_18000955D
0x1800097dd  call    cs:__imp_GetLastError
0x1800097e3  test    eax, eax
0x1800097e5  jnz     loc_18000958E
0x1800097eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097f2  test    rcx, rcx
0x1800097f5  jz      loc_180009899
0x1800097fb  mov     rax, [rcx]
0x1800097fe  mov     rax, [rax]
0x180009801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009806  test    rax, rax
0x180009809  jnz     loc_18000958B
0x18000980f  jmp     loc_18000958E
0x180009814  call    cs:__imp_GetLastError
0x18000981a  test    eax, eax
0x18000981c  jnz     loc_1800096AE
0x180009822  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009829  test    rcx, rcx
0x18000982c  jz      loc_1800098E2
0x180009832  mov     rax, [rcx]
0x180009835  mov     rax, [rax]
0x180009838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983d  test    rax, rax
0x180009840  jnz     loc_1800096AB
0x180009846  jmp     loc_1800096AE
0x18000984b  call    cs:__imp_GetLastError
0x180009851  test    eax, eax
0x180009853  jnz     loc_180009743
0x180009859  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009860  test    rcx, rcx
0x180009863  jz      loc_180009928
0x180009869  mov     rax, [rcx]
0x18000986c  mov     rax, [rax]
0x18000986f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009874  test    rax, rax
0x180009877  jnz     loc_180009740
0x18000987d  jmp     loc_180009743
0x180009882  lea     rcx, [rsp+78h+arg_8]; this
0x18000988a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000988f  mov     eax, 80004003h
0x180009894  jmp     loc_180009701
0x180009899  mov     rax, cs:stru_1801FC290.__vftable
0x1800098a0  lea     rcx, stru_1801FC290
0x1800098a7  mov     edx, 7F0h
0x1800098ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098b3  mov     rax, [rax+8]
0x1800098b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098bc  test    eax, eax
0x1800098be  jnz     short loc_1800098D6
0x1800098c0  lea     rax, stru_1801F8A30
0x1800098c7  mov     rcx, rax
0x1800098ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098d1  jmp     loc_1800097FB
0x1800098d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098dd  jmp     loc_1800097FB
0x1800098e2  mov     rax, cs:stru_1801FC290.__vftable
0x1800098e9  lea     rcx, stru_1801FC290
0x1800098f0  mov     edx, 7F0h
0x1800098f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098fc  mov     rax, [rax+8]
0x180009900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009905  test    eax, eax
0x180009907  jnz     short loc_18000991C
0x180009909  lea     rcx, stru_1801F8A30
0x180009910  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009917  jmp     loc_180009832
0x18000991c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009923  jmp     loc_180009832
0x180009928  mov     rax, cs:stru_1801FC290.__vftable
0x18000992f  lea     rcx, stru_1801FC290
0x180009936  mov     edx, 7F0h
0x18000993b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009942  mov     rax, [rax+8]
0x180009946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000994b  test    eax, eax
0x18000994d  jnz     short loc_18000995E
0x18000994f  mov     rcx, rbp
0x180009952  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009959  jmp     loc_180009869
0x18000995e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009965  jmp     loc_180009869
0x18000996a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180009971  jnz     short loc_1800099A4
0x180009973  mov     rcx, cs:stru_1801FC290.__vftable
0x18000997a  mov     edx, 7F0h
0x18000997f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009986  mov     rax, [rcx+8]
0x18000998a  mov     rcx, rbx
0x18000998d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009992  test    eax, eax
0x180009994  jnz     short loc_1800099A4
0x180009996  lea     rax, stru_1801F8A30
0x18000999d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800099a4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800099ab  cmp     [rdi+8], sil
0x1800099af  jnz     short loc_1800099E6
0x1800099b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800099b8  jb      loc_18000967C
0x1800099be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099c5  lea     r8, WPP_00c2d7c8d70c351f27a565e25347ab72_Traceguids
0x1800099cc  mov     edx, 2Fh ; '/'
0x1800099d1  mov     dword ptr [rsp+78h+var_58], ebp
0x1800099d5  mov     r9, r14
0x1800099d8  mov     rcx, [rcx+10h]
0x1800099dc  call    WPP_SF_qD
0x1800099e1  jmp     loc_18000967C
0x1800099e6  mov     rcx, rdi; this
0x1800099e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800099ee  cmp     [rax+7CCh], ebp
0x1800099f4  jz      short loc_1800099B1
0x1800099f6  mov     r9d, ebp; int
0x1800099f9  mov     r8d, 3EEh; int
0x1800099ff  mov     rdx, r13; char *
0x180009a02  mov     rcx, rax; this
0x180009a05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009a0a  jmp     short loc_1800099B1
0x180009a0c  mov     rax, [r14]
0x180009a0f  mov     rcx, r14
0x180009a12  mov     [r14+38h], esi
0x180009a16  mov     rax, [rax+40h]
0x180009a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a1f  mov     ebp, eax
0x180009a21  test    eax, eax
0x180009a23  jns     loc_1800095F6
0x180009a29  jmp     loc_18000996A
0x180009a2e  cmp     cs:byte_1801FD289, 10h
0x180009a35  jb      short loc_180009A59
0x180009a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a3e  mov     edx, 30h ; '0'
0x180009a43  mov     [rsp+78h+var_50], rax
0x180009a48  mov     r9, r14
0x180009a4b  mov     [rsp+78h+var_58], rbx
0x180009a50  mov     rcx, [rcx+38h]
0x180009a54  call    WPP_SF_qii
0x180009a59  mov     rbx, [r14+30h]
0x180009a5d  jmp     loc_180009664
0x180009a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a69  mov     [rsp+78h+var_48], rbx
0x180009a6e  mov     [rsp+78h+var_50], rdi
0x180009a73  mov     [rsp+78h+var_58], r14
0x180009a78  mov     rcx, [rcx+38h]
0x180009a7c  call    WPP_SF_sqii
  ... truncated ...
```
