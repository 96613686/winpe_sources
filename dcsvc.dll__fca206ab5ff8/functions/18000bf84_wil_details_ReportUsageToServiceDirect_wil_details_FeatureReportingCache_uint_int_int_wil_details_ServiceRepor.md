# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000bf84`
- end: `0x18000c117`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, __int64, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000beac`

## callees

- `0x18000bcf0`
- `0x18000bf84`
- `0x18000e55c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c097`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c097`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c04b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c04b`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // r12d
  unsigned int v17; // esi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(__int64, __int64, _QWORD, _QWORD); // rax
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  v17 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(56698136, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v14 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(56698136, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18001B5D0 )
    {
      qword_18001B5D0 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_18001B5D0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(56698136, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(56698136, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x18000bf84  mov     [rsp+arg_18], r9d
0x18000bf89  push    rbx
0x18000bf8a  push    rbp
0x18000bf8b  push    rsi
0x18000bf8c  push    rdi
0x18000bf8d  push    r12
0x18000bf8f  push    r13
0x18000bf91  push    r14
0x18000bf93  push    r15
0x18000bf95  sub     rsp, 58h
0x18000bf99  mov     r13d, r8d
0x18000bf9c  mov     rbp, rcx
0x18000bf9f  mov     ebx, [rsp+98h+arg_20]
0x18000bfa6  mov     r8d, ebx
0x18000bfa9  mov     rdx, rcx
0x18000bfac  lea     rcx, [rsp+98h+var_68]
0x18000bfb1  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000bfb6  mov     r14d, [rax]
0x18000bfb9  mov     edi, [rax+4]
0x18000bfbc  mov     r15d, [rax+8]
0x18000bfc0  mov     r12d, [rax+10h]
0x18000bfc4  mov     esi, 1
0x18000bfc9  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000bfd0  test    rax, rax
0x18000bfd3  jz      short loc_18000BFF0
0x18000bfd5  test    ebx, ebx
0x18000bfd7  jz      short loc_18000BFE1
0x18000bfd9  lea     ecx, [rbx-64h]
0x18000bfdc  cmp     ecx, 31h ; '1'
0x18000bfdf  ja      short loc_18000BFF0
0x18000bfe1  mov     r8d, esi
0x18000bfe4  mov     edx, ebx
0x18000bfe6  mov     ecx, 3612518h
0x18000bfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff0  test    r14d, r14d
0x18000bff3  jz      short loc_18000C004
0x18000bff5  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x18000bff8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000bfff  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c004  xor     ebp, ebp
0x18000c006  test    edi, edi
0x18000c008  jz      short loc_18000C035
0x18000c00a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c011  test    rax, rax
0x18000c014  jnz     short loc_18000C022
0x18000c016  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c01d  test    rax, rax
0x18000c020  jz      short loc_18000C035
0x18000c022  xor     r9d, r9d
0x18000c025  mov     r8d, edi
0x18000c028  mov     edx, r15d
0x18000c02b  mov     ecx, 3612518h
0x18000c030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c035  test    r12d, r12d
0x18000c038  jnz     short loc_18000C09E
0x18000c03a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c040  test    eax, eax
0x18000c042  jz      short loc_18000C09E
0x18000c044  lea     rcx, SRWLock; SRWLock
0x18000c04b  call    cs:__imp_AcquireSRWLockExclusive
0x18000c051  cmp     cs:qword_18001B5D0, rbp
0x18000c058  jnz     short loc_18000C090
0x18000c05a  mov     cs:qword_18001B5D0, rbp
0x18000c061  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000c068  test    rax, rax
0x18000c06b  jnz     short loc_18000C079
0x18000c06d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000c074  test    rax, rax
0x18000c077  jz      short loc_18000C090
0x18000c079  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c07d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000c084  lea     rcx, qword_18001B5D0
0x18000c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c090  lea     rcx, SRWLock; SRWLock
0x18000c097  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c09d  nop
0x18000c09e  test    r13d, r13d
0x18000c0a1  jz      short loc_18000C0DB
0x18000c0a3  mov     edx, ebx
0x18000c0a5  bts     edx, 1Fh
0x18000c0a9  cmp     [rsp+98h+arg_18], ebp
0x18000c0b0  cmovz   edx, ebx
0x18000c0b3  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c0ba  test    rax, rax
0x18000c0bd  jnz     short loc_18000C0CB
0x18000c0bf  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c0c6  test    rax, rax
0x18000c0c9  jz      short loc_18000C0DB
0x18000c0cb  xor     r9d, r9d
0x18000c0ce  xor     r8d, r8d
0x18000c0d1  mov     ecx, 3612518h
0x18000c0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0db  test    r12d, r12d
0x18000c0de  jnz     short loc_18000C102
0x18000c0e0  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000c0e7  test    rax, rax
0x18000c0ea  jz      short loc_18000C104
0x18000c0ec  mov     r8b, [rsp+98h+arg_38]
0x18000c0f4  mov     edx, ebx
0x18000c0f6  mov     ecx, 3612518h
0x18000c0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c100  jmp     short loc_18000C104
0x18000c102  mov     esi, ebp
0x18000c104  mov     eax, esi
0x18000c106  add     rsp, 58h
0x18000c10a  pop     r15
0x18000c10c  pop     r14
0x18000c10e  pop     r13
0x18000c110  pop     r12
0x18000c112  pop     rdi
0x18000c113  pop     rsi
0x18000c114  pop     rbp
0x18000c115  pop     rbx
0x18000c116  retn
```
