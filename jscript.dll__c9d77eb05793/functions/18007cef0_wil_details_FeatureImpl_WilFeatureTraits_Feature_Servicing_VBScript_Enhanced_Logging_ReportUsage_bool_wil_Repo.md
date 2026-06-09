# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18007cef0`
- end: `0x18007d3b5`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1221`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18007e100`

## callees

- `0x180059cd4`
- `0x180073540`
- `0x180078ab0`
- `0x18007cef0`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007d0c4`
- `msvcrt!memcpy_s` at `0x18007d141`
- `msvcrt!memcpy_s` at `0x18007d0c4`
- `msvcrt!memcpy_s` at `0x18007d141`
- `KERNEL32!HeapFree` at `0x18007d0eb`
- `KERNEL32!HeapFree` at `0x18007d0eb`
- `KERNEL32!SetLastError` at `0x18007d09f`
- `KERNEL32!SetLastError` at `0x18007d110`
- `KERNEL32!SetLastError` at `0x18007d1d4`
- `KERNEL32!SetLastError` at `0x18007d1e3`
- `KERNEL32!SetLastError` at `0x18007d09f`
- `KERNEL32!SetLastError` at `0x18007d110`
- `KERNEL32!SetLastError` at `0x18007d1d4`
- `KERNEL32!SetLastError` at `0x18007d1e3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007d1c3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18007d1c3`
- `KERNEL32!GetLastError` at `0x18007d07b`
- `KERNEL32!GetLastError` at `0x18007d174`
- `KERNEL32!GetLastError` at `0x18007d1a2`
- `KERNEL32!GetLastError` at `0x18007d07b`
- `KERNEL32!GetLastError` at `0x18007d174`
- `KERNEL32!GetLastError` at `0x18007d1a2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d234`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d2f2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d234`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007d2f2`
- `KERNEL32!CloseThreadpoolTimer` at `0x18007d1cc`
- `KERNEL32!CloseThreadpoolTimer` at `0x18007d1cc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007cfe3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007d29e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007cfe3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007d29e`
- `KERNEL32!SetThreadpoolTimer` at `0x18007d1b5`
- `KERNEL32!SetThreadpoolTimer` at `0x18007d212`
- `KERNEL32!SetThreadpoolTimer` at `0x18007d1b5`
- `KERNEL32!SetThreadpoolTimer` at `0x18007d212`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007d18d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18007d18d`
- `KERNEL32!GetProcessHeap` at `0x18007d0dd`
- `KERNEL32!GetProcessHeap` at `0x18007d0dd`

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
    v16 = qword_1800B70E8;
    v17 = qword_1800B70F0;
    v18 = qword_1800B70F0 - (_QWORD)qword_1800B70E0;
    Source[0] = 57540041;
    Source[1] = v8;
    if ( (_BYTE *)qword_1800B70E8 - (_BYTE *)qword_1800B70E0 + 16 >= (unsigned __int64)(qword_1800B70F0
                                                                                      - (_QWORD)qword_1800B70E0) )
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
          if ( !byte_1800B70D8 )
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
              byte_1800B70D8 = 1;
            }
          }
          v9 = v46;
          v13 = v45;
          goto LABEL_31;
        }
        v25 = (_BYTE *)qword_1800B70E8 - (_BYTE *)qword_1800B70E0;
        memcpy_s(v23, v21, qword_1800B70E0, (_BYTE *)qword_1800B70E8 - (_BYTE *)qword_1800B70E0);
        v26 = qword_1800B70F8;
        qword_1800B70F8 = v24;
        if ( v26 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v26);
        }
        qword_1800B70E0 = v24;
        qword_1800B70E8 = &v24[v25];
        qword_1800B70F0 = (__int64)&v24[v21];
        SetLastError(LastError);
        v17 = qword_1800B70F0;
        v16 = qword_1800B70E8;
      }
    }
    v28 = 0;
    if ( (unsigned __int64)v16 < v17 )
      v28 = v17 - (_QWORD)v16;
    memcpy_s(v16, v28, Source, 0x10u);
    qword_1800B70E8 = (char *)qword_1800B70E8 + 16;
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
    if ( !qword_1800B7128 )
    {
      v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B7128 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v36(&qword_1800B7128, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18007cef0  mov     r11, rsp
0x18007cef3  mov     [r11+20h], r9
0x18007cef7  mov     [r11+18h], r8b
0x18007cefb  push    rbx
0x18007cefc  push    rbp
0x18007cefd  sub     rsp, 0C8h
0x18007cf04  mov     rax, cs:Feature_Servicing_VBScript_Enhanced_Logging__descriptor
0x18007cf0b  mov     [r11-18h], rsi
0x18007cf0f  mov     [r11-20h], rdi
0x18007cf13  mov     rdi, rcx
0x18007cf16  mov     [r11-28h], r12
0x18007cf1a  mov     [r11-30h], r13
0x18007cf1e  mov     [r11-40h], r15
0x18007cf22  mov     r15d, [rax]
0x18007cf25  movzx   ebx, dl
0x18007cf28  test    r15b, 4
0x18007cf2c  jnz     short loc_18007CF45
0x18007cf2e  lea     rdx, [r11+20h]
0x18007cf32  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetCachedFeatureEnabledState(void)
0x18007cf37  mov     r8, [rax]
0x18007cf3a  mov     [rsp+0D8h+arg_18], r8
0x18007cf42  mov     r15d, r8d
0x18007cf45  xor     eax, eax
0x18007cf47  mov     dword ptr [rsp+0D8h+arg_18], ebx
0x18007cf4e  mov     [rsp+0D8h+var_88], eax
0x18007cf52  lea     rcx, [rsp+0D8h+var_68]
0x18007cf57  mov     eax, ebx
0x18007cf59  mov     [rsp+0D8h+var_84], 2
0x18007cf60  xor     eax, 1
0x18007cf63  mov     [rsp+0D8h+arg_0], 3
0x18007cf6e  mov     ebp, ebx
0x18007cf70  add     rdi, 8
0x18007cf74  mov     rdx, rdi
0x18007cf77  lea     ebx, ds:2[rax*4]
0x18007cf7e  mov     r8d, ebx
0x18007cf81  mov     [rsp+0D8h+arg_10], ebx
0x18007cf88  call    wil_details_FeatureReporting_RecordUsageInCache
0x18007cf8d  cmp     dword ptr [rax], 0
0x18007cf90  mov     esi, [rax+10h]
0x18007cf93  mov     r12d, [rax+4]
0x18007cf97  mov     r13d, [rax+8]
0x18007cf9b  mov     [rsp+0D8h+arg_8], esi
0x18007cfa2  jz      loc_18007D241
0x18007cfa8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007cfae  test    eax, eax
0x18007cfb0  jz      loc_18007D241
0x18007cfb6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007cfbd  jnz     loc_18007D241
0x18007cfc3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007cfca  test    rax, rax
0x18007cfcd  jz      short loc_18007CFDC
0x18007cfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfd4  test    al, al
0x18007cfd6  jnz     loc_18007D241
0x18007cfdc  lea     rcx, SRWLock; SRWLock
0x18007cfe3  call    cs:__imp_AcquireSRWLockExclusive
0x18007cfe9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007cfef  test    eax, eax
0x18007cff1  jz      loc_18007D22D
0x18007cff7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18007cffe  jnz     loc_18007D22D
0x18007d004  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18007d00b  test    rax, rax
0x18007d00e  jz      short loc_18007D01D
0x18007d010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d015  test    al, al
0x18007d017  jnz     loc_18007D22D
0x18007d01d  mov     r10, cs:qword_1800B70E8
0x18007d024  mov     r8, cs:qword_1800B70F0
0x18007d02b  mov     rax, r10
0x18007d02e  sub     rax, cs:qword_1800B70E0
0x18007d035  mov     rdx, r8
0x18007d038  sub     rdx, cs:qword_1800B70E0
0x18007d03f  add     rax, 10h
0x18007d043  mov     [rsp+0D8h+var_38], r14
0x18007d04b  mov     [rsp+0D8h+Source], 36DFDC9h
0x18007d054  mov     [rsp+0D8h+var_70], rdi
0x18007d059  cmp     rax, rdx
0x18007d05c  jb      loc_18007D124
0x18007d062  lea     rax, [rdx+rdx]
0x18007d066  mov     ebx, 10h
0x18007d06b  cmp     rax, rbx
0x18007d06e  cmova   rbx, rax
0x18007d072  cmp     rdx, rbx
0x18007d075  jnb     loc_18007D124
0x18007d07b  call    cs:__imp_GetLastError
0x18007d081  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18007d085  xor     ecx, ecx; dwFlags
0x18007d087  mov     esi, eax
0x18007d089  lea     r14, [rbx+40h]
0x18007d08d  mov     rdx, r14; dwBytes
0x18007d090  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007d095  mov     rbx, rax
0x18007d098  test    rax, rax
0x18007d09b  jnz     short loc_18007D0AA
0x18007d09d  mov     ecx, esi; dwErrCode
0x18007d09f  call    cs:__imp_SetLastError
0x18007d0a5  jmp     loc_18007D14F
0x18007d0aa  mov     r8, cs:qword_1800B70E0; Source
0x18007d0b1  mov     rdx, r14; DestinationSize
0x18007d0b4  mov     rdi, cs:qword_1800B70E8
0x18007d0bb  mov     rcx, rbx; Destination
0x18007d0be  sub     rdi, r8
0x18007d0c1  mov     r9, rdi; SourceSize
0x18007d0c4  call    cs:__imp_memcpy_s
0x18007d0ca  mov     rbp, cs:qword_1800B70F8
0x18007d0d1  mov     cs:qword_1800B70F8, rbx
0x18007d0d8  test    rbp, rbp
0x18007d0db  jz      short loc_18007D0F1
0x18007d0dd  call    cs:__imp_GetProcessHeap
0x18007d0e3  mov     r8, rbp; lpMem
0x18007d0e6  xor     edx, edx; dwFlags
0x18007d0e8  mov     rcx, rax; hHeap
0x18007d0eb  call    cs:__imp_HeapFree
0x18007d0f1  lea     rax, [rdi+rbx]
0x18007d0f5  mov     cs:qword_1800B70E0, rbx
0x18007d0fc  mov     cs:qword_1800B70E8, rax
0x18007d103  mov     ecx, esi; dwErrCode
0x18007d105  lea     rax, [r14+rbx]
0x18007d109  mov     cs:qword_1800B70F0, rax
0x18007d110  call    cs:__imp_SetLastError
0x18007d116  mov     r8, cs:qword_1800B70F0
0x18007d11d  mov     r10, cs:qword_1800B70E8
0x18007d124  mov     rax, r8
0x18007d127  xor     edx, edx
0x18007d129  sub     rax, r10
0x18007d12c  mov     r9d, 10h; SourceSize
0x18007d132  cmp     r10, r8
0x18007d135  mov     rcx, r10; Destination
0x18007d138  lea     r8, [rsp+0D8h+Source]; Source
0x18007d13d  cmovb   rdx, rax; DestinationSize
0x18007d141  call    cs:__imp_memcpy_s
0x18007d147  add     cs:qword_1800B70E8, 10h
0x18007d14f  cmp     cs:byte_1800B70D8, 0
0x18007d156  mov     r14, [rsp+0D8h+var_38]
0x18007d15e  jnz     loc_18007D21F
0x18007d164  mov     rcx, cs:pti
0x18007d16b  test    rcx, rcx
0x18007d16e  jnz     loc_18007D1F5
0x18007d174  call    cs:__imp_GetLastError
0x18007d17a  xor     r8d, r8d; pcbe
0x18007d17d  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18007d184  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18007d18b  mov     esi, eax
0x18007d18d  call    cs:__imp_CreateThreadpoolTimer
0x18007d193  mov     rdi, cs:pti
0x18007d19a  mov     rbp, rax
0x18007d19d  test    rdi, rdi
0x18007d1a0  jz      short loc_18007D1DA
0x18007d1a2  call    cs:__imp_GetLastError
0x18007d1a8  xor     r9d, r9d; msWindowLength
0x18007d1ab  xor     r8d, r8d; msPeriod
0x18007d1ae  xor     edx, edx; pftDueTime
0x18007d1b0  mov     rcx, rdi; pti
0x18007d1b3  mov     ebx, eax
0x18007d1b5  call    cs:__imp_SetThreadpoolTimer
0x18007d1bb  mov     edx, 1; fCancelPendingCallbacks
0x18007d1c0  mov     rcx, rdi; pti
0x18007d1c3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007d1c9  mov     rcx, rdi; pti
0x18007d1cc  call    cs:__imp_CloseThreadpoolTimer
0x18007d1d2  mov     ecx, ebx; dwErrCode
0x18007d1d4  call    cs:__imp_SetLastError
0x18007d1da  mov     ecx, esi; dwErrCode
0x18007d1dc  mov     cs:pti, rbp
0x18007d1e3  call    cs:__imp_SetLastError
0x18007d1e9  mov     rcx, cs:pti; pti
0x18007d1f0  test    rcx, rcx
0x18007d1f3  jz      short loc_18007D21F
0x18007d1f5  mov     rax, 0FFFFFFFF4D2FA200h
0x18007d1ff  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18007d204  mov     r9d, 124F8h; msWindowLength
0x18007d20a  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18007d20f  xor     r8d, r8d; msPeriod
0x18007d212  call    cs:__imp_SetThreadpoolTimer
0x18007d218  mov     cs:byte_1800B70D8, 1
0x18007d21f  mov     ebx, [rsp+0D8h+arg_10]
0x18007d226  mov     esi, [rsp+0D8h+arg_8]
0x18007d22d  lea     rcx, SRWLock; SRWLock
0x18007d234  call    cs:__imp_ReleaseSRWLockExclusive
0x18007d23a  mov     ebp, dword ptr [rsp+0D8h+arg_18]
0x18007d241  mov     rdi, [rsp+0D8h+var_20]
0x18007d249  test    r12d, r12d
0x18007d24c  jz      short loc_18007D279
0x18007d24e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18007d255  test    rax, rax
0x18007d258  jnz     short loc_18007D266
0x18007d25a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18007d261  test    rax, rax
0x18007d264  jz      short loc_18007D279
0x18007d266  xor     r9d, r9d
0x18007d269  mov     r8d, r12d
0x18007d26c  mov     edx, r13d
0x18007d26f  mov     ecx, 36DFDC9h
0x18007d274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d279  mov     r13, [rsp+0D8h+var_30]
0x18007d281  mov     r12, [rsp+0D8h+var_28]
0x18007d289  test    esi, esi
0x18007d28b  jnz     short loc_18007D2F8
0x18007d28d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007d293  test    eax, eax
0x18007d295  jz      short loc_18007D2F8
0x18007d297  lea     rcx, SRWLock; SRWLock
0x18007d29e  call    cs:__imp_AcquireSRWLockExclusive
0x18007d2a4  cmp     cs:qword_1800B7128, 0
0x18007d2ac  jnz     short loc_18007D2EB
0x18007d2ae  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007d2b5  mov     cs:qword_1800B7128, 0
0x18007d2c0  test    rax, rax
0x18007d2c3  jnz     short loc_18007D2D1
0x18007d2c5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007d2cc  test    rax, rax
0x18007d2cf  jz      short loc_18007D2EB
0x18007d2d1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007d2d8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18007d2df  lea     rcx, qword_1800B7128
0x18007d2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d2eb  lea     rcx, SRWLock; SRWLock
0x18007d2f2  call    cs:__imp_ReleaseSRWLockExclusive
0x18007d2f8  bt      r15d, 0Ah
0x18007d2fd  jnb     short loc_18007D337
0x18007d2ff  mov     eax, ebx
0x18007d301  mov     edx, ebx
0x18007d303  bts     eax, 1Fh
0x18007d307  bt      r15d, 0Bh
0x18007d30c  cmovb   edx, eax
0x18007d30f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18007d316  test    rax, rax
0x18007d319  jnz     short loc_18007D327
0x18007d31b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18007d322  test    rax, rax
0x18007d325  jz      short loc_18007D337
0x18007d327  xor     r9d, r9d
0x18007d32a  xor     r8d, r8d
0x18007d32d  mov     ecx, 36DFDC9h
0x18007d332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d337  mov     r15, [rsp+0D8h+var_40]
0x18007d33f  test    esi, esi
0x18007d341  mov     rsi, [rsp+0D8h+var_18]
0x18007d349  jnz     short loc_18007D3AB
0x18007d34b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18007d352  test    rax, rax
0x18007d355  jz      short loc_18007D366
0x18007d357  mov     r8b, 2
0x18007d35a  mov     edx, ebx
0x18007d35c  mov     ecx, 36DFDC9h
0x18007d361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d366  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18007d36d  test    rax, rax
0x18007d370  jz      short loc_18007D3AB
0x18007d372  mov     [rsp+0D8h+var_A0], 1
0x18007d37b  lea     rdx, [rsp+0D8h+arg_0]
0x18007d383  mov     [rsp+0D8h+var_A8], 0
0x18007d388  mov     r9d, ebp
0x18007d38b  mov     [rsp+0D8h+var_B0], 0
0x18007d394  xor     r8d, r8d
0x18007d397  mov     [rsp+0D8h+var_B8], rdx
0x18007d39c  mov     ecx, 36DFDC9h
0x18007d3a1  lea     rdx, [rsp+0D8h+var_88]
0x18007d3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3ab  add     rsp, 0C8h
0x18007d3b2  pop     rbp
0x18007d3b3  pop     rbx
0x18007d3b4  retn
```
