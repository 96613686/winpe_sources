# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800150f0`
- end: `0x180015557`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `1127`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180014b9c`
- `0x180015040`
- `0x18004ca88`

## callees

- `0x1800150f0`
- `0x18001dffc`
- `0x18001f544`
- `0x180026326`
- `0x180026394`
- `0x180033588`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001533c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015311`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001533c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800151bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001547c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800151bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001547c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015430`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800154d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015430`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800154d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001526b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001526b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800153b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015410`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800153b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015410`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001538b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001538b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800153c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800153c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800153ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800153ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v8; // r15d
  int *v11; // rax
  int v12; // ebx
  unsigned int v13; // edi
  unsigned int v14; // r14d
  int v15; // ebp
  __int64 v16; // rcx
  DWORD dwLowDateTime; // r11d
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // rdx
  unsigned int *v20; // r9
  unsigned __int64 v21; // rbx
  DWORD LastError; // edi
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // r8
  char *v25; // rax
  char *v26; // rbx
  signed __int64 v27; // r15
  void *v28; // rbp
  HANDLE ProcessHeap; // rax
  size_t v30; // r8
  struct _TP_TIMER *v31; // rcx
  DWORD v32; // ebp
  struct _TP_TIMER *ThreadpoolTimer; // r14
  struct _TP_TIMER *v34; // rdi
  DWORD v35; // ebx
  void (__fastcall *v36)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v37)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v38; // rdx
  void (__fastcall *v39)(_QWORD, __int64, _QWORD, _QWORD); // rax
  unsigned int v41; // [rsp+30h] [rbp-68h]
  int v42; // [rsp+34h] [rbp-64h]
  _FILETIME pftDueTime; // [rsp+38h] [rbp-60h] BYREF
  char v44[88]; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v47; // [rsp+D0h] [rbp+38h]

  v8 = a3;
  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v44, a1, a5, a6);
  v12 = *v11;
  v13 = v11[1];
  v47 = v13;
  v14 = v11[2];
  v41 = v14;
  v15 = v11[4];
  v42 = v15;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_39:
      ReleaseSRWLockExclusive(&SRWLock);
      v15 = v42;
      goto LABEL_40;
    }
    dwLowDateTime = 0;
    pftDueTime = 0;
    v18 = qword_180095F28;
    v19 = qword_180095F28 - (_QWORD)Source;
    v20 = (unsigned int *)qword_180095F20;
    if ( (_BYTE *)qword_180095F20 - (_BYTE *)Source + 16 >= (unsigned __int64)(qword_180095F28 - (_QWORD)Source) )
    {
      v21 = 16;
      if ( 2 * v19 > 0x10 )
        v21 = 2 * v19;
      if ( v19 < v21 )
      {
        LastError = GetLastError();
        v23 = (v21 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v25 = (char *)wil::details::ProcessHeapAlloc(0, v23, v24);
        v26 = v25;
        if ( !v25 )
        {
          SetLastError(LastError);
          goto LABEL_32;
        }
        v27 = (_BYTE *)qword_180095F20 - (_BYTE *)Source;
        memcpy_s_0(v25, v23, Source, (_BYTE *)qword_180095F20 - (_BYTE *)Source);
        v28 = lpMem;
        lpMem = v26;
        if ( v28 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v28);
        }
        Source = v26;
        qword_180095F20 = &v26[v27];
        qword_180095F28 = (__int64)&v26[v23];
        SetLastError(LastError);
        v18 = qword_180095F28;
        v20 = (unsigned int *)qword_180095F20;
        v8 = a3;
        dwLowDateTime = pftDueTime.dwLowDateTime;
      }
    }
    v30 = 0;
    if ( (unsigned __int64)v20 < v18 )
      v30 = v18 - (_QWORD)v20;
    if ( v20 )
    {
      if ( v30 >= 0x10 )
      {
        *v20 = a2;
        v20[1] = dwLowDateTime;
        *((_QWORD *)v20 + 1) = a1;
LABEL_31:
        qword_180095F20 = (char *)qword_180095F20 + 16;
LABEL_32:
        if ( !byte_180095F10 )
        {
          v31 = pti;
          if ( pti )
            goto LABEL_37;
          v32 = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              &wil::details::g_enabledStateManager,
                              0);
          v34 = pti;
          if ( pti )
          {
            v35 = GetLastError();
            SetThreadpoolTimer(v34, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v34, 1);
            CloseThreadpoolTimer(v34);
            SetLastError(v35);
          }
          pti = ThreadpoolTimer;
          SetLastError(v32);
          v31 = pti;
          if ( pti )
          {
LABEL_37:
            pftDueTime = (_FILETIME)-3000000000LL;
            SetThreadpoolTimer(v31, &pftDueTime, 0, 0x124F8u);
            byte_180095F10 = 1;
          }
        }
        v13 = v47;
        v14 = v41;
        goto LABEL_39;
      }
      memset_0(v20, 0, v30);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v16, v19, v30) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_31;
  }
LABEL_40:
  if ( v13 )
  {
    v36 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v36 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v36(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180095F60 )
    {
      qword_180095F60 = 0;
      v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v37(&qword_180095F60, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v8 )
  {
    v38 = a5;
    LODWORD(v38) = a5 | 0x80000000;
    if ( !a4 )
      v38 = a5;
    v39 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v39 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v39(a2, v38, 0, 0);
    }
  }
  if ( v15 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(a2, a5, a8);
  return 1;
}

```

## disassembly

```asm
0x1800150f0  mov     [rsp+arg_0], rbx
0x1800150f5  mov     [rsp+arg_18], r9d
0x1800150fa  mov     [rsp+arg_10], r8d
0x1800150ff  push    rbp
0x180015100  push    rsi
0x180015101  push    rdi
0x180015102  push    r12
0x180015104  push    r13
0x180015106  push    r14
0x180015108  push    r15
0x18001510a  sub     rsp, 60h
0x18001510e  mov     r15d, r8d
0x180015111  mov     r12d, edx
0x180015114  mov     r13, rcx
0x180015117  mov     r9d, [rsp+98h+arg_28]
0x18001511f  mov     esi, [rsp+98h+arg_20]
0x180015126  mov     r8d, esi
0x180015129  mov     rdx, rcx
0x18001512c  lea     rcx, [rsp+98h+var_58]
0x180015131  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015136  mov     ebx, [rax]
0x180015138  mov     edi, [rax+4]
0x18001513b  mov     [rsp+98h+arg_30], edi
0x180015142  mov     r14d, [rax+8]
0x180015146  mov     [rsp+98h+var_68], r14d
0x18001514b  mov     ebp, [rax+10h]
0x18001514e  mov     [rsp+98h+var_64], ebp
0x180015152  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015159  test    rax, rax
0x18001515c  jz      short loc_18001517A
0x18001515e  test    esi, esi
0x180015160  jz      short loc_18001516A
0x180015162  lea     ecx, [rsi-64h]
0x180015165  cmp     ecx, 31h ; '1'
0x180015168  ja      short loc_18001517A
0x18001516a  mov     r8d, 1
0x180015170  mov     edx, esi
0x180015172  mov     ecx, r12d
0x180015175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001517a  test    ebx, ebx
0x18001517c  jz      loc_18001543A
0x180015182  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015188  test    eax, eax
0x18001518a  jz      loc_18001543A
0x180015190  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180015197  jnz     loc_18001543A
0x18001519d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800151a4  test    rax, rax
0x1800151a7  jz      short loc_1800151B6
0x1800151a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ae  test    al, al
0x1800151b0  jnz     loc_18001543A
0x1800151b6  lea     rcx, SRWLock; SRWLock
0x1800151bd  call    cs:__imp_AcquireSRWLockExclusive
0x1800151c3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800151c9  test    eax, eax
0x1800151cb  jz      loc_180015429
0x1800151d1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800151d8  jnz     loc_180015429
0x1800151de  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800151e5  test    rax, rax
0x1800151e8  jz      short loc_1800151F7
0x1800151ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ef  test    al, al
0x1800151f1  jnz     loc_180015429
0x1800151f7  xor     r11d, r11d
0x1800151fa  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], r11
0x1800151ff  mov     r10, cs:qword_180095F28
0x180015206  mov     rdx, r10
0x180015209  sub     rdx, cs:Source
0x180015210  mov     r9, cs:qword_180095F20
0x180015217  mov     rax, r9
0x18001521a  sub     rax, cs:Source
0x180015221  add     rax, 10h
0x180015225  cmp     rax, rdx
0x180015228  jb      loc_1800152FC
0x18001522e  lea     rax, [rdx+rdx]
0x180015232  mov     ebx, 10h
0x180015237  cmp     rax, rbx
0x18001523a  cmova   rbx, rax
0x18001523e  cmp     rdx, rbx
0x180015241  jnb     loc_1800152FC
0x180015247  call    cs:__imp_GetLastError
0x18001524d  mov     edi, eax
0x18001524f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180015253  lea     r14, [rbx+40h]
0x180015257  mov     rdx, r14; dwBytes
0x18001525a  xor     ecx, ecx; dwFlags
0x18001525c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015261  mov     rbx, rax
0x180015264  test    rax, rax
0x180015267  jnz     short loc_180015276
0x180015269  mov     ecx, edi; dwErrCode
0x18001526b  call    cs:__imp_SetLastError
0x180015271  jmp     loc_180015355
0x180015276  mov     r8, cs:Source; Source
0x18001527d  mov     r15, cs:qword_180095F20
0x180015284  sub     r15, r8
0x180015287  mov     r9, r15; SourceSize
0x18001528a  mov     rdx, r14; DestinationSize
0x18001528d  mov     rcx, rbx; Destination
0x180015290  call    memcpy_s_0
0x180015295  mov     rbp, cs:lpMem
0x18001529c  mov     cs:lpMem, rbx
0x1800152a3  test    rbp, rbp
0x1800152a6  jz      short loc_1800152BC
0x1800152a8  call    cs:__imp_GetProcessHeap
0x1800152ae  mov     rcx, rax; hHeap
0x1800152b1  mov     r8, rbp; lpMem
0x1800152b4  xor     edx, edx; dwFlags
0x1800152b6  call    cs:__imp_HeapFree
0x1800152bc  mov     cs:Source, rbx
0x1800152c3  lea     rax, [r15+rbx]
0x1800152c7  mov     cs:qword_180095F20, rax
0x1800152ce  lea     rax, [r14+rbx]
0x1800152d2  mov     cs:qword_180095F28, rax
0x1800152d9  mov     ecx, edi; dwErrCode
0x1800152db  call    cs:__imp_SetLastError
0x1800152e1  mov     r10, cs:qword_180095F28
0x1800152e8  mov     r9, cs:qword_180095F20
0x1800152ef  mov     r15d, [rsp+98h+arg_10]
0x1800152f7  mov     r11, qword ptr [rsp+98h+pftDueTime.dwLowDateTime]
0x1800152fc  mov     rax, r10
0x1800152ff  sub     rax, r9
0x180015302  xor     r8d, r8d
0x180015305  cmp     r9, r10
0x180015308  cmovb   r8, rax; Size
0x18001530c  test    r9, r9
0x18001530f  jnz     short loc_18001531F
0x180015311  call    cs:__imp__o__errno
0x180015317  mov     dword ptr [rax], 16h
0x18001531d  jmp     short loc_180015348
0x18001531f  cmp     r8, 10h
0x180015323  jb      short loc_180015332
0x180015325  mov     [r9], r12d
0x180015328  mov     [r9+4], r11d
0x18001532c  mov     [r9+8], r13
0x180015330  jmp     short loc_18001534D
0x180015332  xor     edx, edx; Val
0x180015334  mov     rcx, r9; void *
0x180015337  call    memset_0
0x18001533c  call    cs:__imp__o__errno
0x180015342  mov     dword ptr [rax], 22h ; '"'
0x180015348  call    _invalid_parameter_noinfo
0x18001534d  add     cs:qword_180095F20, 10h
0x180015355  cmp     cs:byte_180095F10, 0
0x18001535c  jnz     loc_18001541D
0x180015362  mov     rcx, cs:pti
0x180015369  test    rcx, rcx
0x18001536c  jnz     loc_1800153F3
0x180015372  call    cs:__imp_GetLastError
0x180015378  mov     ebp, eax
0x18001537a  xor     r8d, r8d; pcbe
0x18001537d  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015384  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001538b  call    cs:__imp_CreateThreadpoolTimer
0x180015391  mov     r14, rax
0x180015394  mov     rdi, cs:pti
0x18001539b  test    rdi, rdi
0x18001539e  jz      short loc_1800153D8
0x1800153a0  call    cs:__imp_GetLastError
0x1800153a6  mov     ebx, eax
0x1800153a8  xor     r9d, r9d; msWindowLength
0x1800153ab  xor     r8d, r8d; msPeriod
0x1800153ae  xor     edx, edx; pftDueTime
0x1800153b0  mov     rcx, rdi; pti
0x1800153b3  call    cs:__imp_SetThreadpoolTimer
0x1800153b9  mov     edx, 1; fCancelPendingCallbacks
0x1800153be  mov     rcx, rdi; pti
0x1800153c1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800153c7  mov     rcx, rdi; pti
0x1800153ca  call    cs:__imp_CloseThreadpoolTimer
0x1800153d0  mov     ecx, ebx; dwErrCode
0x1800153d2  call    cs:__imp_SetLastError
0x1800153d8  mov     cs:pti, r14
0x1800153df  mov     ecx, ebp; dwErrCode
0x1800153e1  call    cs:__imp_SetLastError
0x1800153e7  mov     rcx, cs:pti; pti
0x1800153ee  test    rcx, rcx
0x1800153f1  jz      short loc_18001541D
0x1800153f3  mov     rax, 0FFFFFFFF4D2FA200h
0x1800153fd  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x180015402  mov     r9d, 124F8h; msWindowLength
0x180015408  xor     r8d, r8d; msPeriod
0x18001540b  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x180015410  call    cs:__imp_SetThreadpoolTimer
0x180015416  mov     cs:byte_180095F10, 1
0x18001541d  mov     edi, [rsp+98h+arg_30]
0x180015424  mov     r14d, [rsp+98h+var_68]
0x180015429  lea     rcx, SRWLock; SRWLock
0x180015430  call    cs:__imp_ReleaseSRWLockExclusive
0x180015436  mov     ebp, [rsp+98h+var_64]
0x18001543a  test    edi, edi
0x18001543c  jz      short loc_180015467
0x18001543e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015445  test    rax, rax
0x180015448  jnz     short loc_180015456
0x18001544a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015451  test    rax, rax
0x180015454  jz      short loc_180015467
0x180015456  xor     r9d, r9d
0x180015459  mov     r8d, edi
0x18001545c  mov     edx, r14d
0x18001545f  mov     ecx, r12d
0x180015462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015467  test    ebp, ebp
0x180015469  jnz     short loc_1800154D7
0x18001546b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015471  test    eax, eax
0x180015473  jz      short loc_1800154D7
0x180015475  lea     rcx, SRWLock; SRWLock
0x18001547c  call    cs:__imp_AcquireSRWLockExclusive
0x180015482  cmp     cs:qword_180095F60, 0
0x18001548a  jnz     short loc_1800154C9
0x18001548c  mov     cs:qword_180095F60, 0
0x180015497  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001549e  test    rax, rax
0x1800154a1  jnz     short loc_1800154AF
0x1800154a3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800154aa  test    rax, rax
0x1800154ad  jz      short loc_1800154C9
0x1800154af  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800154b6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800154bd  lea     rcx, qword_180095F60
0x1800154c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c9  lea     rcx, SRWLock; SRWLock
0x1800154d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800154d6  nop
0x1800154d7  test    r15d, r15d
0x1800154da  jz      short loc_180015513
0x1800154dc  mov     edx, esi
0x1800154de  bts     edx, 1Fh
0x1800154e2  cmp     [rsp+98h+arg_18], 0
0x1800154ea  cmovz   edx, esi
0x1800154ed  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800154f4  test    rax, rax
0x1800154f7  jnz     short loc_180015505
0x1800154f9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015500  test    rax, rax
0x180015503  jz      short loc_180015513
0x180015505  xor     r9d, r9d
0x180015508  xor     r8d, r8d
0x18001550b  mov     ecx, r12d
0x18001550e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015513  test    ebp, ebp
0x180015515  jnz     short loc_18001553D
0x180015517  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001551e  test    rax, rax
0x180015521  jz      short loc_180015536
0x180015523  movzx   r8d, [rsp+98h+arg_38]
0x18001552c  mov     edx, esi
0x18001552e  mov     ecx, r12d
0x180015531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015536  mov     eax, 1
0x18001553b  jmp     short loc_18001553F
0x18001553d  xor     eax, eax
0x18001553f  mov     rbx, [rsp+98h+arg_0]
0x180015547  add     rsp, 60h
0x18001554b  pop     r15
0x18001554d  pop     r14
0x18001554f  pop     r13
0x180015551  pop     r12
0x180015553  pop     rdi
0x180015554  pop     rsi
0x180015555  pop     rbp
0x180015556  retn
```
