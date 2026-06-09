# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180010688`
- end: `0x18001082a`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010550`

## callees

- `0x18000ec70`
- `0x180010688`
- `0x180019970`
- `0x180023010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180010756`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180010756`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800107a2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800107a2`

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

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5, 0);
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
    if ( !qword_18002F500 )
    {
      qword_18002F500 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18002F500, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x180010688  mov     rax, rsp
0x18001068b  mov     [rax+8], rbx
0x18001068f  mov     [rax+20h], r9d
0x180010693  mov     [rax+18h], r8d
0x180010697  push    rbp
0x180010698  push    rsi
0x180010699  push    rdi
0x18001069a  push    r12
0x18001069c  push    r13
0x18001069e  push    r14
0x1800106a0  push    r15
0x1800106a2  sub     rsp, 50h
0x1800106a6  mov     ebx, edx
0x1800106a8  mov     r14, rcx
0x1800106ab  xor     r9d, r9d
0x1800106ae  mov     edi, [rsp+88h+arg_20]
0x1800106b5  mov     r8d, edi
0x1800106b8  mov     rdx, rcx
0x1800106bb  lea     rcx, [rax-58h]
0x1800106bf  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800106c4  mov     r15d, [rax]
0x1800106c7  mov     esi, [rax+4]
0x1800106ca  mov     r12d, [rax+8]
0x1800106ce  mov     r13d, [rax+10h]
0x1800106d2  mov     ebp, 1
0x1800106d7  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800106de  test    rax, rax
0x1800106e1  jz      short loc_1800106FB
0x1800106e3  test    edi, edi
0x1800106e5  jz      short loc_1800106EF
0x1800106e7  lea     ecx, [rdi-64h]
0x1800106ea  cmp     ecx, 31h ; '1'
0x1800106ed  ja      short loc_1800106FB
0x1800106ef  mov     r8d, ebp
0x1800106f2  mov     edx, edi
0x1800106f4  mov     ecx, ebx
0x1800106f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106fb  test    r15d, r15d
0x1800106fe  jz      short loc_180010711
0x180010700  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180010703  mov     edx, ebx; unsigned int
0x180010705  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001070c  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180010711  xor     r14d, r14d
0x180010714  test    esi, esi
0x180010716  jz      short loc_180010740
0x180010718  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001071f  test    rax, rax
0x180010722  jnz     short loc_180010730
0x180010724  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001072b  test    rax, rax
0x18001072e  jz      short loc_180010740
0x180010730  xor     r9d, r9d
0x180010733  mov     r8d, esi
0x180010736  mov     edx, r12d
0x180010739  mov     ecx, ebx
0x18001073b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010740  test    r13d, r13d
0x180010743  jnz     short loc_1800107A9
0x180010745  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001074b  test    eax, eax
0x18001074d  jz      short loc_1800107A9
0x18001074f  lea     rcx, SRWLock; SRWLock
0x180010756  call    cs:__imp_AcquireSRWLockExclusive
0x18001075c  cmp     cs:qword_18002F500, r14
0x180010763  jnz     short loc_18001079B
0x180010765  mov     cs:qword_18002F500, r14
0x18001076c  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180010773  test    rax, rax
0x180010776  jnz     short loc_180010784
0x180010778  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001077f  test    rax, rax
0x180010782  jz      short loc_18001079B
0x180010784  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010788  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001078f  lea     rcx, qword_18002F500
0x180010796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001079b  lea     rcx, SRWLock; SRWLock
0x1800107a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800107a8  nop
0x1800107a9  cmp     [rsp+88h+arg_10], r14d
0x1800107b1  jz      short loc_1800107E9
0x1800107b3  mov     edx, edi
0x1800107b5  bts     edx, 1Fh
0x1800107b9  cmp     [rsp+88h+arg_18], r14d
0x1800107c1  cmovz   edx, edi
0x1800107c4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800107cb  test    rax, rax
0x1800107ce  jnz     short loc_1800107DC
0x1800107d0  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800107d7  test    rax, rax
0x1800107da  jz      short loc_1800107E9
0x1800107dc  xor     r9d, r9d
0x1800107df  xor     r8d, r8d
0x1800107e2  mov     ecx, ebx
0x1800107e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e9  test    r13d, r13d
0x1800107ec  jnz     short loc_18001080D
0x1800107ee  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800107f5  test    rax, rax
0x1800107f8  jz      short loc_180010810
0x1800107fa  mov     r8b, [rsp+88h+arg_38]
0x180010802  mov     edx, edi
0x180010804  mov     ecx, ebx
0x180010806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080b  jmp     short loc_180010810
0x18001080d  mov     ebp, r14d
0x180010810  mov     eax, ebp
0x180010812  mov     rbx, [rsp+88h+arg_0]
0x18001081a  add     rsp, 50h
0x18001081e  pop     r15
0x180010820  pop     r14
0x180010822  pop     r13
0x180010824  pop     r12
0x180010826  pop     rdi
0x180010827  pop     rsi
0x180010828  pop     rbp
0x180010829  retn
```
