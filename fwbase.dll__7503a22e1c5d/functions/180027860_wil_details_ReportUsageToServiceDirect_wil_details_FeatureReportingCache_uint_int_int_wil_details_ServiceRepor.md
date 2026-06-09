# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180027860`
- end: `0x1800279fc`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180027700`

## callees

- `0x180025fe0`
- `0x180027860`
- `0x18002a270`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027925`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027925`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027979`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027979`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int *v11; // rax
  int v12; // r14d
  unsigned int v13; // esi
  unsigned int v14; // r15d
  int v15; // r12d
  void (__fastcall *v16)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v17)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v18; // rdx
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _BYTE v22[80]; // [rsp+38h] [rbp-50h] BYREF

  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
  v12 = *v11;
  v13 = v11[1];
  v14 = v11[2];
  v15 = v11[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v13 )
  {
    v16 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v16 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v16(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18003C478 )
    {
      qword_18003C478 = 0;
      v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v17 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v17(&qword_18003C478, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v18 = a5;
    LODWORD(v18) = a5 | 0x80000000;
    if ( !a4 )
      v18 = a5;
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v18, 0, 0);
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
0x180027860  mov     [rsp+arg_10], rbx
0x180027865  push    rbp
0x180027866  push    rsi
0x180027867  push    rdi
0x180027868  push    r12
0x18002786a  push    r13
0x18002786c  push    r14
0x18002786e  push    r15
0x180027870  sub     rsp, 50h
0x180027874  mov     [rsp+88h+var_58], r9d
0x180027879  mov     r13d, r8d
0x18002787c  mov     ebx, edx
0x18002787e  mov     rbp, rcx
0x180027881  mov     edi, [rsp+88h+arg_20]
0x180027888  mov     r8d, edi
0x18002788b  mov     rdx, rcx
0x18002788e  lea     rcx, [rsp+88h+var_50]
0x180027893  call    wil_details_FeatureReporting_RecordUsageInCache
0x180027898  mov     r14d, [rax]
0x18002789b  mov     esi, [rax+4]
0x18002789e  mov     r15d, [rax+8]
0x1800278a2  mov     r12d, [rax+10h]
0x1800278a6  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800278ad  test    rax, rax
0x1800278b0  jz      short loc_1800278CD
0x1800278b2  test    edi, edi
0x1800278b4  jz      short loc_1800278BE
0x1800278b6  lea     ecx, [rdi-64h]
0x1800278b9  cmp     ecx, 31h ; '1'
0x1800278bc  ja      short loc_1800278CD
0x1800278be  mov     r8d, 1
0x1800278c4  mov     edx, edi
0x1800278c6  mov     ecx, ebx
0x1800278c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278cd  test    r14d, r14d
0x1800278d0  jz      short loc_1800278E3
0x1800278d2  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x1800278d5  mov     edx, ebx; unsigned int
0x1800278d7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800278de  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800278e3  test    esi, esi
0x1800278e5  jz      short loc_18002790F
0x1800278e7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800278ee  test    rax, rax
0x1800278f1  jnz     short loc_1800278FF
0x1800278f3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800278fa  test    rax, rax
0x1800278fd  jz      short loc_18002790F
0x1800278ff  xor     r9d, r9d
0x180027902  mov     r8d, esi
0x180027905  mov     edx, r15d
0x180027908  mov     ecx, ebx
0x18002790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002790f  test    r12d, r12d
0x180027912  jnz     short loc_180027980
0x180027914  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002791a  test    eax, eax
0x18002791c  jz      short loc_180027980
0x18002791e  lea     rcx, SRWLock; SRWLock
0x180027925  call    cs:__imp_AcquireSRWLockExclusive
0x18002792b  cmp     cs:qword_18003C478, 0
0x180027933  jnz     short loc_180027972
0x180027935  mov     cs:qword_18003C478, 0
0x180027940  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180027947  test    rax, rax
0x18002794a  jnz     short loc_180027958
0x18002794c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180027953  test    rax, rax
0x180027956  jz      short loc_180027972
0x180027958  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002795f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180027966  lea     rcx, qword_18003C478
0x18002796d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027972  lea     rcx, SRWLock; SRWLock
0x180027979  call    cs:__imp_ReleaseSRWLockExclusive
0x18002797f  nop
0x180027980  test    r13d, r13d
0x180027983  jz      short loc_1800279B8
0x180027985  mov     edx, edi
0x180027987  bts     edx, 1Fh
0x18002798b  cmp     [rsp+88h+var_58], 0
0x180027990  cmovz   edx, edi
0x180027993  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18002799a  test    rax, rax
0x18002799d  jnz     short loc_1800279AB
0x18002799f  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800279a6  test    rax, rax
0x1800279a9  jz      short loc_1800279B8
0x1800279ab  xor     r9d, r9d
0x1800279ae  xor     r8d, r8d
0x1800279b1  mov     ecx, ebx
0x1800279b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279b8  test    r12d, r12d
0x1800279bb  jnz     short loc_1800279E2
0x1800279bd  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800279c4  test    rax, rax
0x1800279c7  jz      short loc_1800279DB
0x1800279c9  movzx   r8d, [rsp+88h+arg_38]
0x1800279d2  mov     edx, edi
0x1800279d4  mov     ecx, ebx
0x1800279d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279db  mov     eax, 1
0x1800279e0  jmp     short loc_1800279E4
0x1800279e2  xor     eax, eax
0x1800279e4  mov     rbx, [rsp+88h+arg_10]
0x1800279ec  add     rsp, 50h
0x1800279f0  pop     r15
0x1800279f2  pop     r14
0x1800279f4  pop     r13
0x1800279f6  pop     r12
0x1800279f8  pop     rdi
0x1800279f9  pop     rsi
0x1800279fa  pop     rbp
0x1800279fb  retn
```
