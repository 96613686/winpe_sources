# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18012e540`
- end: `0x18012ea03`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18012fb60`

## callees

- `0x180079624`
- `0x180082db8`
- `0x180089918`
- `0x1801289f0`
- `0x18012e540`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e6ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e75f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e831`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e6ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e75f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18012e831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e7c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e7c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012e7f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012e633`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012e8ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012e633`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012e8ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012e882`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012e940`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012e882`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18012e940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e73a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e73a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e72c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e72c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012e803`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012e860`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012e803`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012e860`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012e811`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012e811`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012e81a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012e81a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012e7db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18012e7db`

## pseudocode

```c
void wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        ...)
{
  int v4; // r15d
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // ebp
  __int64 v8; // rdi
  unsigned int v9; // ebx
  _DWORD *v10; // rax
  __int64 v11; // r8
  bool v12; // zf
  int v13; // esi
  unsigned int v14; // r12d
  unsigned int v15; // r13d
  void *v16; // r10
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rbx
  DWORD LastError; // esi
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // r8
  char *v23; // rax
  char *v24; // rbx
  signed __int64 v25; // rdi
  void *v26; // rbp
  HANDLE ProcessHeap; // rax
  rsize_t v28; // rdx
  struct _TP_TIMER *v29; // rcx
  DWORD v30; // esi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v32; // rdi
  struct _TP_TIMER *v33; // rbp
  DWORD v34; // ebx
  void (__fastcall *v35)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v36)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v37; // rdx
  void (__fastcall *v38)(__int64, __int64, _QWORD, _QWORD); // rax
  int v39; // [rsp+50h] [rbp-88h] BYREF
  __int16 v40; // [rsp+54h] [rbp-84h]
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp-80h] BYREF
  _QWORD Source[2]; // [rsp+60h] [rbp-78h] BYREF
  char v43[40]; // [rsp+70h] [rbp-68h] BYREF
  int v44; // [rsp+E0h] [rbp+8h] BYREF
  int v45; // [rsp+E8h] [rbp+10h]
  int v46; // [rsp+F0h] [rbp+18h]
  __int64 v47; // [rsp+F8h] [rbp+20h] BYREF
  va_list va; // [rsp+F8h] [rbp+20h]
  va_list va1; // [rsp+100h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v47 = va_arg(va1, _QWORD);
  LOBYTE(v46) = a3;
  v4 = *(_DWORD *)Feature_IncreaseUdpTransportTimerInterval2__descriptor;
  v5 = a2;
  if ( (*(_DWORD *)Feature_IncreaseUdpTransportTimerInterval2__descriptor & 4) == 0 )
  {
    v47 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2>::GetCachedFeatureEnabledState(
                       a1,
                       (__int64 *)va);
    LOWORD(v4) = v47;
  }
  LODWORD(v47) = v5;
  v39 = 0;
  v40 = 2;
  v6 = v5 ^ 1;
  v44 = 3;
  v7 = v5;
  v8 = a1 + 8;
  v9 = 4 * (v5 ^ 1) + 2;
  v46 = 4 * v6 + 2;
  v10 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v43, v8, v9);
  v12 = *v10 == 0;
  v13 = v10[4];
  v14 = v10[1];
  v15 = v10[2];
  v45 = v13;
  if ( !v12
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&stru_1801EB5C0);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_31:
      ReleaseSRWLockExclusive(&stru_1801EB5C0);
      v7 = v47;
      goto LABEL_32;
    }
    v16 = qword_1801EB5E0;
    v17 = qword_1801EB5E8;
    v18 = qword_1801EB5E8 - (_QWORD)qword_1801EB5D8;
    Source[0] = 56610234;
    Source[1] = v8;
    if ( (_BYTE *)qword_1801EB5E0 - (_BYTE *)qword_1801EB5D8 + 16 >= (unsigned __int64)(qword_1801EB5E8
                                                                                      - (_QWORD)qword_1801EB5D8) )
    {
      v19 = 16;
      if ( 2 * v18 > 0x10 )
        v19 = 2 * v18;
      if ( v18 < v19 )
      {
        LastError = GetLastError();
        v21 = (v19 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v23 = (char *)wil::details::ProcessHeapAlloc(0, v21, v22);
        v24 = v23;
        if ( !v23 )
        {
          SetLastError(LastError);
LABEL_24:
          if ( !byte_1801EB5D0 )
          {
            v29 = pti;
            if ( pti )
              goto LABEL_29;
            v30 = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            v32 = pti;
            v33 = ThreadpoolTimer;
            if ( pti )
            {
              v34 = GetLastError();
              SetThreadpoolTimer(v32, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(v32, 1);
              CloseThreadpoolTimer(v32);
              SetLastError(v34);
            }
            pti = v33;
            SetLastError(v30);
            v29 = pti;
            if ( pti )
            {
LABEL_29:
              pftDueTime = (struct _FILETIME)-3000000000LL;
              SetThreadpoolTimer(v29, &pftDueTime, 0, 0x124F8u);
              byte_1801EB5D0 = 1;
            }
          }
          v9 = v46;
          v13 = v45;
          goto LABEL_31;
        }
        v25 = (_BYTE *)qword_1801EB5E0 - (_BYTE *)qword_1801EB5D8;
        memcpy_s(v23, v21, qword_1801EB5D8, (_BYTE *)qword_1801EB5E0 - (_BYTE *)qword_1801EB5D8);
        v26 = qword_1801EB5F0;
        qword_1801EB5F0 = v24;
        if ( v26 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v26);
        }
        qword_1801EB5D8 = v24;
        qword_1801EB5E0 = &v24[v25];
        qword_1801EB5E8 = (__int64)&v24[v21];
        SetLastError(LastError);
        v17 = qword_1801EB5E8;
        v16 = qword_1801EB5E0;
      }
    }
    v28 = 0;
    if ( (unsigned __int64)v16 < v17 )
      v28 = v17 - (_QWORD)v16;
    memcpy_s(v16, v28, Source, 0x10u);
    qword_1801EB5E0 = (char *)qword_1801EB5E0 + 16;
    goto LABEL_24;
  }
LABEL_32:
  if ( v14 )
  {
    v35 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v35 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v35(56610234, v15, v14, 0);
    }
  }
  if ( !v13 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_1801EB5C0);
    if ( !qword_1801EB620 )
    {
      v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1801EB620 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v36(&qword_1801EB620, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_1801EB5C0);
  }
  if ( (v4 & 0x400) != 0 )
  {
    v37 = v9;
    if ( (v4 & 0x800) != 0 )
      v37 = v9 | 0x80000000;
    v38 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v38 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v38(56610234, v37, 0, 0);
    }
  }
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v11) = 2;
      g_wil_details_realtimeFeatureUsageHook(56610234, v9, v11);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(56610234, &v39, 0, v7, &v44, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x18012e540  mov     r11, rsp
0x18012e543  mov     [r11+20h], r9
0x18012e547  mov     [r11+18h], r8b
0x18012e54b  push    rbx
0x18012e54c  push    rbp
0x18012e54d  sub     rsp, 0C8h
0x18012e554  mov     rax, cs:Feature_IncreaseUdpTransportTimerInterval2__descriptor
0x18012e55b  mov     [r11-18h], rsi
0x18012e55f  mov     [r11-20h], rdi
0x18012e563  mov     rdi, rcx
0x18012e566  mov     [r11-28h], r12
0x18012e56a  mov     [r11-30h], r13
0x18012e56e  mov     [r11-40h], r15
0x18012e572  mov     r15d, [rax]
0x18012e575  movzx   ebx, dl
0x18012e578  test    r15b, 4
0x18012e57c  jnz     short loc_18012E595
0x18012e57e  lea     rdx, [r11+20h]
0x18012e582  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IncreaseUdpTransportTimerInterval2>::GetCachedFeatureEnabledState(void)
0x18012e587  mov     r8, [rax]
0x18012e58a  mov     [rsp+0D8h+arg_18], r8
0x18012e592  mov     r15d, r8d
0x18012e595  xor     eax, eax
0x18012e597  mov     dword ptr [rsp+0D8h+arg_18], ebx
0x18012e59e  mov     [rsp+0D8h+var_88], eax
0x18012e5a2  lea     rcx, [rsp+0D8h+var_68]
0x18012e5a7  mov     eax, ebx
0x18012e5a9  mov     [rsp+0D8h+var_84], 2
0x18012e5b0  xor     eax, 1
0x18012e5b3  mov     [rsp+0D8h+arg_0], 3
0x18012e5be  mov     ebp, ebx
0x18012e5c0  add     rdi, 8
0x18012e5c4  mov     rdx, rdi
0x18012e5c7  lea     ebx, ds:2[rax*4]
0x18012e5ce  mov     r8d, ebx
0x18012e5d1  mov     [rsp+0D8h+arg_10], ebx
0x18012e5d8  call    wil_details_FeatureReporting_RecordUsageInCache
0x18012e5dd  cmp     dword ptr [rax], 0
0x18012e5e0  mov     esi, [rax+10h]
0x18012e5e3  mov     r12d, [rax+4]
0x18012e5e7  mov     r13d, [rax+8]
0x18012e5eb  mov     [rsp+0D8h+arg_8], esi
0x18012e5f2  jz      loc_18012E88F
0x18012e5f8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18012e5fe  test    eax, eax
0x18012e600  jz      loc_18012E88F
0x18012e606  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18012e60d  jnz     loc_18012E88F
0x18012e613  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18012e61a  test    rax, rax
0x18012e61d  jz      short loc_18012E62C
0x18012e61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e624  test    al, al
0x18012e626  jnz     loc_18012E88F
0x18012e62c  lea     rcx, stru_1801EB5C0; SRWLock
0x18012e633  call    cs:__imp_AcquireSRWLockExclusive
0x18012e639  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18012e63f  test    eax, eax
0x18012e641  jz      loc_18012E87B
0x18012e647  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18012e64e  jnz     loc_18012E87B
0x18012e654  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18012e65b  test    rax, rax
0x18012e65e  jz      short loc_18012E66D
0x18012e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e665  test    al, al
0x18012e667  jnz     loc_18012E87B
0x18012e66d  mov     r10, cs:qword_1801EB5E0
0x18012e674  mov     r8, cs:qword_1801EB5E8
0x18012e67b  mov     rax, r10
0x18012e67e  sub     rax, cs:qword_1801EB5D8
0x18012e685  mov     rdx, r8
0x18012e688  sub     rdx, cs:qword_1801EB5D8
0x18012e68f  add     rax, 10h
0x18012e693  mov     [rsp+0D8h+var_38], r14
0x18012e69b  mov     [rsp+0D8h+Source], 35FCDBAh
0x18012e6a4  mov     [rsp+0D8h+var_70], rdi
0x18012e6a9  cmp     rax, rdx
0x18012e6ac  jb      loc_18012E773
0x18012e6b2  lea     rax, [rdx+rdx]
0x18012e6b6  mov     ebx, 10h
0x18012e6bb  cmp     rax, rbx
0x18012e6be  cmova   rbx, rax
0x18012e6c2  cmp     rdx, rbx
0x18012e6c5  jnb     loc_18012E773
0x18012e6cb  call    cs:__imp_GetLastError
0x18012e6d1  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18012e6d5  xor     ecx, ecx; dwFlags
0x18012e6d7  mov     esi, eax
0x18012e6d9  lea     r14, [rbx+40h]
0x18012e6dd  mov     rdx, r14; dwBytes
0x18012e6e0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18012e6e5  mov     rbx, rax
0x18012e6e8  test    rax, rax
0x18012e6eb  jnz     short loc_18012E6FA
0x18012e6ed  mov     ecx, esi; dwErrCode
0x18012e6ef  call    cs:__imp_SetLastError
0x18012e6f5  jmp     loc_18012E79D
0x18012e6fa  mov     r8, cs:qword_1801EB5D8; Source
0x18012e701  mov     rdx, r14; DestinationSize
0x18012e704  mov     rdi, cs:qword_1801EB5E0
0x18012e70b  mov     rcx, rbx; Destination
0x18012e70e  sub     rdi, r8
0x18012e711  mov     r9, rdi; SourceSize
0x18012e714  call    memcpy_s
0x18012e719  mov     rbp, cs:qword_1801EB5F0
0x18012e720  mov     cs:qword_1801EB5F0, rbx
0x18012e727  test    rbp, rbp
0x18012e72a  jz      short loc_18012E740
0x18012e72c  call    cs:__imp_GetProcessHeap
0x18012e732  mov     r8, rbp; lpMem
0x18012e735  xor     edx, edx; dwFlags
0x18012e737  mov     rcx, rax; hHeap
0x18012e73a  call    cs:__imp_HeapFree
0x18012e740  lea     rax, [rdi+rbx]
0x18012e744  mov     cs:qword_1801EB5D8, rbx
0x18012e74b  mov     cs:qword_1801EB5E0, rax
0x18012e752  mov     ecx, esi; dwErrCode
0x18012e754  lea     rax, [r14+rbx]
0x18012e758  mov     cs:qword_1801EB5E8, rax
0x18012e75f  call    cs:__imp_SetLastError
0x18012e765  mov     r8, cs:qword_1801EB5E8
0x18012e76c  mov     r10, cs:qword_1801EB5E0
0x18012e773  mov     rax, r8
0x18012e776  xor     edx, edx
0x18012e778  sub     rax, r10
0x18012e77b  mov     r9d, 10h; SourceSize
0x18012e781  cmp     r10, r8
0x18012e784  mov     rcx, r10; Destination
0x18012e787  lea     r8, [rsp+0D8h+Source]; Source
0x18012e78c  cmovb   rdx, rax; DestinationSize
0x18012e790  call    memcpy_s
0x18012e795  add     cs:qword_1801EB5E0, 10h
0x18012e79d  cmp     cs:byte_1801EB5D0, 0
0x18012e7a4  mov     r14, [rsp+0D8h+var_38]
0x18012e7ac  jnz     loc_18012E86D
0x18012e7b2  mov     rcx, cs:pti
0x18012e7b9  test    rcx, rcx
0x18012e7bc  jnz     loc_18012E843
0x18012e7c2  call    cs:__imp_GetLastError
0x18012e7c8  xor     r8d, r8d; pcbe
0x18012e7cb  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18012e7d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18012e7d9  mov     esi, eax
0x18012e7db  call    cs:__imp_CreateThreadpoolTimer
0x18012e7e1  mov     rdi, cs:pti
0x18012e7e8  mov     rbp, rax
0x18012e7eb  test    rdi, rdi
0x18012e7ee  jz      short loc_18012E828
0x18012e7f0  call    cs:__imp_GetLastError
0x18012e7f6  xor     r9d, r9d; msWindowLength
0x18012e7f9  xor     r8d, r8d; msPeriod
0x18012e7fc  xor     edx, edx; pftDueTime
0x18012e7fe  mov     rcx, rdi; pti
0x18012e801  mov     ebx, eax
0x18012e803  call    cs:__imp_SetThreadpoolTimer
0x18012e809  mov     edx, 1; fCancelPendingCallbacks
0x18012e80e  mov     rcx, rdi; pti
0x18012e811  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18012e817  mov     rcx, rdi; pti
0x18012e81a  call    cs:__imp_CloseThreadpoolTimer
0x18012e820  mov     ecx, ebx; dwErrCode
0x18012e822  call    cs:__imp_SetLastError
0x18012e828  mov     ecx, esi; dwErrCode
0x18012e82a  mov     cs:pti, rbp
0x18012e831  call    cs:__imp_SetLastError
0x18012e837  mov     rcx, cs:pti; pti
0x18012e83e  test    rcx, rcx
0x18012e841  jz      short loc_18012E86D
0x18012e843  mov     rax, 0FFFFFFFF4D2FA200h
0x18012e84d  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18012e852  mov     r9d, 124F8h; msWindowLength
0x18012e858  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18012e85d  xor     r8d, r8d; msPeriod
0x18012e860  call    cs:__imp_SetThreadpoolTimer
0x18012e866  mov     cs:byte_1801EB5D0, 1
0x18012e86d  mov     ebx, [rsp+0D8h+arg_10]
0x18012e874  mov     esi, [rsp+0D8h+arg_8]
0x18012e87b  lea     rcx, stru_1801EB5C0; SRWLock
0x18012e882  call    cs:__imp_ReleaseSRWLockExclusive
0x18012e888  mov     ebp, dword ptr [rsp+0D8h+arg_18]
0x18012e88f  mov     rdi, [rsp+0D8h+var_20]
0x18012e897  test    r12d, r12d
0x18012e89a  jz      short loc_18012E8C7
0x18012e89c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18012e8a3  test    rax, rax
0x18012e8a6  jnz     short loc_18012E8B4
0x18012e8a8  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18012e8af  test    rax, rax
0x18012e8b2  jz      short loc_18012E8C7
0x18012e8b4  xor     r9d, r9d
0x18012e8b7  mov     r8d, r12d
0x18012e8ba  mov     edx, r13d
0x18012e8bd  mov     ecx, 35FCDBAh
0x18012e8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e8c7  mov     r13, [rsp+0D8h+var_30]
0x18012e8cf  mov     r12, [rsp+0D8h+var_28]
0x18012e8d7  test    esi, esi
0x18012e8d9  jnz     short loc_18012E946
0x18012e8db  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18012e8e1  test    eax, eax
0x18012e8e3  jz      short loc_18012E946
0x18012e8e5  lea     rcx, stru_1801EB5C0; SRWLock
0x18012e8ec  call    cs:__imp_AcquireSRWLockExclusive
0x18012e8f2  cmp     cs:qword_1801EB620, 0
0x18012e8fa  jnz     short loc_18012E939
0x18012e8fc  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18012e903  mov     cs:qword_1801EB620, 0
0x18012e90e  test    rax, rax
0x18012e911  jnz     short loc_18012E91F
0x18012e913  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18012e91a  test    rax, rax
0x18012e91d  jz      short loc_18012E939
0x18012e91f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18012e926  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18012e92d  lea     rcx, qword_1801EB620
0x18012e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e939  lea     rcx, stru_1801EB5C0; SRWLock
0x18012e940  call    cs:__imp_ReleaseSRWLockExclusive
0x18012e946  bt      r15d, 0Ah
0x18012e94b  jnb     short loc_18012E985
0x18012e94d  mov     eax, ebx
0x18012e94f  mov     edx, ebx
0x18012e951  bts     eax, 1Fh
0x18012e955  bt      r15d, 0Bh
0x18012e95a  cmovb   edx, eax
0x18012e95d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18012e964  test    rax, rax
0x18012e967  jnz     short loc_18012E975
0x18012e969  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18012e970  test    rax, rax
0x18012e973  jz      short loc_18012E985
0x18012e975  xor     r9d, r9d
0x18012e978  xor     r8d, r8d
0x18012e97b  mov     ecx, 35FCDBAh
0x18012e980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e985  mov     r15, [rsp+0D8h+var_40]
0x18012e98d  test    esi, esi
0x18012e98f  mov     rsi, [rsp+0D8h+var_18]
0x18012e997  jnz     short loc_18012E9F9
0x18012e999  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18012e9a0  test    rax, rax
0x18012e9a3  jz      short loc_18012E9B4
0x18012e9a5  mov     r8b, 2
0x18012e9a8  mov     edx, ebx
0x18012e9aa  mov     ecx, 35FCDBAh
0x18012e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e9b4  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18012e9bb  test    rax, rax
0x18012e9be  jz      short loc_18012E9F9
0x18012e9c0  mov     [rsp+0D8h+var_A0], 1
0x18012e9c9  lea     rdx, [rsp+0D8h+arg_0]
0x18012e9d1  mov     [rsp+0D8h+var_A8], 0
0x18012e9d6  mov     r9d, ebp
0x18012e9d9  mov     [rsp+0D8h+var_B0], 0
0x18012e9e2  xor     r8d, r8d
0x18012e9e5  mov     [rsp+0D8h+var_B8], rdx
0x18012e9ea  mov     ecx, 35FCDBAh
0x18012e9ef  lea     rdx, [rsp+0D8h+var_88]
0x18012e9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012e9f9  add     rsp, 0C8h
0x18012ea00  pop     rbp
0x18012ea01  pop     rbx
0x18012ea02  retn
```
