# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000b9e4`
- end: `0x18000bb83`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b8ac`

## callees

- `0x18000b6ec`
- `0x18000b9e4`
- `0x18000c4d8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000baaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bafb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bafb`

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
    if ( !qword_1800207C0 )
    {
      qword_1800207C0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800207C0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000b9e4  mov     rax, rsp
0x18000b9e7  mov     [rax+8], rbx
0x18000b9eb  mov     [rax+20h], r9d
0x18000b9ef  mov     [rax+18h], r8d
0x18000b9f3  push    rbp
0x18000b9f4  push    rsi
0x18000b9f5  push    rdi
0x18000b9f6  push    r12
0x18000b9f8  push    r13
0x18000b9fa  push    r14
0x18000b9fc  push    r15
0x18000b9fe  sub     rsp, 50h
0x18000ba02  mov     edi, edx
0x18000ba04  mov     r14, rcx
0x18000ba07  mov     ebx, [rsp+88h+arg_20]
0x18000ba0e  mov     r8d, ebx
0x18000ba11  mov     rdx, rcx
0x18000ba14  lea     rcx, [rax-58h]
0x18000ba18  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000ba1d  mov     r15d, [rax]
0x18000ba20  mov     esi, [rax+4]
0x18000ba23  mov     r12d, [rax+8]
0x18000ba27  mov     r13d, [rax+10h]
0x18000ba2b  mov     ebp, 1
0x18000ba30  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000ba37  test    rax, rax
0x18000ba3a  jz      short loc_18000BA54
0x18000ba3c  test    ebx, ebx
0x18000ba3e  jz      short loc_18000BA48
0x18000ba40  lea     ecx, [rbx-64h]
0x18000ba43  cmp     ecx, 31h ; '1'
0x18000ba46  ja      short loc_18000BA54
0x18000ba48  mov     r8d, ebp
0x18000ba4b  mov     edx, ebx
0x18000ba4d  mov     ecx, edi
0x18000ba4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba54  test    r15d, r15d
0x18000ba57  jz      short loc_18000BA6A
0x18000ba59  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000ba5c  mov     edx, edi; unsigned int
0x18000ba5e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000ba65  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000ba6a  xor     r14d, r14d
0x18000ba6d  test    esi, esi
0x18000ba6f  jz      short loc_18000BA99
0x18000ba71  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ba78  test    rax, rax
0x18000ba7b  jnz     short loc_18000BA89
0x18000ba7d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ba84  test    rax, rax
0x18000ba87  jz      short loc_18000BA99
0x18000ba89  xor     r9d, r9d
0x18000ba8c  mov     r8d, esi
0x18000ba8f  mov     edx, r12d
0x18000ba92  mov     ecx, edi
0x18000ba94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba99  test    r13d, r13d
0x18000ba9c  jnz     short loc_18000BB02
0x18000ba9e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000baa4  test    eax, eax
0x18000baa6  jz      short loc_18000BB02
0x18000baa8  lea     rcx, SRWLock; SRWLock
0x18000baaf  call    cs:__imp_AcquireSRWLockExclusive
0x18000bab5  cmp     cs:qword_1800207C0, r14
0x18000babc  jnz     short loc_18000BAF4
0x18000babe  mov     cs:qword_1800207C0, r14
0x18000bac5  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000bacc  test    rax, rax
0x18000bacf  jnz     short loc_18000BADD
0x18000bad1  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000bad8  test    rax, rax
0x18000badb  jz      short loc_18000BAF4
0x18000badd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bae1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000bae8  lea     rcx, qword_1800207C0
0x18000baef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf4  lea     rcx, SRWLock; SRWLock
0x18000bafb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bb01  nop
0x18000bb02  cmp     [rsp+88h+arg_10], r14d
0x18000bb0a  jz      short loc_18000BB42
0x18000bb0c  mov     edx, ebx
0x18000bb0e  bts     edx, 1Fh
0x18000bb12  cmp     [rsp+88h+arg_18], r14d
0x18000bb1a  cmovz   edx, ebx
0x18000bb1d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000bb24  test    rax, rax
0x18000bb27  jnz     short loc_18000BB35
0x18000bb29  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000bb30  test    rax, rax
0x18000bb33  jz      short loc_18000BB42
0x18000bb35  xor     r9d, r9d
0x18000bb38  xor     r8d, r8d
0x18000bb3b  mov     ecx, edi
0x18000bb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb42  test    r13d, r13d
0x18000bb45  jnz     short loc_18000BB66
0x18000bb47  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000bb4e  test    rax, rax
0x18000bb51  jz      short loc_18000BB69
0x18000bb53  mov     r8b, [rsp+88h+arg_38]
0x18000bb5b  mov     edx, ebx
0x18000bb5d  mov     ecx, edi
0x18000bb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb64  jmp     short loc_18000BB69
0x18000bb66  mov     ebp, r14d
0x18000bb69  mov     eax, ebp
0x18000bb6b  mov     rbx, [rsp+88h+arg_0]
0x18000bb73  add     rsp, 50h
0x18000bb77  pop     r15
0x18000bb79  pop     r14
0x18000bb7b  pop     r13
0x18000bb7d  pop     r12
0x18000bb7f  pop     rdi
0x18000bb80  pop     rsi
0x18000bb81  pop     rbp
0x18000bb82  retn
```
