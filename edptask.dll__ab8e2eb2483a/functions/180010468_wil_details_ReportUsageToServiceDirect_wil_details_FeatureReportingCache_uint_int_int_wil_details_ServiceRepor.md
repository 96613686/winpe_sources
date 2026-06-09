# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180010468`
- end: `0x180010607`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010330`

## callees

- `0x18000f0b4`
- `0x180010468`
- `0x1800129c0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001057f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001057f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010533`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010533`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // r8
  int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // ebp
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = *v10;
  v13 = v10[1];
  v14 = v10[2];
  v15 = v10[4];
  v16 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v13 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18001D3E0 )
    {
      qword_18001D3E0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18001D3E0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5;
    LODWORD(v19) = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(a2, v19, 0, 0);
    }
  }
  if ( v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v16;
}

```

## disassembly

```asm
0x180010468  mov     rax, rsp
0x18001046b  mov     [rax+8], rbx
0x18001046f  mov     [rax+20h], r9d
0x180010473  mov     [rax+18h], r8d
0x180010477  push    rbp
0x180010478  push    rsi
0x180010479  push    rdi
0x18001047a  push    r12
0x18001047c  push    r13
0x18001047e  push    r14
0x180010480  push    r15
0x180010482  sub     rsp, 50h
0x180010486  mov     edi, edx
0x180010488  mov     r14, rcx
0x18001048b  mov     ebx, [rsp+88h+arg_20]
0x180010492  mov     r8d, ebx
0x180010495  mov     rdx, rcx
0x180010498  lea     rcx, [rax-58h]
0x18001049c  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800104a1  mov     r15d, [rax]
0x1800104a4  mov     esi, [rax+4]
0x1800104a7  mov     r12d, [rax+8]
0x1800104ab  mov     r13d, [rax+10h]
0x1800104af  mov     ebp, 1
0x1800104b4  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800104bb  test    rax, rax
0x1800104be  jz      short loc_1800104D8
0x1800104c0  test    ebx, ebx
0x1800104c2  jz      short loc_1800104CC
0x1800104c4  lea     ecx, [rbx-64h]
0x1800104c7  cmp     ecx, 31h ; '1'
0x1800104ca  ja      short loc_1800104D8
0x1800104cc  mov     r8d, ebp
0x1800104cf  mov     edx, ebx
0x1800104d1  mov     ecx, edi
0x1800104d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d8  test    r15d, r15d
0x1800104db  jz      short loc_1800104EE
0x1800104dd  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800104e0  mov     edx, edi; unsigned int
0x1800104e2  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800104e9  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800104ee  xor     r14d, r14d
0x1800104f1  test    esi, esi
0x1800104f3  jz      short loc_18001051D
0x1800104f5  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800104fc  test    rax, rax
0x1800104ff  jnz     short loc_18001050D
0x180010501  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180010508  test    rax, rax
0x18001050b  jz      short loc_18001051D
0x18001050d  xor     r9d, r9d
0x180010510  mov     r8d, esi
0x180010513  mov     edx, r12d
0x180010516  mov     ecx, edi
0x180010518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001051d  test    r13d, r13d
0x180010520  jnz     short loc_180010586
0x180010522  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180010528  test    eax, eax
0x18001052a  jz      short loc_180010586
0x18001052c  lea     rcx, SRWLock; SRWLock
0x180010533  call    cs:__imp_AcquireSRWLockExclusive
0x180010539  cmp     cs:qword_18001D3E0, r14
0x180010540  jnz     short loc_180010578
0x180010542  mov     cs:qword_18001D3E0, r14
0x180010549  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180010550  test    rax, rax
0x180010553  jnz     short loc_180010561
0x180010555  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001055c  test    rax, rax
0x18001055f  jz      short loc_180010578
0x180010561  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010565  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001056c  lea     rcx, qword_18001D3E0
0x180010573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010578  lea     rcx, SRWLock; SRWLock
0x18001057f  call    cs:__imp_ReleaseSRWLockExclusive
0x180010585  nop
0x180010586  cmp     [rsp+88h+arg_10], r14d
0x18001058e  jz      short loc_1800105C6
0x180010590  mov     edx, ebx
0x180010592  bts     edx, 1Fh
0x180010596  cmp     [rsp+88h+arg_18], r14d
0x18001059e  cmovz   edx, ebx
0x1800105a1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800105a8  test    rax, rax
0x1800105ab  jnz     short loc_1800105B9
0x1800105ad  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800105b4  test    rax, rax
0x1800105b7  jz      short loc_1800105C6
0x1800105b9  xor     r9d, r9d
0x1800105bc  xor     r8d, r8d
0x1800105bf  mov     ecx, edi
0x1800105c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105c6  test    r13d, r13d
0x1800105c9  jnz     short loc_1800105EA
0x1800105cb  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800105d2  test    rax, rax
0x1800105d5  jz      short loc_1800105ED
0x1800105d7  mov     r8b, [rsp+88h+arg_38]
0x1800105df  mov     edx, ebx
0x1800105e1  mov     ecx, edi
0x1800105e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e8  jmp     short loc_1800105ED
0x1800105ea  mov     ebp, r14d
0x1800105ed  mov     eax, ebp
0x1800105ef  mov     rbx, [rsp+88h+arg_0]
0x1800105f7  add     rsp, 50h
0x1800105fb  pop     r15
0x1800105fd  pop     r14
0x1800105ff  pop     r13
0x180010601  pop     r12
0x180010603  pop     rdi
0x180010604  pop     rsi
0x180010605  pop     rbp
0x180010606  retn
```
