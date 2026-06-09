# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18007e770`
- end: `0x18007ecae`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1342`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18007fa70`

## callees

- `0x18005ad2c`
- `0x1800749d0`
- `0x18007a0f0`
- `0x18007e770`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007e956`
- `msvcrt!memcpy_s` at `0x18007e9eb`
- `msvcrt!memcpy_s` at `0x18007e956`
- `msvcrt!memcpy_s` at `0x18007e9eb`
- `KERNEL32!HeapFree` at `0x18007e989`
- `KERNEL32!HeapFree` at `0x18007e989`
- `KERNEL32!SetLastError` at `0x18007e92b`
- `KERNEL32!SetLastError` at `0x18007e9b4`
- `KERNEL32!SetLastError` at `0x18007eaa8`
- `KERNEL32!SetLastError` at `0x18007eabd`
- `KERNEL32!SetLastError` at `0x18007e92b`
- `KERNEL32!SetLastError` at `0x18007e9b4`
- `KERNEL32!SetLastError` at `0x18007eaa8`
- `KERNEL32!SetLastError` at `0x18007eabd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007ea8b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007ea8b`
- `KERNEL32!GetLastError` at `0x18007e901`
- `KERNEL32!GetLastError` at `0x18007ea24`
- `KERNEL32!GetLastError` at `0x18007ea5e`
- `KERNEL32!GetLastError` at `0x18007e901`
- `KERNEL32!GetLastError` at `0x18007ea24`
- `KERNEL32!GetLastError` at `0x18007ea5e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007eb1a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007ebe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007eb1a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007ebe4`
- `KERNEL32!CloseThreadpoolTimer` at `0x18007ea9a`
- `KERNEL32!CloseThreadpoolTimer` at `0x18007ea9a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007e863`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007eb8a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007e863`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007eb8a`
- `KERNEL32!SetThreadpoolTimer` at `0x18007ea77`
- `KERNEL32!SetThreadpoolTimer` at `0x18007eaf2`
- `KERNEL32!SetThreadpoolTimer` at `0x18007ea77`
- `KERNEL32!SetThreadpoolTimer` at `0x18007eaf2`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007ea43`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007ea43`
- `KERNEL32!GetProcessHeap` at `0x18007e975`
- `KERNEL32!GetProcessHeap` at `0x18007e975`

## pseudocode

```c
void wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::ReportUsage(
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
  v4 = *(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor;
  v5 = a2;
  if ( (*(_DWORD *)Feature_Servicing_VBScript_Enhanced_Logging__descriptor & 4) == 0 )
  {
    v47 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(
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
    AcquireSRWLockExclusive(&SRWLock);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_31:
      ReleaseSRWLockExclusive(&SRWLock);
      v7 = v47;
      goto LABEL_32;
    }
    v16 = qword_1800B90F0;
    v17 = qword_1800B90F8;
    v18 = qword_1800B90F8 - (_QWORD)qword_1800B90E8;
    Source[0] = 57540041;
    Source[1] = v8;
    if ( (_BYTE *)qword_1800B90F0 - (_BYTE *)qword_1800B90E8 + 16 >= (unsigned __int64)(qword_1800B90F8
                                                                                      - (_QWORD)qword_1800B90E8) )
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
          if ( !byte_1800B90D0 )
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
              byte_1800B90D0 = 1;
            }
          }
          v9 = v46;
          v13 = v45;
          goto LABEL_31;
        }
        v25 = (_BYTE *)qword_1800B90F0 - (_BYTE *)qword_1800B90E8;
        memcpy_s(v23, v21, qword_1800B90E8, (_BYTE *)qword_1800B90F0 - (_BYTE *)qword_1800B90E8);
        v26 = qword_1800B9100;
        qword_1800B9100 = v24;
        if ( v26 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v26);
        }
        qword_1800B90E8 = v24;
        qword_1800B90F0 = &v24[v25];
        qword_1800B90F8 = (__int64)&v24[v21];
        SetLastError(LastError);
        v17 = qword_1800B90F8;
        v16 = qword_1800B90F0;
      }
    }
    v28 = 0;
    if ( (unsigned __int64)v16 < v17 )
      v28 = v17 - (_QWORD)v16;
    memcpy_s(v16, v28, Source, 0x10u);
    qword_1800B90F0 = (char *)qword_1800B90F0 + 16;
    goto LABEL_24;
  }
LABEL_32:
  if ( v14 )
  {
    v35 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v35 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v35(57540041, v15, v14, 0);
    }
  }
  if ( !v13 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800B90E0 )
    {
      v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B90E0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v36(&qword_1800B90E0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
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
      v38(57540041, v37, 0, 0);
    }
  }
  if ( !v13 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v11) = 2;
      g_wil_details_realtimeFeatureUsageHook(57540041, v9, v11);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(57540041, &v39, 0, v7, &v44, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x18007e770  mov     r11, rsp
0x18007e773  mov     [r11+20h], r9
0x18007e777  mov     [r11+18h], r8b
0x18007e77b  push    rbx
0x18007e77c  push    rbp
0x18007e77d  sub     rsp, 0C8h
0x18007e784  mov     rax, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x18007e78b  mov     [r11-18h], rsi
0x18007e78f  mov     [r11-20h], rdi
0x18007e793  mov     rdi, rcx
0x18007e796  mov     [r11-28h], r12
0x18007e79a  mov     [r11-30h], r13
0x18007e79e  mov     [r11-40h], r15
0x18007e7a2  mov     r15d, [rax]
0x18007e7a5  movzx   ebx, dl
0x18007e7a8  test    r15b, 4
0x18007e7ac  jnz     short loc_18007E7C5
0x18007e7ae  lea     rdx, [r11+20h]
0x18007e7b2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)
0x18007e7b7  mov     r8, [rax]
0x18007e7ba  mov     [rsp+0D8h+arg_18], r8
0x18007e7c2  mov     r15d, r8d
0x18007e7c5  xor     eax, eax
0x18007e7c7  mov     dword ptr [rsp+0D8h+arg_18], ebx
0x18007e7ce  mov     [rsp+0D8h+var_88], eax
0x18007e7d2  lea     rcx, [rsp+0D8h+var_68]
0x18007e7d7  mov     eax, ebx
0x18007e7d9  mov     [rsp+0D8h+var_84], 2
0x18007e7e0  xor     eax, 1
0x18007e7e3  mov     [rsp+0D8h+arg_0], 3
0x18007e7ee  mov     ebp, ebx
0x18007e7f0  add     rdi, 8
0x18007e7f4  mov     rdx, rdi
0x18007e7f7  lea     ebx, ds:2[rax*4]
0x18007e7fe  mov     r8d, ebx
0x18007e801  mov     [rsp+0D8h+arg_10], ebx
0x18007e808  call    wil_details_FeatureReporting_RecordUsageInCache
0x18007e80d  cmp     dword ptr [rax], 0
0x18007e810  mov     esi, [rax+10h]
0x18007e813  mov     r12d, [rax+4]
0x18007e817  mov     r13d, [rax+8]
0x18007e81b  mov     [rsp+0D8h+arg_8], esi
0x18007e822  jz      loc_18007EB2D
0x18007e828  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007e82e  test    eax, eax
0x18007e830  jz      loc_18007EB2D
0x18007e836  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007e83d  jnz     loc_18007EB2D
0x18007e843  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007e84a  test    rax, rax
0x18007e84d  jz      short loc_18007E85C
0x18007e84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e854  test    al, al
0x18007e856  jnz     loc_18007EB2D
0x18007e85c  lea     rcx, SRWLock; SRWLock
0x18007e863  call    cs:__imp_AcquireSRWLockExclusive
0x18007e86a  nop     dword ptr [rax+rax+00h]
0x18007e86f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007e875  test    eax, eax
0x18007e877  jz      loc_18007EB13
0x18007e87d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007e884  jnz     loc_18007EB13
0x18007e88a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007e891  test    rax, rax
0x18007e894  jz      short loc_18007E8A3
0x18007e896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e89b  test    al, al
0x18007e89d  jnz     loc_18007EB13
0x18007e8a3  mov     r10, cs:qword_1800B90F0
0x18007e8aa  mov     r8, cs:qword_1800B90F8
0x18007e8b1  mov     rax, r10
0x18007e8b4  sub     rax, cs:qword_1800B90E8
0x18007e8bb  mov     rdx, r8
0x18007e8be  sub     rdx, cs:qword_1800B90E8
0x18007e8c5  add     rax, 10h
0x18007e8c9  mov     [rsp+0D8h+var_38], r14
0x18007e8d1  mov     [rsp+0D8h+Source], 36DFDC9h
0x18007e8da  mov     [rsp+0D8h+var_70], rdi
0x18007e8df  cmp     rax, rdx
0x18007e8e2  jb      loc_18007E9CE
0x18007e8e8  lea     rax, [rdx+rdx]
0x18007e8ec  mov     ebx, 10h
0x18007e8f1  cmp     rax, rbx
0x18007e8f4  cmova   rbx, rax
0x18007e8f8  cmp     rdx, rbx
0x18007e8fb  jnb     loc_18007E9CE
0x18007e901  call    cs:__imp_GetLastError
0x18007e908  nop     dword ptr [rax+rax+00h]
0x18007e90d  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18007e911  xor     ecx, ecx; dwFlags
0x18007e913  mov     esi, eax
0x18007e915  lea     r14, [rbx+40h]
0x18007e919  mov     rdx, r14; dwBytes
0x18007e91c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007e921  mov     rbx, rax
0x18007e924  test    rax, rax
0x18007e927  jnz     short loc_18007E93C
0x18007e929  mov     ecx, esi; dwErrCode
0x18007e92b  call    cs:__imp_SetLastError
0x18007e932  nop     dword ptr [rax+rax+00h]
0x18007e937  jmp     loc_18007E9FF
0x18007e93c  mov     r8, cs:qword_1800B90E8; Source
0x18007e943  mov     rdx, r14; DestinationSize
0x18007e946  mov     rdi, cs:qword_1800B90F0
0x18007e94d  mov     rcx, rbx; Destination
0x18007e950  sub     rdi, r8
0x18007e953  mov     r9, rdi; SourceSize
0x18007e956  call    cs:__imp_memcpy_s
0x18007e95d  nop     dword ptr [rax+rax+00h]
0x18007e962  mov     rbp, cs:qword_1800B9100
0x18007e969  mov     cs:qword_1800B9100, rbx
0x18007e970  test    rbp, rbp
0x18007e973  jz      short loc_18007E995
0x18007e975  call    cs:__imp_GetProcessHeap
0x18007e97c  nop     dword ptr [rax+rax+00h]
0x18007e981  mov     r8, rbp; lpMem
0x18007e984  xor     edx, edx; dwFlags
0x18007e986  mov     rcx, rax; hHeap
0x18007e989  call    cs:__imp_HeapFree
0x18007e990  nop     dword ptr [rax+rax+00h]
0x18007e995  lea     rax, [rdi+rbx]
0x18007e999  mov     cs:qword_1800B90E8, rbx
0x18007e9a0  mov     cs:qword_1800B90F0, rax
0x18007e9a7  mov     ecx, esi; dwErrCode
0x18007e9a9  lea     rax, [r14+rbx]
0x18007e9ad  mov     cs:qword_1800B90F8, rax
0x18007e9b4  call    cs:__imp_SetLastError
0x18007e9bb  nop     dword ptr [rax+rax+00h]
0x18007e9c0  mov     r8, cs:qword_1800B90F8
0x18007e9c7  mov     r10, cs:qword_1800B90F0
0x18007e9ce  mov     rax, r8
0x18007e9d1  xor     edx, edx
0x18007e9d3  sub     rax, r10
0x18007e9d6  mov     r9d, 10h; SourceSize
0x18007e9dc  cmp     r10, r8
0x18007e9df  mov     rcx, r10; Destination
0x18007e9e2  lea     r8, [rsp+0D8h+Source]; Source
0x18007e9e7  cmovb   rdx, rax; DestinationSize
0x18007e9eb  call    cs:__imp_memcpy_s
0x18007e9f2  nop     dword ptr [rax+rax+00h]
0x18007e9f7  add     cs:qword_1800B90F0, 10h
0x18007e9ff  cmp     cs:byte_1800B90D0, 0
0x18007ea06  mov     r14, [rsp+0D8h+var_38]
0x18007ea0e  jnz     loc_18007EB05
0x18007ea14  mov     rcx, cs:pti
0x18007ea1b  test    rcx, rcx
0x18007ea1e  jnz     loc_18007EAD5
0x18007ea24  call    cs:__imp_GetLastError
0x18007ea2b  nop     dword ptr [rax+rax+00h]
0x18007ea30  xor     r8d, r8d; pcbe
0x18007ea33  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18007ea3a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007ea41  mov     esi, eax
0x18007ea43  call    cs:__imp_CreateThreadpoolTimer
0x18007ea4a  nop     dword ptr [rax+rax+00h]
0x18007ea4f  mov     rdi, cs:pti
0x18007ea56  mov     rbp, rax
0x18007ea59  test    rdi, rdi
0x18007ea5c  jz      short loc_18007EAB4
0x18007ea5e  call    cs:__imp_GetLastError
0x18007ea65  nop     dword ptr [rax+rax+00h]
0x18007ea6a  xor     r9d, r9d; msWindowLength
0x18007ea6d  xor     r8d, r8d; msPeriod
0x18007ea70  xor     edx, edx; pftDueTime
0x18007ea72  mov     rcx, rdi; pti
0x18007ea75  mov     ebx, eax
0x18007ea77  call    cs:__imp_SetThreadpoolTimer
0x18007ea7e  nop     dword ptr [rax+rax+00h]
0x18007ea83  mov     edx, 1; fCancelPendingCallbacks
0x18007ea88  mov     rcx, rdi; pti
0x18007ea8b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007ea92  nop     dword ptr [rax+rax+00h]
0x18007ea97  mov     rcx, rdi; pti
0x18007ea9a  call    cs:__imp_CloseThreadpoolTimer
0x18007eaa1  nop     dword ptr [rax+rax+00h]
0x18007eaa6  mov     ecx, ebx; dwErrCode
0x18007eaa8  call    cs:__imp_SetLastError
0x18007eaaf  nop     dword ptr [rax+rax+00h]
0x18007eab4  mov     ecx, esi; dwErrCode
0x18007eab6  mov     cs:pti, rbp
0x18007eabd  call    cs:__imp_SetLastError
0x18007eac4  nop     dword ptr [rax+rax+00h]
0x18007eac9  mov     rcx, cs:pti; pti
0x18007ead0  test    rcx, rcx
0x18007ead3  jz      short loc_18007EB05
0x18007ead5  mov     rax, 0FFFFFFFF4D2FA200h
0x18007eadf  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18007eae4  mov     r9d, 124F8h; msWindowLength
0x18007eaea  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18007eaef  xor     r8d, r8d; msPeriod
0x18007eaf2  call    cs:__imp_SetThreadpoolTimer
0x18007eaf9  nop     dword ptr [rax+rax+00h]
0x18007eafe  mov     cs:byte_1800B90D0, 1
0x18007eb05  mov     ebx, [rsp+0D8h+arg_10]
0x18007eb0c  mov     esi, [rsp+0D8h+arg_8]
0x18007eb13  lea     rcx, SRWLock; SRWLock
0x18007eb1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18007eb21  nop     dword ptr [rax+rax+00h]
0x18007eb26  mov     ebp, dword ptr [rsp+0D8h+arg_18]
0x18007eb2d  mov     rdi, [rsp+0D8h+var_20]
0x18007eb35  test    r12d, r12d
0x18007eb38  jz      short loc_18007EB65
0x18007eb3a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18007eb41  test    rax, rax
0x18007eb44  jnz     short loc_18007EB52
0x18007eb46  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18007eb4d  test    rax, rax
0x18007eb50  jz      short loc_18007EB65
0x18007eb52  xor     r9d, r9d
0x18007eb55  mov     r8d, r12d
0x18007eb58  mov     edx, r13d
0x18007eb5b  mov     ecx, 36DFDC9h
0x18007eb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb65  mov     r13, [rsp+0D8h+var_30]
0x18007eb6d  mov     r12, [rsp+0D8h+var_28]
0x18007eb75  test    esi, esi
0x18007eb77  jnz     short loc_18007EBF0
0x18007eb79  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007eb7f  test    eax, eax
0x18007eb81  jz      short loc_18007EBF0
0x18007eb83  lea     rcx, SRWLock; SRWLock
0x18007eb8a  call    cs:__imp_AcquireSRWLockExclusive
0x18007eb91  nop     dword ptr [rax+rax+00h]
0x18007eb96  cmp     cs:qword_1800B90E0, 0
0x18007eb9e  jnz     short loc_18007EBDD
0x18007eba0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007eba7  mov     cs:qword_1800B90E0, 0
0x18007ebb2  test    rax, rax
0x18007ebb5  jnz     short loc_18007EBC3
0x18007ebb7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007ebbe  test    rax, rax
0x18007ebc1  jz      short loc_18007EBDD
0x18007ebc3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007ebca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18007ebd1  lea     rcx, qword_1800B90E0
0x18007ebd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebdd  lea     rcx, SRWLock; SRWLock
0x18007ebe4  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ebeb  nop     dword ptr [rax+rax+00h]
0x18007ebf0  bt      r15d, 0Ah
0x18007ebf5  jnb     short loc_18007EC2F
0x18007ebf7  mov     eax, ebx
0x18007ebf9  mov     edx, ebx
0x18007ebfb  bts     eax, 1Fh
0x18007ebff  bt      r15d, 0Bh
0x18007ec04  cmovb   edx, eax
0x18007ec07  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18007ec0e  test    rax, rax
0x18007ec11  jnz     short loc_18007EC1F
0x18007ec13  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18007ec1a  test    rax, rax
0x18007ec1d  jz      short loc_18007EC2F
0x18007ec1f  xor     r9d, r9d
0x18007ec22  xor     r8d, r8d
0x18007ec25  mov     ecx, 36DFDC9h
0x18007ec2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec2f  mov     r15, [rsp+0D8h+var_40]
0x18007ec37  test    esi, esi
0x18007ec39  mov     rsi, [rsp+0D8h+var_18]
0x18007ec41  jnz     short loc_18007ECA3
0x18007ec43  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18007ec4a  test    rax, rax
0x18007ec4d  jz      short loc_18007EC5E
0x18007ec4f  mov     r8b, 2
0x18007ec52  mov     edx, ebx
0x18007ec54  mov     ecx, 36DFDC9h
0x18007ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec5e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18007ec65  test    rax, rax
0x18007ec68  jz      short loc_18007ECA3
0x18007ec6a  mov     [rsp+0D8h+var_A0], 1
0x18007ec73  lea     rdx, [rsp+0D8h+arg_0]
0x18007ec7b  mov     [rsp+0D8h+var_A8], 0
0x18007ec80  mov     r9d, ebp
0x18007ec83  mov     [rsp+0D8h+var_B0], 0
0x18007ec8c  xor     r8d, r8d
0x18007ec8f  mov     [rsp+0D8h+var_B8], rdx
0x18007ec94  mov     ecx, 36DFDC9h
0x18007ec99  lea     rdx, [rsp+0D8h+var_88]
0x18007ec9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eca3  add     rsp, 0C8h
0x18007ecaa  pop     rbp
0x18007ecab  pop     rbx
0x18007ecac  retn
```
