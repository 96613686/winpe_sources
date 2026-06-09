# CMFSystemTimeSource::GetCorrelatedTime(ulong,__int64 *,__int64 *)

- ea: `0x18003bdc0`
- end: `0x18003c257`
- name: `?GetCorrelatedTime@CMFSystemTimeSource@@UEAAJKPEA_J0@Z`
- size: `1175`
- prototype: `__int64 __fastcall(CMFSystemTimeSource *__hidden this, unsigned int, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180009af0`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x18003b450`
- `0x18003bdc0`
- `0x18012810c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bf31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bf31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c1f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c1f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c20c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c122`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c122`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003be5e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003be5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c1bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bed2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be6e`

## pseudocode

```c
__int64 __fastcall CMFSystemTimeSource::GetCorrelatedTime(
        CMFSystemTimeSource *this,
        unsigned int a2,
        __int64 *a3,
        __int64 *a4)
{
  CallStackTracing *v4; // rbx
  _QWORD *p_m_context; // rdi
  DWORD LastError; // ebp
  _QWORD *Value; // rax
  CallStackTracing *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  bool v16; // zf
  int TimeIfStalling; // edi
  CallStackTracing *v18; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  LONGLONG v23; // rbp
  int v24; // eax
  __int64 v26; // [rsp+40h] [rbp-38h] BYREF
  LONGLONG v27; // [rsp+48h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+18h] BYREF

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
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v13 = v12->AllocateNewContext(v12);
      if ( v13 )
        p_m_context = (_QWORD *)v13;
    }
    SetLastError(LastError);
    v14 = *((unsigned int *)p_m_context + 497);
    if ( (unsigned int)v14 < *((_DWORD *)p_m_context + 498) )
    {
      v15 = 2 * v14;
      p_m_context[v15] = "CMFSystemTimeSource::GetCorrelatedTime";
      LODWORD(p_m_context[v15 + 1]) = 214;
    }
    ++*((_DWORD *)p_m_context + 497);
  }
  if ( !a3 || !a4 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&PerformanceCount);
    return 2147500035LL;
  }
  if ( *((_DWORD *)this + 14) == GetCurrentThreadId() )
    ++*((_DWORD *)this + 15);
  else
    AcquireSRWLockShared((PSRWLOCK)this + 6);
  v16 = *((_DWORD *)this + 18) == 1;
  v26 = 0;
  v27 = 0;
  PerformanceCount.LowPart = 0;
  if ( !v16 )
  {
    *a3 = *((_QWORD *)this + 11);
    TimeIfStalling = 0;
    v23 = 0;
    PerformanceCount.QuadPart = 0;
    if ( QueryPerformanceCounter(&PerformanceCount) )
      v23 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
    goto LABEL_49;
  }
  TimeIfStalling = CMFSystemTimeSource::GetTimeIfStalling(this, a3, a4, (int *)&PerformanceCount);
  if ( TimeIfStalling < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v18 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v18->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v18);
      if ( ThreadRelativeContext->m_result != TimeIfStalling )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFSystemTimeSource::GetCorrelatedTime",
          233,
          TimeIfStalling);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_51;
    v20 = 11;
    goto LABEL_34;
  }
  if ( !PerformanceCount.LowPart )
  {
    TimeIfStalling = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, LONGLONG *))(**((_QWORD **)this + 8) + 32LL))(
                       *((_QWORD *)this + 8),
                       a2,
                       &v26,
                       &v27);
    if ( TimeIfStalling < 0 )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v21->m_fEnabled )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( v22->m_result != TimeIfStalling )
          CallStackContext::TraceFailure(v22, "CMFSystemTimeSource::GetCorrelatedTime", 255, TimeIfStalling);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_51;
      v20 = 12;
LABEL_34:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        &WPP_00c2d7c8d70c351f27a565e25347ab72_Traceguids,
        this,
        TimeIfStalling);
      goto LABEL_51;
    }
    v23 = v27;
    *a3 = (unsigned int)(int)((double)((int)v26 - *((_DWORD *)this + 20)) * *((float *)this + 24));
LABEL_49:
    *a4 = v23;
    if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
      WPP_SF_qiid(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        13,
        v23 / 10000,
        this,
        *a3 / 10000,
        v23 / 10000,
        *((_DWORD *)this + 18));
  }
LABEL_51:
  if ( *((_DWORD *)this + 14) == GetCurrentThreadId() )
  {
    v24 = *((_DWORD *)this + 15);
    if ( v24 )
    {
      *((_DWORD *)this + 15) = v24 - 1;
    }
    else
    {
      *((_DWORD *)this + 14) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&PerformanceCount);
    return (unsigned int)TimeIfStalling;
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)this + 6);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&PerformanceCount);
    return (unsigned int)TimeIfStalling;
  }
}

```

## disassembly

```asm
0x18003bdc0  mov     [rsp+arg_8], rbx
0x18003bdc5  mov     [rsp+arg_18], rbp
0x18003bdca  push    rsi
0x18003bdcb  push    r12
0x18003bdcd  push    r13
0x18003bdcf  push    r14
0x18003bdd1  push    r15
0x18003bdd3  sub     rsp, 50h
0x18003bdd7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bdde  lea     r13, stru_1801F8A30
0x18003bde5  lea     rbp, stru_1801FC290
0x18003bdec  mov     r14, r9
0x18003bdef  mov     r15, r8
0x18003bdf2  mov     r12d, edx
0x18003bdf5  mov     rsi, rcx
0x18003bdf8  test    rbx, rbx
0x18003bdfb  jnz     short loc_18003BE33
0x18003bdfd  mov     rax, cs:stru_1801FC290.__vftable
0x18003be04  mov     edx, 7F0h
0x18003be09  mov     rcx, rbp
0x18003be0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be13  mov     rax, [rax+8]
0x18003be17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be1c  test    eax, eax
0x18003be1e  jnz     short loc_18003BE2C
0x18003be20  mov     rbx, r13
0x18003be23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be2a  jmp     short loc_18003BE33
0x18003be2c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be33  cmp     byte ptr [rbx+8], 0
0x18003be37  lea     rcx, aCmfsystemtimes; "CMFSystemTimeSource::GetCorrelatedTime"
0x18003be3e  mov     [rsp+78h+arg_0], rdi
0x18003be46  jz      loc_18003BF09
0x18003be4c  lea     rdi, [rbx+0D0h]
0x18003be53  call    cs:__imp_GetLastError
0x18003be59  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003be5c  mov     ebp, eax
0x18003be5e  call    cs:__imp_TlsGetValue
0x18003be64  test    rax, rax
0x18003be67  jz      short loc_18003BE6E
0x18003be69  mov     rdi, rax
0x18003be6c  jmp     short loc_18003BED0
0x18003be6e  call    cs:__imp_GetLastError
0x18003be74  test    eax, eax
0x18003be76  jnz     short loc_18003BED0
0x18003be78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be7f  test    rcx, rcx
0x18003be82  jnz     short loc_18003BEBE
0x18003be84  mov     rax, cs:stru_1801FC290.__vftable
0x18003be8b  lea     rcx, stru_1801FC290
0x18003be92  mov     edx, 7F0h
0x18003be97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be9e  mov     rax, [rax+8]
0x18003bea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bea7  test    eax, eax
0x18003bea9  jnz     short loc_18003BEB7
0x18003beab  mov     rcx, r13
0x18003beae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003beb5  jmp     short loc_18003BEBE
0x18003beb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bebe  mov     rax, [rcx]
0x18003bec1  mov     rax, [rax]
0x18003bec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bec9  test    rax, rax
0x18003becc  cmovnz  rdi, rax
0x18003bed0  mov     ecx, ebp; dwErrCode
0x18003bed2  call    cs:__imp_SetLastError
0x18003bed8  mov     eax, [rdi+7C4h]
0x18003bede  lea     rbp, stru_1801FC290
0x18003bee5  lea     rcx, aCmfsystemtimes; "CMFSystemTimeSource::GetCorrelatedTime"
0x18003beec  cmp     eax, [rdi+7C8h]
0x18003bef2  jnb     short loc_18003BF03
0x18003bef4  add     rax, rax
0x18003bef7  mov     [rdi+rax*8], rcx
0x18003befb  mov     dword ptr [rdi+rax*8+8], 0D6h
0x18003bf03  inc     dword ptr [rdi+7C4h]
0x18003bf09  test    r15, r15
0x18003bf0c  jz      loc_18003C223
0x18003bf12  test    r14, r14
0x18003bf15  jz      loc_18003C223
0x18003bf1b  call    cs:__imp_GetCurrentThreadId
0x18003bf21  mov     ecx, [rsi+38h]
0x18003bf24  cmp     ecx, eax
0x18003bf26  jnz     short loc_18003BF2D
0x18003bf28  inc     dword ptr [rsi+3Ch]
0x18003bf2b  jmp     short loc_18003BF37
0x18003bf2d  lea     rcx, [rsi+30h]; SRWLock
0x18003bf31  call    cs:__imp_AcquireSRWLockShared
0x18003bf37  xor     r13d, r13d
0x18003bf3a  cmp     dword ptr [rsi+48h], 1
0x18003bf3e  mov     [rsp+78h+var_38], r13
0x18003bf43  mov     [rsp+78h+var_30], r13
0x18003bf48  mov     dword ptr [rsp+78h+PerformanceCount], r13d
0x18003bf50  jnz     loc_18003C105
0x18003bf56  lea     r9, [rsp+78h+PerformanceCount]; int *
0x18003bf5e  mov     r8, r14; __int64 *
0x18003bf61  mov     rdx, r15; __int64 *
0x18003bf64  mov     rcx, rsi; this
0x18003bf67  call    ?GetTimeIfStalling@CMFSystemTimeSource@@IEAAJPEA_J0PEAH@Z; CMFSystemTimeSource::GetTimeIfStalling(__int64 *,__int64 *,int *)
0x18003bf6c  mov     edi, eax
0x18003bf6e  test    eax, eax
0x18003bf70  jns     loc_18003C01C
0x18003bf76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bf7d  test    rcx, rcx
0x18003bf80  jnz     short loc_18003BFBC
0x18003bf82  mov     r8, cs:stru_1801FC290.__vftable
0x18003bf89  mov     edx, 7F0h
0x18003bf8e  mov     rcx, rbp
0x18003bf91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bf98  mov     rax, [r8+8]
0x18003bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfa1  test    eax, eax
0x18003bfa3  jnz     short loc_18003BFB5
0x18003bfa5  lea     rcx, stru_1801F8A30
0x18003bfac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bfb3  jmp     short loc_18003BFBC
0x18003bfb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003bfbc  cmp     [rcx+8], r13b
0x18003bfc0  jz      short loc_18003BFE7
0x18003bfc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bfc7  cmp     [rax+7CCh], edi
0x18003bfcd  jz      short loc_18003BFE7
0x18003bfcf  mov     r9d, edi; int
0x18003bfd2  lea     rdx, aCmfsystemtimes; "CMFSystemTimeSource::GetCorrelatedTime"
0x18003bfd9  mov     r8d, 0E9h; int
0x18003bfdf  mov     rcx, rax; this
0x18003bfe2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bfe7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bfee  jb      loc_18003C1BF
0x18003bff4  mov     edx, 0Bh
0x18003bff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c000  lea     r8, WPP_00c2d7c8d70c351f27a565e25347ab72_Traceguids
0x18003c007  mov     r9, rsi
0x18003c00a  mov     dword ptr [rsp+78h+var_58], edi
0x18003c00e  mov     rcx, [rcx+10h]
0x18003c012  call    WPP_SF_qD
0x18003c017  jmp     loc_18003C1BF
0x18003c01c  cmp     dword ptr [rsp+78h+PerformanceCount], r13d
0x18003c024  jnz     loc_18003C1BF
0x18003c02a  mov     rcx, [rsi+40h]
0x18003c02e  lea     r9, [rsp+78h+var_30]
0x18003c033  lea     r8, [rsp+78h+var_38]
0x18003c038  mov     edx, r12d
0x18003c03b  mov     rax, [rcx]
0x18003c03e  mov     rax, [rax+20h]
0x18003c042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c047  mov     edi, eax
0x18003c049  test    eax, eax
0x18003c04b  jns     loc_18003C0D9
0x18003c051  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c058  test    rcx, rcx
0x18003c05b  jnz     short loc_18003C097
0x18003c05d  mov     rax, cs:stru_1801FC290.__vftable
0x18003c064  mov     edx, 7F0h
0x18003c069  mov     rcx, rbp
0x18003c06c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c073  mov     rax, [rax+8]
0x18003c077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c07c  test    eax, eax
0x18003c07e  jnz     short loc_18003C090
0x18003c080  lea     rcx, stru_1801F8A30
0x18003c087  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c08e  jmp     short loc_18003C097
0x18003c090  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003c097  cmp     [rcx+8], r13b
0x18003c09b  jz      short loc_18003C0C2
0x18003c09d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c0a2  cmp     [rax+7CCh], edi
0x18003c0a8  jz      short loc_18003C0C2
0x18003c0aa  mov     r9d, edi; int
0x18003c0ad  lea     rdx, aCmfsystemtimes; "CMFSystemTimeSource::GetCorrelatedTime"
0x18003c0b4  mov     r8d, 0FFh; int
0x18003c0ba  mov     rcx, rax; this
0x18003c0bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c0c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c0c9  jb      loc_18003C1BF
0x18003c0cf  mov     edx, 0Ch
0x18003c0d4  jmp     loc_18003BFF9
0x18003c0d9  movss   xmm0, dword ptr [rsi+60h]
0x18003c0de  xorps   xmm1, xmm1
0x18003c0e1  mov     rax, [rsp+78h+var_38]
0x18003c0e6  sub     rax, [rsi+50h]
0x18003c0ea  mov     rbp, [rsp+78h+var_30]
0x18003c0ef  cvtps2pd xmm0, xmm0
0x18003c0f2  cvtsi2sd xmm1, rax
0x18003c0f7  mulsd   xmm1, xmm0
0x18003c0fb  cvttsd2si rax, xmm1
0x18003c100  mov     [r15], rax
0x18003c103  jmp     short loc_18003C152
0x18003c105  mov     rax, [rsi+58h]
0x18003c109  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x18003c111  mov     [r15], rax
0x18003c114  mov     edi, r13d
0x18003c117  mov     rbp, r13
0x18003c11a  mov     qword ptr [rsp+78h+PerformanceCount], r13
0x18003c122  call    cs:__imp_QueryPerformanceCounter
0x18003c128  test    eax, eax
0x18003c12a  jz      short loc_18003C152
0x18003c12c  mov     rcx, qword ptr [rsp+78h+PerformanceCount]
0x18003c134  xor     r9d, r9d; d
0x18003c137  sub     rcx, cs:qword_1801FCD08; a
0x18003c13e  mov     edx, 989680h; b
0x18003c143  mov     r8, cs:c; c
0x18003c14a  call    MFllMulDiv
0x18003c14f  mov     rbp, rax
0x18003c152  mov     [r14], rbp
0x18003c155  cmp     cs:byte_1801FD289, 10h
0x18003c15c  jb      short loc_18003C1BF
0x18003c15e  mov     r9, 346DC5D63886594Bh
0x18003c168  mov     rax, r9
0x18003c16b  imul    rbp
0x18003c16e  mov     rax, r9
0x18003c171  mov     r9, rsi
0x18003c174  mov     r8, rdx
0x18003c177  imul    qword ptr [r15]
0x18003c17a  sar     r8, 0Bh
0x18003c17e  mov     rcx, r8
0x18003c181  shr     rcx, 3Fh
0x18003c185  add     r8, rcx
0x18003c188  mov     rcx, rdx
0x18003c18b  sar     rcx, 0Bh
0x18003c18f  mov     edx, 0Dh
0x18003c194  mov     rax, rcx
0x18003c197  shr     rax, 3Fh
0x18003c19b  add     rcx, rax
0x18003c19e  mov     eax, [rsi+48h]
0x18003c1a1  mov     [rsp+78h+var_48], eax
0x18003c1a5  mov     [rsp+78h+var_50], r8
0x18003c1aa  mov     [rsp+78h+var_58], rcx
0x18003c1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c1b6  mov     rcx, [rcx+38h]
0x18003c1ba  call    WPP_SF_qiid
0x18003c1bf  call    cs:__imp_GetCurrentThreadId
0x18003c1c5  mov     ecx, [rsi+38h]
0x18003c1c8  cmp     ecx, eax
0x18003c1ca  jnz     short loc_18003C208
0x18003c1cc  mov     eax, [rsi+3Ch]
0x18003c1cf  test    eax, eax
0x18003c1d1  jz      short loc_18003C1E9
0x18003c1d3  dec     eax
0x18003c1d5  lea     rcx, [rsp+78h+PerformanceCount]; this
0x18003c1dd  mov     [rsi+3Ch], eax
0x18003c1e0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c1e5  mov     eax, edi
0x18003c1e7  jmp     short loc_18003C235
0x18003c1e9  lea     rcx, [rsi+30h]; SRWLock
0x18003c1ed  mov     [rsi+38h], r13d
0x18003c1f1  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c1f7  lea     rcx, [rsp+78h+PerformanceCount]; this
0x18003c1ff  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c204  mov     eax, edi
0x18003c206  jmp     short loc_18003C235
0x18003c208  lea     rcx, [rsi+30h]; SRWLock
0x18003c20c  call    cs:__imp_ReleaseSRWLockShared
0x18003c212  lea     rcx, [rsp+78h+PerformanceCount]; this
0x18003c21a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c21f  mov     eax, edi
0x18003c221  jmp     short loc_18003C235
0x18003c223  lea     rcx, [rsp+78h+PerformanceCount]; this
0x18003c22b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c230  mov     eax, 80004003h
0x18003c235  mov     rdi, [rsp+78h+arg_0]
0x18003c23d  lea     r11, [rsp+78h+var_28]
0x18003c242  mov     rbx, [r11+38h]
0x18003c246  mov     rbp, [r11+48h]
0x18003c24a  mov     rsp, r11
0x18003c24d  pop     r15
0x18003c24f  pop     r14
0x18003c251  pop     r13
0x18003c253  pop     r12
0x18003c255  pop     rsi
0x18003c256  retn
```
