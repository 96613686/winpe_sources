# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180023d68`
- end: `0x180023efb`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180023c90`

## callees

- `0x180022a2c`
- `0x180023d68`
- `0x180025330`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023e2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023e2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023e7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    g_wil_details_RecordSRUMFeatureUsage(27656178, a5, 1);
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
      v18(27656178, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_180052628);
    if ( !qword_180052688 )
    {
      qword_180052688 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_180052688, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_180052628);
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
      v21(27656178, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(27656178, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x180023d68  mov     [rsp+arg_18], r9d
0x180023d6d  push    rbx
0x180023d6e  push    rbp
0x180023d6f  push    rsi
0x180023d70  push    rdi
0x180023d71  push    r12
0x180023d73  push    r13
0x180023d75  push    r14
0x180023d77  push    r15
0x180023d79  sub     rsp, 58h
0x180023d7d  mov     r13d, r8d
0x180023d80  mov     rbp, rcx
0x180023d83  mov     ebx, [rsp+98h+arg_20]
0x180023d8a  mov     r8d, ebx
0x180023d8d  mov     rdx, rcx
0x180023d90  lea     rcx, [rsp+98h+var_68]
0x180023d95  call    wil_details_FeatureReporting_RecordUsageInCache
0x180023d9a  mov     r14d, [rax]
0x180023d9d  mov     edi, [rax+4]
0x180023da0  mov     r15d, [rax+8]
0x180023da4  mov     r12d, [rax+10h]
0x180023da8  mov     esi, 1
0x180023dad  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180023db4  test    rax, rax
0x180023db7  jz      short loc_180023DD4
0x180023db9  test    ebx, ebx
0x180023dbb  jz      short loc_180023DC5
0x180023dbd  lea     ecx, [rbx-64h]
0x180023dc0  cmp     ecx, 31h ; '1'
0x180023dc3  ja      short loc_180023DD4
0x180023dc5  mov     r8d, esi
0x180023dc8  mov     edx, ebx
0x180023dca  mov     ecx, 1A5FFF2h
0x180023dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd4  test    r14d, r14d
0x180023dd7  jz      short loc_180023DE8
0x180023dd9  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x180023ddc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180023de3  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180023de8  xor     ebp, ebp
0x180023dea  test    edi, edi
0x180023dec  jz      short loc_180023E19
0x180023dee  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180023df5  test    rax, rax
0x180023df8  jnz     short loc_180023E06
0x180023dfa  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180023e01  test    rax, rax
0x180023e04  jz      short loc_180023E19
0x180023e06  xor     r9d, r9d
0x180023e09  mov     r8d, edi
0x180023e0c  mov     edx, r15d
0x180023e0f  mov     ecx, 1A5FFF2h
0x180023e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e19  test    r12d, r12d
0x180023e1c  jnz     short loc_180023E82
0x180023e1e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180023e24  test    eax, eax
0x180023e26  jz      short loc_180023E82
0x180023e28  lea     rcx, stru_180052628; SRWLock
0x180023e2f  call    cs:__imp_AcquireSRWLockExclusive
0x180023e35  cmp     cs:qword_180052688, rbp
0x180023e3c  jnz     short loc_180023E74
0x180023e3e  mov     cs:qword_180052688, rbp
0x180023e45  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180023e4c  test    rax, rax
0x180023e4f  jnz     short loc_180023E5D
0x180023e51  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180023e58  test    rax, rax
0x180023e5b  jz      short loc_180023E74
0x180023e5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023e61  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180023e68  lea     rcx, qword_180052688
0x180023e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e74  lea     rcx, stru_180052628; SRWLock
0x180023e7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180023e81  nop
0x180023e82  test    r13d, r13d
0x180023e85  jz      short loc_180023EBF
0x180023e87  mov     edx, ebx
0x180023e89  bts     edx, 1Fh
0x180023e8d  cmp     [rsp+98h+arg_18], ebp
0x180023e94  cmovz   edx, ebx
0x180023e97  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180023e9e  test    rax, rax
0x180023ea1  jnz     short loc_180023EAF
0x180023ea3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180023eaa  test    rax, rax
0x180023ead  jz      short loc_180023EBF
0x180023eaf  xor     r9d, r9d
0x180023eb2  xor     r8d, r8d
0x180023eb5  mov     ecx, 1A5FFF2h
0x180023eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ebf  test    r12d, r12d
0x180023ec2  jnz     short loc_180023EE6
0x180023ec4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180023ecb  test    rax, rax
0x180023ece  jz      short loc_180023EE8
0x180023ed0  mov     r8b, [rsp+98h+arg_38]
0x180023ed8  mov     edx, ebx
0x180023eda  mov     ecx, 1A5FFF2h
0x180023edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ee4  jmp     short loc_180023EE8
0x180023ee6  mov     esi, ebp
0x180023ee8  mov     eax, esi
0x180023eea  add     rsp, 58h
0x180023eee  pop     r15
0x180023ef0  pop     r14
0x180023ef2  pop     r13
0x180023ef4  pop     r12
0x180023ef6  pop     rdi
0x180023ef7  pop     rsi
0x180023ef8  pop     rbp
0x180023ef9  pop     rbx
0x180023efa  retn
```
