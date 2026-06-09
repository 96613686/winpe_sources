# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180007a1c`
- end: `0x180007bae`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007944`

## callees

- `0x180006488`
- `0x180007a1c`
- `0x180009740`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007ae3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007ae3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b2f`

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
  unsigned int v13; // esi
  int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // r12d
  int v17; // r15d
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v20)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v21; // rdx
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = 1;
  v14 = *v10;
  v15 = v10[1];
  v16 = v10[2];
  v17 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(47350999, a5, 1);
  if ( v14 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v15 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(47350999, v16, v15, 0);
    }
  }
  if ( !v17 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800123C8 )
    {
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800123C8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_1800123C8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v21 = a5;
    LODWORD(v21) = a5 | 0x80000000;
    if ( !a4 )
      v21 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(47350999, v21, 0, 0);
    }
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(47350999, a5, v12);
  }
  return v13;
}

```

## disassembly

```asm
0x180007a1c  mov     [rsp+arg_18], r9d
0x180007a21  push    rbx
0x180007a22  push    rbp
0x180007a23  push    rsi
0x180007a24  push    rdi
0x180007a25  push    r12
0x180007a27  push    r13
0x180007a29  push    r14
0x180007a2b  push    r15
0x180007a2d  sub     rsp, 58h
0x180007a31  mov     ebx, [rsp+98h+arg_20]
0x180007a38  mov     r13d, r8d
0x180007a3b  mov     rbp, rcx
0x180007a3e  mov     rdx, rcx
0x180007a41  mov     r8d, ebx
0x180007a44  lea     rcx, [rsp+98h+var_68]
0x180007a49  call    wil_details_FeatureReporting_RecordUsageInCache
0x180007a4e  mov     esi, 1
0x180007a53  mov     r14d, [rax]
0x180007a56  mov     edi, [rax+4]
0x180007a59  mov     r12d, [rax+8]
0x180007a5d  mov     r15d, [rax+10h]
0x180007a61  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180007a68  test    rax, rax
0x180007a6b  jz      short loc_180007A88
0x180007a6d  test    ebx, ebx
0x180007a6f  jz      short loc_180007A79
0x180007a71  lea     ecx, [rbx-64h]
0x180007a74  cmp     ecx, 31h ; '1'
0x180007a77  ja      short loc_180007A88
0x180007a79  mov     r8d, esi
0x180007a7c  mov     edx, ebx
0x180007a7e  mov     ecx, 2D284D7h
0x180007a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a88  test    r14d, r14d
0x180007a8b  jz      short loc_180007A9C
0x180007a8d  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x180007a90  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180007a97  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180007a9c  xor     ebp, ebp
0x180007a9e  test    edi, edi
0x180007aa0  jz      short loc_180007ACD
0x180007aa2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007aa9  test    rax, rax
0x180007aac  jnz     short loc_180007ABA
0x180007aae  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007ab5  test    rax, rax
0x180007ab8  jz      short loc_180007ACD
0x180007aba  xor     r9d, r9d
0x180007abd  mov     r8d, edi
0x180007ac0  mov     edx, r12d
0x180007ac3  mov     ecx, 2D284D7h
0x180007ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007acd  test    r15d, r15d
0x180007ad0  jnz     short loc_180007B35
0x180007ad2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180007ad8  test    eax, eax
0x180007ada  jz      short loc_180007B35
0x180007adc  lea     rcx, SRWLock; SRWLock
0x180007ae3  call    cs:__imp_AcquireSRWLockExclusive
0x180007ae9  cmp     cs:qword_1800123C8, rbp
0x180007af0  jnz     short loc_180007B28
0x180007af2  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007af9  mov     cs:qword_1800123C8, rbp
0x180007b00  test    rax, rax
0x180007b03  jnz     short loc_180007B11
0x180007b05  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007b0c  test    rax, rax
0x180007b0f  jz      short loc_180007B28
0x180007b11  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007b15  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180007b1c  lea     rcx, qword_1800123C8
0x180007b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b28  lea     rcx, SRWLock; SRWLock
0x180007b2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007b35  test    r13d, r13d
0x180007b38  jz      short loc_180007B72
0x180007b3a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007b41  mov     edx, ebx
0x180007b43  bts     edx, 1Fh
0x180007b47  cmp     [rsp+98h+arg_18], ebp
0x180007b4e  cmovz   edx, ebx
0x180007b51  test    rax, rax
0x180007b54  jnz     short loc_180007B62
0x180007b56  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007b5d  test    rax, rax
0x180007b60  jz      short loc_180007B72
0x180007b62  xor     r9d, r9d
0x180007b65  xor     r8d, r8d
0x180007b68  mov     ecx, 2D284D7h
0x180007b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b72  test    r15d, r15d
0x180007b75  jnz     short loc_180007B99
0x180007b77  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180007b7e  test    rax, rax
0x180007b81  jz      short loc_180007B9B
0x180007b83  mov     r8b, [rsp+98h+arg_38]
0x180007b8b  mov     edx, ebx
0x180007b8d  mov     ecx, 2D284D7h
0x180007b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b97  jmp     short loc_180007B9B
0x180007b99  mov     esi, ebp
0x180007b9b  mov     eax, esi
0x180007b9d  add     rsp, 58h
0x180007ba1  pop     r15
0x180007ba3  pop     r14
0x180007ba5  pop     r13
0x180007ba7  pop     r12
0x180007ba9  pop     rdi
0x180007baa  pop     rsi
0x180007bab  pop     rbp
0x180007bac  pop     rbx
0x180007bad  retn
```
