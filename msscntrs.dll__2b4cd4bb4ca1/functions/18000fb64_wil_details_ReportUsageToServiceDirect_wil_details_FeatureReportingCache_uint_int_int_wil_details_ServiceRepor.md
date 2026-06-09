# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000fb64`
- end: `0x18000fd03`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000fa2c`

## callees

- `0x18000e928`
- `0x18000fb64`
- `0x18001170c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fc2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fc2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc7b`

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
    if ( !qword_180021CC0 )
    {
      qword_180021CC0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180021CC0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000fb64  mov     rax, rsp
0x18000fb67  mov     [rax+8], rbx
0x18000fb6b  mov     [rax+20h], r9d
0x18000fb6f  mov     [rax+18h], r8d
0x18000fb73  push    rbp
0x18000fb74  push    rsi
0x18000fb75  push    rdi
0x18000fb76  push    r12
0x18000fb78  push    r13
0x18000fb7a  push    r14
0x18000fb7c  push    r15
0x18000fb7e  sub     rsp, 50h
0x18000fb82  mov     edi, edx
0x18000fb84  mov     r14, rcx
0x18000fb87  mov     ebx, [rsp+88h+arg_20]
0x18000fb8e  mov     r8d, ebx
0x18000fb91  mov     rdx, rcx
0x18000fb94  lea     rcx, [rax-58h]
0x18000fb98  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000fb9d  mov     r15d, [rax]
0x18000fba0  mov     esi, [rax+4]
0x18000fba3  mov     r12d, [rax+8]
0x18000fba7  mov     r13d, [rax+10h]
0x18000fbab  mov     ebp, 1
0x18000fbb0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000fbb7  test    rax, rax
0x18000fbba  jz      short loc_18000FBD4
0x18000fbbc  test    ebx, ebx
0x18000fbbe  jz      short loc_18000FBC8
0x18000fbc0  lea     ecx, [rbx-64h]
0x18000fbc3  cmp     ecx, 31h ; '1'
0x18000fbc6  ja      short loc_18000FBD4
0x18000fbc8  mov     r8d, ebp
0x18000fbcb  mov     edx, ebx
0x18000fbcd  mov     ecx, edi
0x18000fbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbd4  test    r15d, r15d
0x18000fbd7  jz      short loc_18000FBEA
0x18000fbd9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000fbdc  mov     edx, edi; unsigned int
0x18000fbde  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000fbe5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000fbea  xor     r14d, r14d
0x18000fbed  test    esi, esi
0x18000fbef  jz      short loc_18000FC19
0x18000fbf1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fbf8  test    rax, rax
0x18000fbfb  jnz     short loc_18000FC09
0x18000fbfd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fc04  test    rax, rax
0x18000fc07  jz      short loc_18000FC19
0x18000fc09  xor     r9d, r9d
0x18000fc0c  mov     r8d, esi
0x18000fc0f  mov     edx, r12d
0x18000fc12  mov     ecx, edi
0x18000fc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc19  test    r13d, r13d
0x18000fc1c  jnz     short loc_18000FC82
0x18000fc1e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000fc24  test    eax, eax
0x18000fc26  jz      short loc_18000FC82
0x18000fc28  lea     rcx, SRWLock; SRWLock
0x18000fc2f  call    cs:__imp_AcquireSRWLockExclusive
0x18000fc35  cmp     cs:qword_180021CC0, r14
0x18000fc3c  jnz     short loc_18000FC74
0x18000fc3e  mov     cs:qword_180021CC0, r14
0x18000fc45  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000fc4c  test    rax, rax
0x18000fc4f  jnz     short loc_18000FC5D
0x18000fc51  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000fc58  test    rax, rax
0x18000fc5b  jz      short loc_18000FC74
0x18000fc5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000fc61  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000fc68  lea     rcx, qword_180021CC0
0x18000fc6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc74  lea     rcx, SRWLock; SRWLock
0x18000fc7b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc81  nop
0x18000fc82  cmp     [rsp+88h+arg_10], r14d
0x18000fc8a  jz      short loc_18000FCC2
0x18000fc8c  mov     edx, ebx
0x18000fc8e  bts     edx, 1Fh
0x18000fc92  cmp     [rsp+88h+arg_18], r14d
0x18000fc9a  cmovz   edx, ebx
0x18000fc9d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fca4  test    rax, rax
0x18000fca7  jnz     short loc_18000FCB5
0x18000fca9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fcb0  test    rax, rax
0x18000fcb3  jz      short loc_18000FCC2
0x18000fcb5  xor     r9d, r9d
0x18000fcb8  xor     r8d, r8d
0x18000fcbb  mov     ecx, edi
0x18000fcbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcc2  test    r13d, r13d
0x18000fcc5  jnz     short loc_18000FCE6
0x18000fcc7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000fcce  test    rax, rax
0x18000fcd1  jz      short loc_18000FCE9
0x18000fcd3  mov     r8b, [rsp+88h+arg_38]
0x18000fcdb  mov     edx, ebx
0x18000fcdd  mov     ecx, edi
0x18000fcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fce4  jmp     short loc_18000FCE9
0x18000fce6  mov     ebp, r14d
0x18000fce9  mov     eax, ebp
0x18000fceb  mov     rbx, [rsp+88h+arg_0]
0x18000fcf3  add     rsp, 50h
0x18000fcf7  pop     r15
0x18000fcf9  pop     r14
0x18000fcfb  pop     r13
0x18000fcfd  pop     r12
0x18000fcff  pop     rdi
0x18000fd00  pop     rsi
0x18000fd01  pop     rbp
0x18000fd02  retn
```
