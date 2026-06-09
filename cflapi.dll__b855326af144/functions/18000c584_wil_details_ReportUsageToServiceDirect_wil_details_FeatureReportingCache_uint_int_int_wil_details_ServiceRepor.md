# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000c584`
- end: `0x18000c723`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c44c`

## callees

- `0x18000ae80`
- `0x18000c584`
- `0x180012580`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c69b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c69b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c64f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c64f`

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
    if ( !qword_18003F550 )
    {
      qword_18003F550 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18003F550, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000c584  mov     rax, rsp
0x18000c587  mov     [rax+8], rbx
0x18000c58b  mov     [rax+20h], r9d
0x18000c58f  mov     [rax+18h], r8d
0x18000c593  push    rbp
0x18000c594  push    rsi
0x18000c595  push    rdi
0x18000c596  push    r12
0x18000c598  push    r13
0x18000c59a  push    r14
0x18000c59c  push    r15
0x18000c59e  sub     rsp, 50h
0x18000c5a2  mov     edi, edx
0x18000c5a4  mov     r14, rcx
0x18000c5a7  mov     ebx, [rsp+88h+arg_20]
0x18000c5ae  mov     r8d, ebx
0x18000c5b1  mov     rdx, rcx
0x18000c5b4  lea     rcx, [rax-58h]
0x18000c5b8  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c5bd  mov     r15d, [rax]
0x18000c5c0  mov     esi, [rax+4]
0x18000c5c3  mov     r12d, [rax+8]
0x18000c5c7  mov     r13d, [rax+10h]
0x18000c5cb  mov     ebp, 1
0x18000c5d0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c5d7  test    rax, rax
0x18000c5da  jz      short loc_18000C5F4
0x18000c5dc  test    ebx, ebx
0x18000c5de  jz      short loc_18000C5E8
0x18000c5e0  lea     ecx, [rbx-64h]
0x18000c5e3  cmp     ecx, 31h ; '1'
0x18000c5e6  ja      short loc_18000C5F4
0x18000c5e8  mov     r8d, ebp
0x18000c5eb  mov     edx, ebx
0x18000c5ed  mov     ecx, edi
0x18000c5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f4  test    r15d, r15d
0x18000c5f7  jz      short loc_18000C60A
0x18000c5f9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000c5fc  mov     edx, edi; unsigned int
0x18000c5fe  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c605  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c60a  xor     r14d, r14d
0x18000c60d  test    esi, esi
0x18000c60f  jz      short loc_18000C639
0x18000c611  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c618  test    rax, rax
0x18000c61b  jnz     short loc_18000C629
0x18000c61d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c624  test    rax, rax
0x18000c627  jz      short loc_18000C639
0x18000c629  xor     r9d, r9d
0x18000c62c  mov     r8d, esi
0x18000c62f  mov     edx, r12d
0x18000c632  mov     ecx, edi
0x18000c634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c639  test    r13d, r13d
0x18000c63c  jnz     short loc_18000C6A2
0x18000c63e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c644  test    eax, eax
0x18000c646  jz      short loc_18000C6A2
0x18000c648  lea     rcx, SRWLock; SRWLock
0x18000c64f  call    cs:__imp_AcquireSRWLockExclusive
0x18000c655  cmp     cs:qword_18003F550, r14
0x18000c65c  jnz     short loc_18000C694
0x18000c65e  mov     cs:qword_18003F550, r14
0x18000c665  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000c66c  test    rax, rax
0x18000c66f  jnz     short loc_18000C67D
0x18000c671  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000c678  test    rax, rax
0x18000c67b  jz      short loc_18000C694
0x18000c67d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c681  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000c688  lea     rcx, qword_18003F550
0x18000c68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c694  lea     rcx, SRWLock; SRWLock
0x18000c69b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c6a1  nop
0x18000c6a2  cmp     [rsp+88h+arg_10], r14d
0x18000c6aa  jz      short loc_18000C6E2
0x18000c6ac  mov     edx, ebx
0x18000c6ae  bts     edx, 1Fh
0x18000c6b2  cmp     [rsp+88h+arg_18], r14d
0x18000c6ba  cmovz   edx, ebx
0x18000c6bd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c6c4  test    rax, rax
0x18000c6c7  jnz     short loc_18000C6D5
0x18000c6c9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c6d0  test    rax, rax
0x18000c6d3  jz      short loc_18000C6E2
0x18000c6d5  xor     r9d, r9d
0x18000c6d8  xor     r8d, r8d
0x18000c6db  mov     ecx, edi
0x18000c6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6e2  test    r13d, r13d
0x18000c6e5  jnz     short loc_18000C706
0x18000c6e7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000c6ee  test    rax, rax
0x18000c6f1  jz      short loc_18000C709
0x18000c6f3  mov     r8b, [rsp+88h+arg_38]
0x18000c6fb  mov     edx, ebx
0x18000c6fd  mov     ecx, edi
0x18000c6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c704  jmp     short loc_18000C709
0x18000c706  mov     ebp, r14d
0x18000c709  mov     eax, ebp
0x18000c70b  mov     rbx, [rsp+88h+arg_0]
0x18000c713  add     rsp, 50h
0x18000c717  pop     r15
0x18000c719  pop     r14
0x18000c71b  pop     r13
0x18000c71d  pop     r12
0x18000c71f  pop     rdi
0x18000c720  pop     rsi
0x18000c721  pop     rbp
0x18000c722  retn
```
