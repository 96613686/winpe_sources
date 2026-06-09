# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800401c0`
- end: `0x18004071d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800415b0`

## callees

- `0x180025dd0`
- `0x1800294b0`
- `0x18002a156`
- `0x18002a1f4`
- `0x18003e0c0`
- `0x1800401c0`
- `0x1800437f0`
- `0x180043b54`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180040428`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004045d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180040428`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004045d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800402b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800405e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800402b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800405e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040641`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800404d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800404d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004036f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800403f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004051d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040532`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004036f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800403f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004051d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800403b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800403b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800403c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800403c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800404ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004056d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800404ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004056d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800404b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800404b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004050f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004050f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040500`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180040500`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2)
{
  unsigned int v2; // edi
  int v4; // r15d
  __int64 v5; // r12
  unsigned int v6; // esi
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  __int64 v9; // r8
  unsigned int v10; // r13d
  unsigned int v11; // ecx
  int v12; // edi
  __int64 v13; // rcx
  DWORD dwLowDateTime; // r11d
  unsigned __int64 v15; // r10
  unsigned __int64 v16; // rdx
  _DWORD *v17; // r9
  unsigned __int64 v18; // rbx
  DWORD LastError; // edi
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // r8
  char *v22; // rax
  char *v23; // rbx
  signed __int64 v24; // r14
  void *v25; // rbp
  HANDLE ProcessHeap; // rax
  size_t v27; // r8
  struct _TP_TIMER *v28; // rcx
  DWORD v29; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v31; // rdi
  DWORD v32; // ebx
  void (__fastcall *v33)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v34)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v35; // rdx
  void (__fastcall *v36)(__int64, __int64, _QWORD, _QWORD); // rax
  unsigned int v37; // [rsp+50h] [rbp-88h]
  int v38; // [rsp+54h] [rbp-84h]
  unsigned int v39; // [rsp+58h] [rbp-80h]
  unsigned int v40; // [rsp+5Ch] [rbp-7Ch]
  char v41[24]; // [rsp+60h] [rbp-78h] BYREF
  int v42; // [rsp+78h] [rbp-60h] BYREF
  __int16 v43; // [rsp+7Ch] [rbp-5Ch]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp-58h] BYREF
  __int64 v45; // [rsp+88h] [rbp-50h] BYREF

  v2 = a2;
  v4 = *(_DWORD *)Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor;
  if ( (*(_DWORD *)Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor & 4) == 0 )
  {
    v45 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetCachedFeatureEnabledState(
                       a1,
                       &pftDueTime);
    LOWORD(v4) = v45;
  }
  v42 = 0;
  v43 = 2;
  LODWORD(v45) = 3;
  v5 = a1 + 8;
  v6 = v2;
  v39 = v2;
  v7 = 4 * (v2 ^ 1) + 2;
  v37 = v7;
  v8 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v41, v5, v7);
  v10 = v8[1];
  v11 = v8[2];
  v40 = v11;
  v12 = v8[4];
  v38 = v12;
  if ( *v8 && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      goto LABEL_38;
    AcquireSRWLockExclusive(&stru_18009BCE0);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_37:
      ReleaseSRWLockExclusive(&stru_18009BCE0);
LABEL_38:
      v11 = v40;
      goto LABEL_39;
    }
    dwLowDateTime = 0;
    pftDueTime = 0;
    v15 = qword_18009BD18;
    v16 = qword_18009BD18 - (_QWORD)qword_18009BD08;
    v17 = qword_18009BD10;
    if ( (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08 + 16 >= (unsigned __int64)(qword_18009BD18
                                                                                      - (_QWORD)qword_18009BD08) )
    {
      v18 = 16;
      if ( 2 * v16 > 0x10 )
        v18 = 2 * v16;
      if ( v16 < v18 )
      {
        LastError = GetLastError();
        v20 = (v18 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v22 = (char *)wil::details::ProcessHeapAlloc(0, v20, v21);
        v23 = v22;
        if ( !v22 )
        {
          SetLastError(LastError);
          goto LABEL_30;
        }
        v24 = (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08;
        memcpy_s_0(v22, v20, qword_18009BD08, (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08);
        v25 = qword_18009BD20;
        qword_18009BD20 = v23;
        if ( v25 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
        }
        qword_18009BD08 = v23;
        qword_18009BD10 = &v23[v24];
        qword_18009BD18 = (__int64)&v23[v20];
        SetLastError(LastError);
        v15 = qword_18009BD18;
        v17 = qword_18009BD10;
        dwLowDateTime = pftDueTime.dwLowDateTime;
      }
    }
    v27 = 0;
    if ( (unsigned __int64)v17 < v15 )
      v27 = v15 - (_QWORD)v17;
    if ( v17 )
    {
      if ( v27 >= 0x10 )
      {
        *v17 = 56414822;
        v17[1] = dwLowDateTime;
        *((_QWORD *)v17 + 1) = v5;
LABEL_29:
        qword_18009BD10 = (char *)qword_18009BD10 + 16;
LABEL_30:
        if ( !byte_18009BCF0 )
        {
          v28 = pti;
          if ( pti )
            goto LABEL_35;
          v29 = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              &wil::details::g_enabledStateManager,
                              0);
          v31 = pti;
          if ( pti )
          {
            v32 = GetLastError();
            SetThreadpoolTimer(v31, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v31, 1);
            CloseThreadpoolTimer(v31);
            SetLastError(v32);
          }
          pti = ThreadpoolTimer;
          SetLastError(v29);
          v28 = pti;
          if ( pti )
          {
LABEL_35:
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v28, &pftDueTime, 0, 0x124F8u);
            byte_18009BCF0 = 1;
          }
        }
        v7 = v37;
        v12 = v38;
        v6 = v39;
        goto LABEL_37;
      }
      memset_0(v17, 0, v27);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v13, v16, v27) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_29;
  }
LABEL_39:
  if ( v10 )
  {
    v33 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v33 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v33(56414822, v11, v10, 0);
    }
  }
  if ( !v12 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_18009BCE0);
    if ( !qword_18009BD00 )
    {
      qword_18009BD00 = 0;
      v34 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v34 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v34(&qword_18009BD00, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_18009BCE0);
  }
  if ( (v4 & 0x400) != 0 )
  {
    v35 = v7;
    if ( (v4 & 0x800) != 0 )
      v35 = v7 | 0x80000000;
    v36 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v36 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v36(56414822, v35, 0, 0);
    }
  }
  if ( !v12 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v9) = 2;
      g_wil_details_realtimeFeatureUsageHook(56414822, v7, v9);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(56414822, &v42, 0, v6, &v45, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x1800401c0  mov     [rsp+arg_10], rbx
0x1800401c5  push    rbp
0x1800401c6  push    rsi
0x1800401c7  push    rdi
0x1800401c8  push    r12
0x1800401ca  push    r13
0x1800401cc  push    r14
0x1800401ce  push    r15
0x1800401d0  sub     rsp, 0A0h
0x1800401d7  mov     rax, cs:__security_cookie
0x1800401de  xor     rax, rsp
0x1800401e1  mov     [rsp+0D8h+var_48], rax
0x1800401e9  movzx   edi, dl
0x1800401ec  mov     rbx, rcx
0x1800401ef  mov     rax, cs:Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor
0x1800401f6  mov     r15d, [rax]
0x1800401f9  test    r15b, 4
0x1800401fd  jnz     short loc_18004021A
0x1800401ff  lea     rdx, [rsp+0D8h+pftDueTime]
0x180040207  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetCachedFeatureEnabledState(void)
0x18004020c  mov     rcx, [rax]
0x18004020f  mov     [rsp+0D8h+var_50], rcx
0x180040217  mov     r15d, ecx
0x18004021a  xor     eax, eax
0x18004021c  mov     [rsp+0D8h+var_60], eax
0x180040220  mov     [rsp+0D8h+var_5C], 2
0x180040227  mov     dword ptr [rsp+0D8h+var_50], 3
0x180040232  lea     r12, [rbx+8]
0x180040236  mov     esi, edi
0x180040238  mov     [rsp+0D8h+var_80], edi
0x18004023c  mov     eax, edi
0x18004023e  xor     eax, 1
0x180040241  lea     ebx, ds:2[rax*4]
0x180040248  mov     [rsp+0D8h+var_88], ebx
0x18004024c  mov     r8d, ebx
0x18004024f  mov     rdx, r12
0x180040252  lea     rcx, [rsp+0D8h+var_78]
0x180040257  call    wil_details_FeatureReporting_RecordUsageInCache
0x18004025c  mov     r13d, [rax+4]
0x180040260  mov     ecx, [rax+8]
0x180040263  mov     [rsp+0D8h+var_7C], ecx
0x180040267  mov     edi, [rax+10h]
0x18004026a  mov     [rsp+0D8h+var_84], edi
0x18004026e  cmp     dword ptr [rax], 0
0x180040271  jz      loc_1800405A3
0x180040277  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004027d  test    eax, eax
0x18004027f  jz      loc_1800405A3
0x180040285  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004028c  jnz     loc_1800405A3
0x180040292  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180040299  test    rax, rax
0x18004029c  jz      short loc_1800402AB
0x18004029e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402a3  test    al, al
0x1800402a5  jnz     loc_18004059F
0x1800402ab  lea     rcx, stru_18009BCE0; SRWLock
0x1800402b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800402b9  nop     dword ptr [rax+rax+00h]
0x1800402be  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800402c4  test    eax, eax
0x1800402c6  jz      loc_18004058C
0x1800402cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800402d3  jnz     loc_18004058C
0x1800402d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800402e0  test    rax, rax
0x1800402e3  jz      short loc_1800402F2
0x1800402e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402ea  test    al, al
0x1800402ec  jnz     loc_18004058C
0x1800402f2  xor     r11d, r11d
0x1800402f5  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], r11
0x1800402fd  mov     r10, cs:qword_18009BD18
0x180040304  mov     rdx, r10
0x180040307  sub     rdx, cs:qword_18009BD08
0x18004030e  mov     r9, cs:qword_18009BD10
0x180040315  mov     rax, r9
0x180040318  sub     rax, cs:qword_18009BD08
0x18004031f  add     rax, 10h
0x180040323  cmp     rax, rdx
0x180040326  jb      loc_180040413
0x18004032c  lea     rax, [rdx+rdx]
0x180040330  mov     ebx, 10h
0x180040335  cmp     rax, rbx
0x180040338  cmova   rbx, rax
0x18004033c  cmp     rdx, rbx
0x18004033f  jnb     loc_180040413
0x180040345  call    cs:__imp_GetLastError
0x18004034c  nop     dword ptr [rax+rax+00h]
0x180040351  mov     edi, eax
0x180040353  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180040357  lea     rsi, [rbx+40h]
0x18004035b  mov     rdx, rsi; dwBytes
0x18004035e  xor     ecx, ecx; dwFlags
0x180040360  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180040365  mov     rbx, rax
0x180040368  test    rax, rax
0x18004036b  jnz     short loc_180040380
0x18004036d  mov     ecx, edi; dwErrCode
0x18004036f  call    cs:__imp_SetLastError
0x180040376  nop     dword ptr [rax+rax+00h]
0x18004037b  jmp     loc_18004047C
0x180040380  mov     r8, cs:qword_18009BD08; Source
0x180040387  mov     r14, cs:qword_18009BD10
0x18004038e  sub     r14, r8
0x180040391  mov     r9, r14; SourceSize
0x180040394  mov     rdx, rsi; DestinationSize
0x180040397  mov     rcx, rbx; Destination
0x18004039a  call    memcpy_s_0
0x18004039f  mov     rbp, cs:qword_18009BD20
0x1800403a6  mov     cs:qword_18009BD20, rbx
0x1800403ad  test    rbp, rbp
0x1800403b0  jz      short loc_1800403D2
0x1800403b2  call    cs:__imp_GetProcessHeap
0x1800403b9  nop     dword ptr [rax+rax+00h]
0x1800403be  mov     rcx, rax; hHeap
0x1800403c1  mov     r8, rbp; lpMem
0x1800403c4  xor     edx, edx; dwFlags
0x1800403c6  call    cs:__imp_HeapFree
0x1800403cd  nop     dword ptr [rax+rax+00h]
0x1800403d2  mov     cs:qword_18009BD08, rbx
0x1800403d9  lea     rax, [r14+rbx]
0x1800403dd  mov     cs:qword_18009BD10, rax
0x1800403e4  lea     rax, [rsi+rbx]
0x1800403e8  mov     cs:qword_18009BD18, rax
0x1800403ef  mov     ecx, edi; dwErrCode
0x1800403f1  call    cs:__imp_SetLastError
0x1800403f8  nop     dword ptr [rax+rax+00h]
0x1800403fd  mov     r10, cs:qword_18009BD18
0x180040404  mov     r9, cs:qword_18009BD10
0x18004040b  mov     r11, qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime]
0x180040413  mov     rax, r10
0x180040416  sub     rax, r9
0x180040419  xor     r8d, r8d
0x18004041c  cmp     r9, r10
0x18004041f  cmovb   r8, rax; Size
0x180040423  test    r9, r9
0x180040426  jnz     short loc_18004043C
0x180040428  call    cs:__imp__o__errno
0x18004042f  nop     dword ptr [rax+rax+00h]
0x180040434  mov     dword ptr [rax], 16h
0x18004043a  jmp     short loc_18004046F
0x18004043c  cmp     r8, 10h
0x180040440  jb      short loc_180040453
0x180040442  mov     dword ptr [r9], 35CD266h
0x180040449  mov     [r9+4], r11d
0x18004044d  mov     [r9+8], r12
0x180040451  jmp     short loc_180040474
0x180040453  xor     edx, edx; Val
0x180040455  mov     rcx, r9; void *
0x180040458  call    memset_0
0x18004045d  call    cs:__imp__o__errno
0x180040464  nop     dword ptr [rax+rax+00h]
0x180040469  mov     dword ptr [rax], 22h ; '"'
0x18004046f  call    _invalid_parameter_noinfo
0x180040474  add     cs:qword_18009BD10, 10h
0x18004047c  cmp     cs:byte_18009BCF0, 0
0x180040483  jnz     loc_180040580
0x180040489  mov     rcx, cs:pti
0x180040490  test    rcx, rcx
0x180040493  jnz     loc_18004054A
0x180040499  call    cs:__imp_GetLastError
0x1800404a0  nop     dword ptr [rax+rax+00h]
0x1800404a5  mov     esi, eax
0x1800404a7  xor     r8d, r8d; pcbe
0x1800404aa  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800404b1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800404b8  call    cs:__imp_CreateThreadpoolTimer
0x1800404bf  nop     dword ptr [rax+rax+00h]
0x1800404c4  mov     rbp, rax
0x1800404c7  mov     rdi, cs:pti
0x1800404ce  test    rdi, rdi
0x1800404d1  jz      short loc_180040529
0x1800404d3  call    cs:__imp_GetLastError
0x1800404da  nop     dword ptr [rax+rax+00h]
0x1800404df  mov     ebx, eax
0x1800404e1  xor     r9d, r9d; msWindowLength
0x1800404e4  xor     r8d, r8d; msPeriod
0x1800404e7  xor     edx, edx; pftDueTime
0x1800404e9  mov     rcx, rdi; pti
0x1800404ec  call    cs:__imp_SetThreadpoolTimer
0x1800404f3  nop     dword ptr [rax+rax+00h]
0x1800404f8  mov     edx, 1; fCancelPendingCallbacks
0x1800404fd  mov     rcx, rdi; pti
0x180040500  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180040507  nop     dword ptr [rax+rax+00h]
0x18004050c  mov     rcx, rdi; pti
0x18004050f  call    cs:__imp_CloseThreadpoolTimer
0x180040516  nop     dword ptr [rax+rax+00h]
0x18004051b  mov     ecx, ebx; dwErrCode
0x18004051d  call    cs:__imp_SetLastError
0x180040524  nop     dword ptr [rax+rax+00h]
0x180040529  mov     cs:pti, rbp
0x180040530  mov     ecx, esi; dwErrCode
0x180040532  call    cs:__imp_SetLastError
0x180040539  nop     dword ptr [rax+rax+00h]
0x18004053e  mov     rcx, cs:pti; pti
0x180040545  test    rcx, rcx
0x180040548  jz      short loc_180040580
0x18004054a  mov     rax, 0FFFFFFFF4D2FA200h
0x180040554  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18004055c  mov     r9d, 124F8h; msWindowLength
0x180040562  xor     r8d, r8d; msPeriod
0x180040565  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18004056d  call    cs:__imp_SetThreadpoolTimer
0x180040574  nop     dword ptr [rax+rax+00h]
0x180040579  mov     cs:byte_18009BCF0, 1
0x180040580  mov     ebx, [rsp+0D8h+var_88]
0x180040584  mov     edi, [rsp+0D8h+var_84]
0x180040588  mov     esi, [rsp+0D8h+var_80]
0x18004058c  lea     rcx, stru_18009BCE0; SRWLock
0x180040593  call    cs:__imp_ReleaseSRWLockExclusive
0x18004059a  nop     dword ptr [rax+rax+00h]
0x18004059f  mov     ecx, [rsp+0D8h+var_7C]
0x1800405a3  test    r13d, r13d
0x1800405a6  jz      short loc_1800405D2
0x1800405a8  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800405af  test    rax, rax
0x1800405b2  jnz     short loc_1800405C0
0x1800405b4  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800405bb  test    rax, rax
0x1800405be  jz      short loc_1800405D2
0x1800405c0  mov     edx, ecx
0x1800405c2  xor     r9d, r9d
0x1800405c5  mov     r8d, r13d
0x1800405c8  mov     ecx, 35CD266h
0x1800405cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405d2  test    edi, edi
0x1800405d4  jnz     short loc_18004064E
0x1800405d6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800405dc  test    eax, eax
0x1800405de  jz      short loc_18004064E
0x1800405e0  lea     rcx, stru_18009BCE0; SRWLock
0x1800405e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800405ee  nop     dword ptr [rax+rax+00h]
0x1800405f3  cmp     cs:qword_18009BD00, 0
0x1800405fb  jnz     short loc_18004063A
0x1800405fd  mov     cs:qword_18009BD00, 0
0x180040608  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18004060f  test    rax, rax
0x180040612  jnz     short loc_180040620
0x180040614  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18004061b  test    rax, rax
0x18004061e  jz      short loc_18004063A
0x180040620  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180040627  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18004062e  lea     rcx, qword_18009BD00
0x180040635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004063a  lea     rcx, stru_18009BCE0; SRWLock
0x180040641  call    cs:__imp_ReleaseSRWLockExclusive
0x180040648  nop     dword ptr [rax+rax+00h]
0x18004064d  nop
0x18004064e  bt      r15d, 0Ah
0x180040653  jnb     short loc_18004068D
0x180040655  mov     eax, ebx
0x180040657  bts     eax, 1Fh
0x18004065b  mov     edx, ebx
0x18004065d  bt      r15d, 0Bh
0x180040662  cmovb   edx, eax
0x180040665  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18004066c  test    rax, rax
0x18004066f  jnz     short loc_18004067D
0x180040671  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180040678  test    rax, rax
0x18004067b  jz      short loc_18004068D
0x18004067d  xor     r9d, r9d
0x180040680  xor     r8d, r8d
0x180040683  mov     ecx, 35CD266h
0x180040688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004068d  test    edi, edi
0x18004068f  jnz     short loc_1800406F1
0x180040691  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180040698  test    rax, rax
0x18004069b  jz      short loc_1800406AC
0x18004069d  mov     r8b, 2
0x1800406a0  mov     edx, ebx
0x1800406a2  mov     ecx, 35CD266h
0x1800406a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ac  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800406b3  test    rax, rax
0x1800406b6  jz      short loc_1800406F1
0x1800406b8  mov     [rsp+0D8h+var_A0], 1
0x1800406c1  mov     [rsp+0D8h+var_A8], 0
0x1800406c6  mov     [rsp+0D8h+var_B0], 0
0x1800406cf  lea     rdx, [rsp+0D8h+var_50]
0x1800406d7  mov     [rsp+0D8h+var_B8], rdx
0x1800406dc  mov     r9d, esi
0x1800406df  xor     r8d, r8d
0x1800406e2  lea     rdx, [rsp+0D8h+var_60]
0x1800406e7  mov     ecx, 35CD266h
0x1800406ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406f1  mov     rcx, [rsp+0D8h+var_48]
0x1800406f9  xor     rcx, rsp; StackCookie
0x1800406fc  call    __security_check_cookie
0x180040701  mov     rbx, [rsp+0D8h+arg_10]
0x180040709  add     rsp, 0A0h
0x180040710  pop     r15
0x180040712  pop     r14
0x180040714  pop     r13
0x180040716  pop     r12
  ... truncated ...
```
