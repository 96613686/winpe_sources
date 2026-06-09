# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800097a8`
- end: `0x180009947`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180009670`

## callees

- `0x18000815c`
- `0x1800097a8`
- `0x18000d050`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009873`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009873`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098bf`

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
    if ( !qword_18001E708 )
    {
      qword_18001E708 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18001E708, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1800097a8  mov     rax, rsp
0x1800097ab  mov     [rax+8], rbx
0x1800097af  mov     [rax+20h], r9d
0x1800097b3  mov     [rax+18h], r8d
0x1800097b7  push    rbp
0x1800097b8  push    rsi
0x1800097b9  push    rdi
0x1800097ba  push    r12
0x1800097bc  push    r13
0x1800097be  push    r14
0x1800097c0  push    r15
0x1800097c2  sub     rsp, 50h
0x1800097c6  mov     edi, edx
0x1800097c8  mov     r14, rcx
0x1800097cb  mov     ebx, [rsp+88h+arg_20]
0x1800097d2  mov     r8d, ebx
0x1800097d5  mov     rdx, rcx
0x1800097d8  lea     rcx, [rax-58h]
0x1800097dc  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800097e1  mov     r15d, [rax]
0x1800097e4  mov     esi, [rax+4]
0x1800097e7  mov     r12d, [rax+8]
0x1800097eb  mov     r13d, [rax+10h]
0x1800097ef  mov     ebp, 1
0x1800097f4  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800097fb  test    rax, rax
0x1800097fe  jz      short loc_180009818
0x180009800  test    ebx, ebx
0x180009802  jz      short loc_18000980C
0x180009804  lea     ecx, [rbx-64h]
0x180009807  cmp     ecx, 31h ; '1'
0x18000980a  ja      short loc_180009818
0x18000980c  mov     r8d, ebp
0x18000980f  mov     edx, ebx
0x180009811  mov     ecx, edi
0x180009813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009818  test    r15d, r15d
0x18000981b  jz      short loc_18000982E
0x18000981d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180009820  mov     edx, edi; unsigned int
0x180009822  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180009829  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000982e  xor     r14d, r14d
0x180009831  test    esi, esi
0x180009833  jz      short loc_18000985D
0x180009835  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000983c  test    rax, rax
0x18000983f  jnz     short loc_18000984D
0x180009841  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180009848  test    rax, rax
0x18000984b  jz      short loc_18000985D
0x18000984d  xor     r9d, r9d
0x180009850  mov     r8d, esi
0x180009853  mov     edx, r12d
0x180009856  mov     ecx, edi
0x180009858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985d  test    r13d, r13d
0x180009860  jnz     short loc_1800098C6
0x180009862  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009868  test    eax, eax
0x18000986a  jz      short loc_1800098C6
0x18000986c  lea     rcx, SRWLock; SRWLock
0x180009873  call    cs:__imp_AcquireSRWLockExclusive
0x180009879  cmp     cs:qword_18001E708, r14
0x180009880  jnz     short loc_1800098B8
0x180009882  mov     cs:qword_18001E708, r14
0x180009889  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180009890  test    rax, rax
0x180009893  jnz     short loc_1800098A1
0x180009895  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000989c  test    rax, rax
0x18000989f  jz      short loc_1800098B8
0x1800098a1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800098a5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1800098ac  lea     rcx, qword_18001E708
0x1800098b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b8  lea     rcx, SRWLock; SRWLock
0x1800098bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098c5  nop
0x1800098c6  cmp     [rsp+88h+arg_10], r14d
0x1800098ce  jz      short loc_180009906
0x1800098d0  mov     edx, ebx
0x1800098d2  bts     edx, 1Fh
0x1800098d6  cmp     [rsp+88h+arg_18], r14d
0x1800098de  cmovz   edx, ebx
0x1800098e1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800098e8  test    rax, rax
0x1800098eb  jnz     short loc_1800098F9
0x1800098ed  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800098f4  test    rax, rax
0x1800098f7  jz      short loc_180009906
0x1800098f9  xor     r9d, r9d
0x1800098fc  xor     r8d, r8d
0x1800098ff  mov     ecx, edi
0x180009901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009906  test    r13d, r13d
0x180009909  jnz     short loc_18000992A
0x18000990b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180009912  test    rax, rax
0x180009915  jz      short loc_18000992D
0x180009917  mov     r8b, [rsp+88h+arg_38]
0x18000991f  mov     edx, ebx
0x180009921  mov     ecx, edi
0x180009923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009928  jmp     short loc_18000992D
0x18000992a  mov     ebp, r14d
0x18000992d  mov     eax, ebp
0x18000992f  mov     rbx, [rsp+88h+arg_0]
0x180009937  add     rsp, 50h
0x18000993b  pop     r15
0x18000993d  pop     r14
0x18000993f  pop     r13
0x180009941  pop     r12
0x180009943  pop     rdi
0x180009944  pop     rsi
0x180009945  pop     rbp
0x180009946  retn
```
