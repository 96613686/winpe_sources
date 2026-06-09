# wil::details::FeatureImpl<__WilFeatureTraits_Feature_FuzzedBoundaryChecks>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800c37c0`
- end: `0x1800c3c83`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_FuzzedBoundaryChecks@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c4160`

## callees

- `0x180079624`
- `0x180082db8`
- `0x180089918`
- `0x1800c28f0`
- `0x1800c37c0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c396f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c39df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3aa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3ab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c396f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c39df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3aa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c394b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c394b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3a70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c38b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3b6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c38b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c3b6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3b02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3bc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3b02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c3bc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c39ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c39ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c39ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c39ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3a83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3ae0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3a83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c3ae0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c3a91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c3a91`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c3a9a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c3a9a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c3a5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800c3a5b`

## pseudocode

```c
void wil::details::FeatureImpl<__WilFeatureTraits_Feature_FuzzedBoundaryChecks>::ReportUsage(
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
  v4 = *(_DWORD *)Feature_FuzzedBoundaryChecks__descriptor;
  v5 = a2;
  if ( (*(_DWORD *)Feature_FuzzedBoundaryChecks__descriptor & 4) == 0 )
  {
    v47 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FuzzedBoundaryChecks>::GetCachedFeatureEnabledState(
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
    Source[0] = 57496600;
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
      v35(57496600, v15, v14, 0);
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
      v38(57496600, v37, 0, 0);
    }
  }
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v11) = 2;
      g_wil_details_realtimeFeatureUsageHook(57496600, v9, v11);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(57496600, &v39, 0, v7, &v44, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x1800c37c0  mov     r11, rsp
0x1800c37c3  mov     [r11+20h], r9
0x1800c37c7  mov     [r11+18h], r8b
0x1800c37cb  push    rbx
0x1800c37cc  push    rbp
0x1800c37cd  sub     rsp, 0C8h
0x1800c37d4  mov     rax, cs:Feature_FuzzedBoundaryChecks__descriptor
0x1800c37db  mov     [r11-18h], rsi
0x1800c37df  mov     [r11-20h], rdi
0x1800c37e3  mov     rdi, rcx
0x1800c37e6  mov     [r11-28h], r12
0x1800c37ea  mov     [r11-30h], r13
0x1800c37ee  mov     [r11-40h], r15
0x1800c37f2  mov     r15d, [rax]
0x1800c37f5  movzx   ebx, dl
0x1800c37f8  test    r15b, 4
0x1800c37fc  jnz     short loc_1800C3815
0x1800c37fe  lea     rdx, [r11+20h]
0x1800c3802  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FuzzedBoundaryChecks@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FuzzedBoundaryChecks>::GetCachedFeatureEnabledState(void)
0x1800c3807  mov     r8, [rax]
0x1800c380a  mov     [rsp+0D8h+arg_18], r8
0x1800c3812  mov     r15d, r8d
0x1800c3815  xor     eax, eax
0x1800c3817  mov     dword ptr [rsp+0D8h+arg_18], ebx
0x1800c381e  mov     [rsp+0D8h+var_88], eax
0x1800c3822  lea     rcx, [rsp+0D8h+var_68]
0x1800c3827  mov     eax, ebx
0x1800c3829  mov     [rsp+0D8h+var_84], 2
0x1800c3830  xor     eax, 1
0x1800c3833  mov     [rsp+0D8h+arg_0], 3
0x1800c383e  mov     ebp, ebx
0x1800c3840  add     rdi, 8
0x1800c3844  mov     rdx, rdi
0x1800c3847  lea     ebx, ds:2[rax*4]
0x1800c384e  mov     r8d, ebx
0x1800c3851  mov     [rsp+0D8h+arg_10], ebx
0x1800c3858  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800c385d  cmp     dword ptr [rax], 0
0x1800c3860  mov     esi, [rax+10h]
0x1800c3863  mov     r12d, [rax+4]
0x1800c3867  mov     r13d, [rax+8]
0x1800c386b  mov     [rsp+0D8h+arg_8], esi
0x1800c3872  jz      loc_1800C3B0F
0x1800c3878  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800c387e  test    eax, eax
0x1800c3880  jz      loc_1800C3B0F
0x1800c3886  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800c388d  jnz     loc_1800C3B0F
0x1800c3893  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800c389a  test    rax, rax
0x1800c389d  jz      short loc_1800C38AC
0x1800c389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c38a4  test    al, al
0x1800c38a6  jnz     loc_1800C3B0F
0x1800c38ac  lea     rcx, stru_1801EB5C0; SRWLock
0x1800c38b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800c38b9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800c38bf  test    eax, eax
0x1800c38c1  jz      loc_1800C3AFB
0x1800c38c7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800c38ce  jnz     loc_1800C3AFB
0x1800c38d4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800c38db  test    rax, rax
0x1800c38de  jz      short loc_1800C38ED
0x1800c38e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c38e5  test    al, al
0x1800c38e7  jnz     loc_1800C3AFB
0x1800c38ed  mov     r10, cs:qword_1801EB5E0
0x1800c38f4  mov     r8, cs:qword_1801EB5E8
0x1800c38fb  mov     rax, r10
0x1800c38fe  sub     rax, cs:qword_1801EB5D8
0x1800c3905  mov     rdx, r8
0x1800c3908  sub     rdx, cs:qword_1801EB5D8
0x1800c390f  add     rax, 10h
0x1800c3913  mov     [rsp+0D8h+var_38], r14
0x1800c391b  mov     [rsp+0D8h+Source], 36D5418h
0x1800c3924  mov     [rsp+0D8h+var_70], rdi
0x1800c3929  cmp     rax, rdx
0x1800c392c  jb      loc_1800C39F3
0x1800c3932  lea     rax, [rdx+rdx]
0x1800c3936  mov     ebx, 10h
0x1800c393b  cmp     rax, rbx
0x1800c393e  cmova   rbx, rax
0x1800c3942  cmp     rdx, rbx
0x1800c3945  jnb     loc_1800C39F3
0x1800c394b  call    cs:__imp_GetLastError
0x1800c3951  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800c3955  xor     ecx, ecx; dwFlags
0x1800c3957  mov     esi, eax
0x1800c3959  lea     r14, [rbx+40h]
0x1800c395d  mov     rdx, r14; dwBytes
0x1800c3960  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800c3965  mov     rbx, rax
0x1800c3968  test    rax, rax
0x1800c396b  jnz     short loc_1800C397A
0x1800c396d  mov     ecx, esi; dwErrCode
0x1800c396f  call    cs:__imp_SetLastError
0x1800c3975  jmp     loc_1800C3A1D
0x1800c397a  mov     r8, cs:qword_1801EB5D8; Source
0x1800c3981  mov     rdx, r14; DestinationSize
0x1800c3984  mov     rdi, cs:qword_1801EB5E0
0x1800c398b  mov     rcx, rbx; Destination
0x1800c398e  sub     rdi, r8
0x1800c3991  mov     r9, rdi; SourceSize
0x1800c3994  call    memcpy_s
0x1800c3999  mov     rbp, cs:qword_1801EB5F0
0x1800c39a0  mov     cs:qword_1801EB5F0, rbx
0x1800c39a7  test    rbp, rbp
0x1800c39aa  jz      short loc_1800C39C0
0x1800c39ac  call    cs:__imp_GetProcessHeap
0x1800c39b2  mov     r8, rbp; lpMem
0x1800c39b5  xor     edx, edx; dwFlags
0x1800c39b7  mov     rcx, rax; hHeap
0x1800c39ba  call    cs:__imp_HeapFree
0x1800c39c0  lea     rax, [rdi+rbx]
0x1800c39c4  mov     cs:qword_1801EB5D8, rbx
0x1800c39cb  mov     cs:qword_1801EB5E0, rax
0x1800c39d2  mov     ecx, esi; dwErrCode
0x1800c39d4  lea     rax, [r14+rbx]
0x1800c39d8  mov     cs:qword_1801EB5E8, rax
0x1800c39df  call    cs:__imp_SetLastError
0x1800c39e5  mov     r8, cs:qword_1801EB5E8
0x1800c39ec  mov     r10, cs:qword_1801EB5E0
0x1800c39f3  mov     rax, r8
0x1800c39f6  xor     edx, edx
0x1800c39f8  sub     rax, r10
0x1800c39fb  mov     r9d, 10h; SourceSize
0x1800c3a01  cmp     r10, r8
0x1800c3a04  mov     rcx, r10; Destination
0x1800c3a07  lea     r8, [rsp+0D8h+Source]; Source
0x1800c3a0c  cmovb   rdx, rax; DestinationSize
0x1800c3a10  call    memcpy_s
0x1800c3a15  add     cs:qword_1801EB5E0, 10h
0x1800c3a1d  cmp     cs:byte_1801EB5D0, 0
0x1800c3a24  mov     r14, [rsp+0D8h+var_38]
0x1800c3a2c  jnz     loc_1800C3AED
0x1800c3a32  mov     rcx, cs:pti
0x1800c3a39  test    rcx, rcx
0x1800c3a3c  jnz     loc_1800C3AC3
0x1800c3a42  call    cs:__imp_GetLastError
0x1800c3a48  xor     r8d, r8d; pcbe
0x1800c3a4b  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800c3a52  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800c3a59  mov     esi, eax
0x1800c3a5b  call    cs:__imp_CreateThreadpoolTimer
0x1800c3a61  mov     rdi, cs:pti
0x1800c3a68  mov     rbp, rax
0x1800c3a6b  test    rdi, rdi
0x1800c3a6e  jz      short loc_1800C3AA8
0x1800c3a70  call    cs:__imp_GetLastError
0x1800c3a76  xor     r9d, r9d; msWindowLength
0x1800c3a79  xor     r8d, r8d; msPeriod
0x1800c3a7c  xor     edx, edx; pftDueTime
0x1800c3a7e  mov     rcx, rdi; pti
0x1800c3a81  mov     ebx, eax
0x1800c3a83  call    cs:__imp_SetThreadpoolTimer
0x1800c3a89  mov     edx, 1; fCancelPendingCallbacks
0x1800c3a8e  mov     rcx, rdi; pti
0x1800c3a91  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c3a97  mov     rcx, rdi; pti
0x1800c3a9a  call    cs:__imp_CloseThreadpoolTimer
0x1800c3aa0  mov     ecx, ebx; dwErrCode
0x1800c3aa2  call    cs:__imp_SetLastError
0x1800c3aa8  mov     ecx, esi; dwErrCode
0x1800c3aaa  mov     cs:pti, rbp
0x1800c3ab1  call    cs:__imp_SetLastError
0x1800c3ab7  mov     rcx, cs:pti; pti
0x1800c3abe  test    rcx, rcx
0x1800c3ac1  jz      short loc_1800C3AED
0x1800c3ac3  mov     rax, 0FFFFFFFF4D2FA200h
0x1800c3acd  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x1800c3ad2  mov     r9d, 124F8h; msWindowLength
0x1800c3ad8  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x1800c3add  xor     r8d, r8d; msPeriod
0x1800c3ae0  call    cs:__imp_SetThreadpoolTimer
0x1800c3ae6  mov     cs:byte_1801EB5D0, 1
0x1800c3aed  mov     ebx, [rsp+0D8h+arg_10]
0x1800c3af4  mov     esi, [rsp+0D8h+arg_8]
0x1800c3afb  lea     rcx, stru_1801EB5C0; SRWLock
0x1800c3b02  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c3b08  mov     ebp, dword ptr [rsp+0D8h+arg_18]
0x1800c3b0f  mov     rdi, [rsp+0D8h+var_20]
0x1800c3b17  test    r12d, r12d
0x1800c3b1a  jz      short loc_1800C3B47
0x1800c3b1c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800c3b23  test    rax, rax
0x1800c3b26  jnz     short loc_1800C3B34
0x1800c3b28  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800c3b2f  test    rax, rax
0x1800c3b32  jz      short loc_1800C3B47
0x1800c3b34  xor     r9d, r9d
0x1800c3b37  mov     r8d, r12d
0x1800c3b3a  mov     edx, r13d
0x1800c3b3d  mov     ecx, 36D5418h
0x1800c3b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3b47  mov     r13, [rsp+0D8h+var_30]
0x1800c3b4f  mov     r12, [rsp+0D8h+var_28]
0x1800c3b57  test    esi, esi
0x1800c3b59  jnz     short loc_1800C3BC6
0x1800c3b5b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800c3b61  test    eax, eax
0x1800c3b63  jz      short loc_1800C3BC6
0x1800c3b65  lea     rcx, stru_1801EB5C0; SRWLock
0x1800c3b6c  call    cs:__imp_AcquireSRWLockExclusive
0x1800c3b72  cmp     cs:qword_1801EB620, 0
0x1800c3b7a  jnz     short loc_1800C3BB9
0x1800c3b7c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800c3b83  mov     cs:qword_1801EB620, 0
0x1800c3b8e  test    rax, rax
0x1800c3b91  jnz     short loc_1800C3B9F
0x1800c3b93  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800c3b9a  test    rax, rax
0x1800c3b9d  jz      short loc_1800C3BB9
0x1800c3b9f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800c3ba6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800c3bad  lea     rcx, qword_1801EB620
0x1800c3bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3bb9  lea     rcx, stru_1801EB5C0; SRWLock
0x1800c3bc0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c3bc6  bt      r15d, 0Ah
0x1800c3bcb  jnb     short loc_1800C3C05
0x1800c3bcd  mov     eax, ebx
0x1800c3bcf  mov     edx, ebx
0x1800c3bd1  bts     eax, 1Fh
0x1800c3bd5  bt      r15d, 0Bh
0x1800c3bda  cmovb   edx, eax
0x1800c3bdd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800c3be4  test    rax, rax
0x1800c3be7  jnz     short loc_1800C3BF5
0x1800c3be9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800c3bf0  test    rax, rax
0x1800c3bf3  jz      short loc_1800C3C05
0x1800c3bf5  xor     r9d, r9d
0x1800c3bf8  xor     r8d, r8d
0x1800c3bfb  mov     ecx, 36D5418h
0x1800c3c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3c05  mov     r15, [rsp+0D8h+var_40]
0x1800c3c0d  test    esi, esi
0x1800c3c0f  mov     rsi, [rsp+0D8h+var_18]
0x1800c3c17  jnz     short loc_1800C3C79
0x1800c3c19  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800c3c20  test    rax, rax
0x1800c3c23  jz      short loc_1800C3C34
0x1800c3c25  mov     r8b, 2
0x1800c3c28  mov     edx, ebx
0x1800c3c2a  mov     ecx, 36D5418h
0x1800c3c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3c34  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800c3c3b  test    rax, rax
0x1800c3c3e  jz      short loc_1800C3C79
0x1800c3c40  mov     [rsp+0D8h+var_A0], 1
0x1800c3c49  lea     rdx, [rsp+0D8h+arg_0]
0x1800c3c51  mov     [rsp+0D8h+var_A8], 0
0x1800c3c56  mov     r9d, ebp
0x1800c3c59  mov     [rsp+0D8h+var_B0], 0
0x1800c3c62  xor     r8d, r8d
0x1800c3c65  mov     [rsp+0D8h+var_B8], rdx
0x1800c3c6a  mov     ecx, 36D5418h
0x1800c3c6f  lea     rdx, [rsp+0D8h+var_88]
0x1800c3c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3c79  add     rsp, 0C8h
0x1800c3c80  pop     rbp
0x1800c3c81  pop     rbx
0x1800c3c82  retn
```
