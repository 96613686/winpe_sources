# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x140034840`
- end: `0x1400349d3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140034768`

## callees

- `0x1400345ac`
- `0x140034840`
- `0x140034a18`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034953`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034953`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140034907`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140034907`

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
  void (__fastcall *v19)(__int64 *, void (*)(), __int64); // rax
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
    g_wil_details_RecordSRUMFeatureUsage(43378192, a5, 1);
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
      v18(43378192, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1400758F0 )
    {
      qword_1400758F0 = 0;
      v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_1400758F0, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
      v21(43378192, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(43378192, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x140034840  mov     [rsp+arg_18], r9d
0x140034845  push    rbx
0x140034846  push    rbp
0x140034847  push    rsi
0x140034848  push    rdi
0x140034849  push    r12
0x14003484b  push    r13
0x14003484d  push    r14
0x14003484f  push    r15
0x140034851  sub     rsp, 58h
0x140034855  mov     r13d, r8d
0x140034858  mov     rbp, rcx
0x14003485b  mov     ebx, [rsp+98h+arg_20]
0x140034862  mov     r8d, ebx
0x140034865  mov     rdx, rcx
0x140034868  lea     rcx, [rsp+98h+var_68]
0x14003486d  call    wil_details_FeatureReporting_RecordUsageInCache
0x140034872  mov     r14d, [rax]
0x140034875  mov     edi, [rax+4]
0x140034878  mov     r15d, [rax+8]
0x14003487c  mov     r12d, [rax+10h]
0x140034880  mov     esi, 1
0x140034885  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14003488c  test    rax, rax
0x14003488f  jz      short loc_1400348AC
0x140034891  test    ebx, ebx
0x140034893  jz      short loc_14003489D
0x140034895  lea     ecx, [rbx-64h]
0x140034898  cmp     ecx, 31h ; '1'
0x14003489b  ja      short loc_1400348AC
0x14003489d  mov     r8d, esi
0x1400348a0  mov     edx, ebx
0x1400348a2  mov     ecx, 295E610h
0x1400348a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400348ac  test    r14d, r14d
0x1400348af  jz      short loc_1400348C0
0x1400348b1  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x1400348b4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1400348bb  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1400348c0  xor     ebp, ebp
0x1400348c2  test    edi, edi
0x1400348c4  jz      short loc_1400348F1
0x1400348c6  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400348cd  test    rax, rax
0x1400348d0  jnz     short loc_1400348DE
0x1400348d2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400348d9  test    rax, rax
0x1400348dc  jz      short loc_1400348F1
0x1400348de  xor     r9d, r9d
0x1400348e1  mov     r8d, edi
0x1400348e4  mov     edx, r15d
0x1400348e7  mov     ecx, 295E610h
0x1400348ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400348f1  test    r12d, r12d
0x1400348f4  jnz     short loc_14003495A
0x1400348f6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400348fc  test    eax, eax
0x1400348fe  jz      short loc_14003495A
0x140034900  lea     rcx, SRWLock; SRWLock
0x140034907  call    cs:__imp_AcquireSRWLockExclusive
0x14003490d  cmp     cs:qword_1400758F0, rbp
0x140034914  jnz     short loc_14003494C
0x140034916  mov     cs:qword_1400758F0, rbp
0x14003491d  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x140034924  test    rax, rax
0x140034927  jnz     short loc_140034935
0x140034929  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140034930  test    rax, rax
0x140034933  jz      short loc_14003494C
0x140034935  or      r8, 0FFFFFFFFFFFFFFFFh
0x140034939  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x140034940  lea     rcx, qword_1400758F0
0x140034947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003494c  lea     rcx, SRWLock; SRWLock
0x140034953  call    cs:__imp_ReleaseSRWLockExclusive
0x140034959  nop
0x14003495a  test    r13d, r13d
0x14003495d  jz      short loc_140034997
0x14003495f  mov     edx, ebx
0x140034961  bts     edx, 1Fh
0x140034965  cmp     [rsp+98h+arg_18], ebp
0x14003496c  cmovz   edx, ebx
0x14003496f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140034976  test    rax, rax
0x140034979  jnz     short loc_140034987
0x14003497b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140034982  test    rax, rax
0x140034985  jz      short loc_140034997
0x140034987  xor     r9d, r9d
0x14003498a  xor     r8d, r8d
0x14003498d  mov     ecx, 295E610h
0x140034992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034997  test    r12d, r12d
0x14003499a  jnz     short loc_1400349BE
0x14003499c  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1400349a3  test    rax, rax
0x1400349a6  jz      short loc_1400349C0
0x1400349a8  mov     r8b, [rsp+98h+arg_38]
0x1400349b0  mov     edx, ebx
0x1400349b2  mov     ecx, 295E610h
0x1400349b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400349bc  jmp     short loc_1400349C0
0x1400349be  mov     esi, ebp
0x1400349c0  mov     eax, esi
0x1400349c2  add     rsp, 58h
0x1400349c6  pop     r15
0x1400349c8  pop     r14
0x1400349ca  pop     r13
0x1400349cc  pop     r12
0x1400349ce  pop     rdi
0x1400349cf  pop     rsi
0x1400349d0  pop     rbp
0x1400349d1  pop     rbx
0x1400349d2  retn
```
