# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1400081cc`
- end: `0x140008378`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000812c`

## callees

- `0x140006c9c`
- `0x1400081cc`
- `0x14000b2bc`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008297`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008297`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400082e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400082e9`

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
      (char *)&wil::details::g_enabledStateManager,
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
    AcquireSRWLockExclusive(&stru_1400239F0);
    if ( !qword_140023A10 )
    {
      qword_140023A10 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_140023A10, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_1400239F0);
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
0x1400081cc  mov     rax, rsp
0x1400081cf  mov     [rax+8], rbx
0x1400081d3  mov     [rax+20h], r9d
0x1400081d7  mov     [rax+18h], r8d
0x1400081db  push    rbp
0x1400081dc  push    rsi
0x1400081dd  push    rdi
0x1400081de  push    r12
0x1400081e0  push    r13
0x1400081e2  push    r14
0x1400081e4  push    r15
0x1400081e6  sub     rsp, 50h
0x1400081ea  mov     edi, edx
0x1400081ec  mov     r14, rcx
0x1400081ef  mov     ebx, [rsp+88h+arg_20]
0x1400081f6  mov     r8d, ebx
0x1400081f9  mov     rdx, rcx
0x1400081fc  lea     rcx, [rax-58h]
0x140008200  call    wil_details_FeatureReporting_RecordUsageInCache
0x140008205  mov     r15d, [rax]
0x140008208  mov     esi, [rax+4]
0x14000820b  mov     r12d, [rax+8]
0x14000820f  mov     r13d, [rax+10h]
0x140008213  mov     ebp, 1
0x140008218  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000821f  test    rax, rax
0x140008222  jz      short loc_14000823C
0x140008224  test    ebx, ebx
0x140008226  jz      short loc_140008230
0x140008228  lea     ecx, [rbx-64h]
0x14000822b  cmp     ecx, 31h ; '1'
0x14000822e  ja      short loc_14000823C
0x140008230  mov     r8d, ebp
0x140008233  mov     edx, ebx
0x140008235  mov     ecx, edi
0x140008237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000823c  test    r15d, r15d
0x14000823f  jz      short loc_140008252
0x140008241  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x140008244  mov     edx, edi; unsigned int
0x140008246  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000824d  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x140008252  xor     r14d, r14d
0x140008255  test    esi, esi
0x140008257  jz      short loc_140008281
0x140008259  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140008260  test    rax, rax
0x140008263  jnz     short loc_140008271
0x140008265  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000826c  test    rax, rax
0x14000826f  jz      short loc_140008281
0x140008271  xor     r9d, r9d
0x140008274  mov     r8d, esi
0x140008277  mov     edx, r12d
0x14000827a  mov     ecx, edi
0x14000827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008281  test    r13d, r13d
0x140008284  jnz     short loc_1400082F6
0x140008286  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000828c  test    eax, eax
0x14000828e  jz      short loc_1400082F6
0x140008290  lea     rcx, stru_1400239F0; SRWLock
0x140008297  call    cs:__imp_AcquireSRWLockExclusive
0x14000829e  nop     dword ptr [rax+rax+00h]
0x1400082a3  cmp     cs:qword_140023A10, r14
0x1400082aa  jnz     short loc_1400082E2
0x1400082ac  mov     cs:qword_140023A10, r14
0x1400082b3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1400082ba  test    rax, rax
0x1400082bd  jnz     short loc_1400082CB
0x1400082bf  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1400082c6  test    rax, rax
0x1400082c9  jz      short loc_1400082E2
0x1400082cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400082cf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1400082d6  lea     rcx, qword_140023A10
0x1400082dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082e2  lea     rcx, stru_1400239F0; SRWLock
0x1400082e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400082f0  nop     dword ptr [rax+rax+00h]
0x1400082f5  nop
0x1400082f6  cmp     [rsp+88h+arg_10], r14d
0x1400082fe  jz      short loc_140008336
0x140008300  mov     edx, ebx
0x140008302  bts     edx, 1Fh
0x140008306  cmp     [rsp+88h+arg_18], r14d
0x14000830e  cmovz   edx, ebx
0x140008311  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140008318  test    rax, rax
0x14000831b  jnz     short loc_140008329
0x14000831d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140008324  test    rax, rax
0x140008327  jz      short loc_140008336
0x140008329  xor     r9d, r9d
0x14000832c  xor     r8d, r8d
0x14000832f  mov     ecx, edi
0x140008331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008336  test    r13d, r13d
0x140008339  jnz     short loc_14000835A
0x14000833b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x140008342  test    rax, rax
0x140008345  jz      short loc_14000835D
0x140008347  mov     r8b, [rsp+88h+arg_38]
0x14000834f  mov     edx, ebx
0x140008351  mov     ecx, edi
0x140008353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008358  jmp     short loc_14000835D
0x14000835a  mov     ebp, r14d
0x14000835d  mov     eax, ebp
0x14000835f  mov     rbx, [rsp+88h+arg_0]
0x140008367  add     rsp, 50h
0x14000836b  pop     r15
0x14000836d  pop     r14
0x14000836f  pop     r13
0x140008371  pop     r12
0x140008373  pop     rdi
0x140008374  pop     rsi
0x140008375  pop     rbp
0x140008376  retn
```
