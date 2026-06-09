# CBaseStreamSink::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)

- ea: `0x18003d6d0`
- end: `0x18003db5c`
- name: `?QueueEvent@CBaseStreamSink@@UEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z`
- size: `1164`
- prototype: `int(CBaseStreamSink *__hidden this, unsigned int, const struct _GUID *, int, const struct tagPROPVARIANT *)`
- caller_count: `5`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180079a90`
- `0x1800cc968`
- `0x1800e6bb0`
- `0x1800e9ec4`
- `0x180121d10`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x18003d6d0`
- `0x18003e55c`
- `0x180077708`
- `0x180079680`
- `0x18016c588`
- `0x18016c5e4`
- `0x18016d298`
- `0x18016d5b8`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d8da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d830`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d8da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d6fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d870`
- `MFPlat!MFCreateMediaEventResult` at `0x18003d89a`
- `MFPlat!MFCreateMediaEventResult` at `0x18003d89a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d963`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d963`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9bc`
- `MFPlat!MFCreateMediaEvent` at `0x18003d7dc`
- `MFPlat!MFCreateMediaEvent` at `0x18003d7dc`

## string_xrefs

- `0x18003d71a`: `CBaseStreamSink::QueueEvent`
- `0x18003da3b`: `CBaseStreamSink::QueueEvent`

## pseudocode

```c
__int64 __fastcall CBaseStreamSink::QueueEvent(
        CBaseStreamSink *this,
        unsigned int a2,
        const struct _GUID *a3,
        HRESULT a4,
        const struct tagPROPVARIANT *pvValue)
{
  struct _RTL_CRITICAL_SECTION *v5; // r13
  __int64 v10; // rdx
  __int64 v11; // r8
  CallStackTracing *v12; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  char *v16; // r12
  char *v17; // rsi
  struct CallStackContext *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  HRESULT v21; // ebx
  __int64 v22; // rdx
  struct IMFMediaEvent *v24; // rbx
  unsigned int v25; // edx
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  const char *v36; // rax
  int v37; // edx
  int v38; // r8d
  int v39; // [rsp+30h] [rbp-28h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v41[3]; // [rsp+40h] [rbp-18h] BYREF
  int v42; // [rsp+A0h] [rbp+48h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v12 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
    v14 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v14 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v15 = 2 * v14;
      *((_QWORD *)ThreadRelativeContext + v15) = "CBaseStreamSink::QueueEvent";
      *((_DWORD *)ThreadRelativeContext + 2 * v15 + 2) = 227;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v12 = CallStackTracing::s_wpInstance;
  }
  v16 = (char *)this - 16;
  if ( *((_DWORD *)this + 82) == 7 )
  {
    v21 = -1072870856;
    if ( g_wppLevels >= 4u )
    {
      v35 = 26;
LABEL_58:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, WPP_85ded7c3193c34fe64ab2cb119f9c690_Traceguids, v16, v21);
    }
  }
  else
  {
    v17 = (char *)this + 88;
    if ( !v12 )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v12);
      v19 = *((unsigned int *)v18 + 497);
      if ( (unsigned int)v19 < *((_DWORD *)v18 + 498) )
      {
        v20 = 2 * v19;
        *((_QWORD *)v18 + v20) = "CMFMediaEventGenerator::QueueEvent";
        *((_DWORD *)v18 + 2 * v20 + 2) = 366;
      }
      ++*((_DWORD *)v18 + 497);
    }
    if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
    {
      v36 = MFTRACE_STRING_FROM_MET(a2);
      WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v37, v38, (_DWORD)v17, (__int64)v36, a4);
    }
    if ( *((_DWORD *)this + 34) )
    {
      v21 = -1072873851;
    }
    else
    {
      ppEvent = 0;
      v21 = MFCreateMediaEvent(a2, a3, a4, pvValue, &ppEvent);
      if ( v21 >= 0 )
      {
        v24 = ppEvent;
        v41[0] = 0;
        v42 = 0;
        v39 = 0;
        if ( ppEvent
          && ((int (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetType)(ppEvent, &v42) >= 0
          && v42 == 1
          && ((int (__fastcall *)(struct IMFMediaEvent *, int *))v24->lpVtbl->GetStatus)(v24, &v39) >= 0 )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( v39 < 0 && *((_DWORD *)v33 + 499) != v39 )
              CallStackContext::TraceFailure(v33, "CMFMediaEventGenerator::QueueEvent", 458, v39);
          }
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
        if ( *((_DWORD *)v17 + 12) )
        {
          v21 = -1072873851;
        }
        else
        {
          if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
            MFTRACE_MEDIA_EVENT_IMPL(0x30001u, v25, v24);
          v21 = MFCreateMediaEventResult(v24, v41);
          if ( v21 >= 0 )
          {
            v26 = (__int64 *)*((_QWORD *)v17 + 9);
            v27 = v41[0] + 128LL;
            *(_QWORD *)(v41[0] + 128LL) = v17 + 64;
            *(_QWORD *)(v27 + 8) = v26;
            *v26 = v27;
            ++*((_DWORD *)v17 + 14);
            *((_QWORD *)v17 + 9) = v27;
            v21 = CMFMediaEventGenerator::CheckDispatchEvent((CMFMediaEventGenerator *)v17);
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
      }
      if ( ppEvent )
        ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    }
    if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 17), v10, v11, v17, v21);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
    if ( v21 < 0 )
    {
      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v34 + 499) != v21 )
          CallStackContext::TraceFailure(v34, "CBaseStreamSink::QueueEvent", 244, v21);
      }
      if ( g_wppLevels )
      {
        v35 = 27;
        goto LABEL_58;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  LeaveCriticalSection(v5);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18003d6d0  push    rbp
0x18003d6d2  push    rbx
0x18003d6d3  push    rsi
0x18003d6d4  push    rdi
0x18003d6d5  push    r12
0x18003d6d7  push    r13
0x18003d6d9  push    r14
0x18003d6db  push    r15
0x18003d6dd  mov     rbp, rsp
0x18003d6e0  sub     rsp, 58h
0x18003d6e4  lea     r13, [rcx+0F8h]
0x18003d6eb  mov     rbx, rcx
0x18003d6ee  mov     rcx, r13; lpCriticalSection
0x18003d6f1  mov     edi, r9d
0x18003d6f4  mov     r15, r8
0x18003d6f7  mov     r14d, edx
0x18003d6fa  call    cs:__imp_EnterCriticalSection
0x18003d701  nop     dword ptr [rax+rax+00h]
0x18003d706  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003d70d  test    rcx, rcx
0x18003d710  jz      loc_18003D8EB
0x18003d716  cmp     byte ptr [rcx+8], 0
0x18003d71a  lea     rsi, aCbasestreamsin_23; "CBaseStreamSink::QueueEvent"
0x18003d721  jz      short loc_18003D752
0x18003d723  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d728  mov     ecx, [rax+7C4h]
0x18003d72e  cmp     ecx, [rax+7C8h]
0x18003d734  jnb     short loc_18003D745
0x18003d736  add     rcx, rcx
0x18003d739  mov     [rax+rcx*8], rsi
0x18003d73d  mov     dword ptr [rax+rcx*8+8], 0E3h
0x18003d745  inc     dword ptr [rax+7C4h]
0x18003d74b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003d752  lea     r12, [rbx-10h]
0x18003d756  cmp     dword ptr [r12+158h], 7
0x18003d75f  jz      loc_18003DA55
0x18003d765  lea     rsi, [rbx+58h]
0x18003d769  test    rcx, rcx
0x18003d76c  jz      loc_18003D8FC
0x18003d772  cmp     byte ptr [rcx+8], 0
0x18003d776  lea     rbx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18003d77d  jz      short loc_18003D7A7
0x18003d77f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d784  mov     ecx, [rax+7C4h]
0x18003d78a  cmp     ecx, [rax+7C8h]
0x18003d790  jnb     short loc_18003D7A1
0x18003d792  add     rcx, rcx
0x18003d795  mov     [rax+rcx*8], rbx
0x18003d799  mov     dword ptr [rax+rcx*8+8], 16Eh
0x18003d7a1  inc     dword ptr [rax+7C4h]
0x18003d7a7  cmp     cs:byte_1801BA10B, 10h
0x18003d7ae  jnb     loc_18003DA71
0x18003d7b4  cmp     dword ptr [rsi+30h], 0
0x18003d7b8  jnz     loc_18003D995
0x18003d7be  mov     r9, [rbp+pvValue]; pvValue
0x18003d7c2  lea     rax, [rbp+var_20]
0x18003d7c6  mov     r8d, edi; hrStatus
0x18003d7c9  mov     [rsp+58h+ppEvent], rax; ppEvent
0x18003d7ce  mov     rdx, r15; guidExtendedType
0x18003d7d1  mov     [rbp+var_20], 0
0x18003d7d9  mov     ecx, r14d; met
0x18003d7dc  call    cs:__imp_MFCreateMediaEvent
0x18003d7e3  nop     dword ptr [rax+rax+00h]
0x18003d7e8  xor     r14d, r14d
0x18003d7eb  mov     ebx, eax
0x18003d7ed  test    eax, eax
0x18003d7ef  jns     short loc_18003D850
0x18003d7f1  mov     rcx, [rbp+var_20]
0x18003d7f5  test    rcx, rcx
0x18003d7f8  jz      short loc_18003D806
0x18003d7fa  mov     rax, [rcx]
0x18003d7fd  mov     rax, [rax+10h]
0x18003d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d806  cmp     cs:byte_1801BA10B, 20h ; ' '
0x18003d80d  jnb     loc_18003DADE
0x18003d813  lea     rcx, [rbp+arg_0]; this
0x18003d817  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d81c  test    ebx, ebx
0x18003d81e  js      loc_18003D9AC
0x18003d824  lea     rcx, [rbp+arg_0]; this
0x18003d828  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d82d  mov     rcx, r13; lpCriticalSection
0x18003d830  call    cs:__imp_LeaveCriticalSection
0x18003d837  nop     dword ptr [rax+rax+00h]
0x18003d83c  mov     eax, ebx
0x18003d83e  add     rsp, 58h
0x18003d842  pop     r15
0x18003d844  pop     r14
0x18003d846  pop     r13
0x18003d848  pop     r12
0x18003d84a  pop     rdi
0x18003d84b  pop     rsi
0x18003d84c  pop     rbx
0x18003d84d  pop     rbp
0x18003d84e  retn
0x18003d850  mov     rbx, [rbp+var_20]
0x18003d854  mov     [rbp+var_18], r14
0x18003d858  mov     [rbp+arg_0], r14d
0x18003d85c  mov     [rbp+var_28], r14d
0x18003d860  test    rbx, rbx
0x18003d863  jnz     loc_18003D90D
0x18003d869  lea     rdi, [rsi+8]
0x18003d86d  mov     rcx, rdi; lpCriticalSection
0x18003d870  call    cs:__imp_EnterCriticalSection
0x18003d877  nop     dword ptr [rax+rax+00h]
0x18003d87c  cmp     [rsi+30h], r14d
0x18003d880  jnz     loc_18003D9A2
0x18003d886  cmp     cs:byte_1801BA10B, 10h
0x18003d88d  jnb     loc_18003DACC
0x18003d893  lea     rdx, [rbp+var_18]
0x18003d897  mov     rcx, rbx
0x18003d89a  call    cs:__imp_MFCreateMediaEventResult
0x18003d8a1  nop     dword ptr [rax+rax+00h]
0x18003d8a6  mov     ebx, eax
0x18003d8a8  test    eax, eax
0x18003d8aa  js      short loc_18003D8D7
0x18003d8ac  mov     rdx, [rbp+var_18]
0x18003d8b0  lea     rcx, [rsi+40h]
0x18003d8b4  mov     rax, [rcx+8]
0x18003d8b8  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18003d8bc  mov     [rdx], rcx
0x18003d8bf  mov     [rdx+8], rax
0x18003d8c3  mov     [rax], rdx
0x18003d8c6  inc     dword ptr [rsi+38h]
0x18003d8c9  mov     [rcx+8], rdx
0x18003d8cd  mov     rcx, rsi; this
0x18003d8d0  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x18003d8d5  mov     ebx, eax
0x18003d8d7  mov     rcx, rdi; lpCriticalSection
0x18003d8da  call    cs:__imp_LeaveCriticalSection
0x18003d8e1  nop     dword ptr [rax+rax+00h]
0x18003d8e6  jmp     loc_18003D7F1
0x18003d8eb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003d8f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d8f7  jmp     loc_18003D716
0x18003d8fc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003d901  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d908  jmp     loc_18003D772
0x18003d90d  mov     rax, [rbx]
0x18003d910  lea     rdx, [rbp+arg_0]
0x18003d914  mov     rcx, rbx
0x18003d917  mov     rax, [rax+108h]
0x18003d91e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d923  test    eax, eax
0x18003d925  js      loc_18003D869
0x18003d92b  cmp     [rbp+arg_0], 1
0x18003d92f  jnz     loc_18003D869
0x18003d935  mov     rax, [rbx]
0x18003d938  lea     rdx, [rbp+var_28]
0x18003d93c  mov     rcx, rbx
0x18003d93f  mov     rax, [rax+118h]
0x18003d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d94b  test    eax, eax
0x18003d94d  js      loc_18003D869
0x18003d953  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d95a  test    rcx, rcx
0x18003d95d  jnz     loc_18003DABD
0x18003d963  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d96a  nop     dword ptr [rax+rax+00h]
0x18003d96f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d976  mov     rcx, rax
0x18003d979  test    rax, rax
0x18003d97c  jnz     loc_18003DA9D
0x18003d982  lea     rcx, qword_1801B97E0
0x18003d989  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d990  jmp     loc_18003DABD
0x18003d995  mov     ebx, 0C00D3E85h
0x18003d99a  xor     r14d, r14d
0x18003d99d  jmp     loc_18003D806
0x18003d9a2  mov     ebx, 0C00D3E85h
0x18003d9a7  jmp     loc_18003D8D7
0x18003d9ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9b3  test    rcx, rcx
0x18003d9b6  jnz     loc_18003DB1D
0x18003d9bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d9c3  nop     dword ptr [rax+rax+00h]
0x18003d9c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9cf  mov     rcx, rax
0x18003d9d2  test    rax, rax
0x18003d9d5  jnz     loc_18003DAFD
0x18003d9db  lea     rcx, qword_1801B97E0
0x18003d9e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9e9  jmp     loc_18003DB1D
0x18003d9ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d9f3  mov     r9d, [rbp+var_28]; int
0x18003d9f7  test    r9d, r9d
0x18003d9fa  jns     loc_18003D869
0x18003da00  cmp     [rax+7CCh], r9d
0x18003da07  jz      loc_18003D869
0x18003da0d  mov     r8d, 1CAh; int
0x18003da13  lea     rdx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18003da1a  mov     rcx, rax; this
0x18003da1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003da22  jmp     loc_18003D869
0x18003da27  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003da2c  cmp     [rax+7CCh], ebx
0x18003da32  jz      loc_18003DB27
0x18003da38  mov     r9d, ebx; int
0x18003da3b  lea     rdx, aCbasestreamsin_23; "CBaseStreamSink::QueueEvent"
0x18003da42  mov     r8d, 0F4h; int
0x18003da48  mov     rcx, rax; this
0x18003da4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003da50  jmp     loc_18003DB27
0x18003da55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18003da5c  mov     ebx, 0C00D4A38h
0x18003da61  jb      loc_18003D824
0x18003da67  mov     edx, 1Ah
0x18003da6c  jmp     loc_18003DB39
0x18003da71  mov     ecx, r14d; unsigned int
0x18003da74  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x18003da79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da80  mov     r9, rsi
0x18003da83  mov     [rsp+58h+var_30], edi
0x18003da87  mov     [rsp+58h+ppEvent], rax
0x18003da8c  mov     rcx, [rcx+88h]
0x18003da93  call    WPP_SF_qsL
0x18003da98  jmp     loc_18003D7B4
0x18003da9d  mov     rax, [rax]
0x18003daa0  mov     edx, 7F0h
0x18003daa5  mov     rax, [rax+8]
0x18003daa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daae  test    eax, eax
0x18003dab0  jz      loc_18003D982
0x18003dab6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003dabd  cmp     [rcx+8], r14b
0x18003dac1  jz      loc_18003D869
0x18003dac7  jmp     loc_18003D9EE
0x18003dacc  mov     r8, rbx; struct IMFMediaEvent *
0x18003dacf  mov     ecx, 30001h; unsigned int
0x18003dad4  call    ?MFTRACE_MEDIA_EVENT_IMPL@@YAXKKPEAUIMFMediaEvent@@@Z; MFTRACE_MEDIA_EVENT_IMPL(ulong,ulong,IMFMediaEvent *)
0x18003dad9  jmp     loc_18003D893
0x18003dade  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dae5  mov     r9, rsi
0x18003dae8  mov     dword ptr [rsp+58h+ppEvent], ebx
0x18003daec  mov     rcx, [rcx+88h]
0x18003daf3  call    WPP_SF_qL
0x18003daf8  jmp     loc_18003D813
0x18003dafd  mov     rax, [rax]
0x18003db00  mov     edx, 7F0h
0x18003db05  mov     rax, [rax+8]
0x18003db09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db0e  test    eax, eax
0x18003db10  jz      loc_18003D9DB
0x18003db16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003db1d  cmp     [rcx+8], r14b
0x18003db21  jnz     loc_18003DA27
0x18003db27  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003db2e  jb      loc_18003D824
0x18003db34  mov     edx, 1Bh
0x18003db39  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db40  lea     r8, WPP_85ded7c3193c34fe64ab2cb119f9c690_Traceguids
0x18003db47  mov     r9, r12
0x18003db4a  mov     dword ptr [rsp+58h+ppEvent], ebx
0x18003db4e  mov     rcx, [rcx+10h]
0x18003db52  call    WPP_SF_qD
0x18003db57  jmp     loc_18003D824
```
