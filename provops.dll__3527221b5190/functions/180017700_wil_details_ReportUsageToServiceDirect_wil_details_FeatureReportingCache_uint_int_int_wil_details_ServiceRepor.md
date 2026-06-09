# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180017700`
- end: `0x18001789f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800175c8`

## callees

- `0x180014c9c`
- `0x180017700`
- `0x1800229f0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800177cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800177cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017817`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017817`

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
    AcquireSRWLockExclusive(&stru_18004A490);
    if ( !qword_18004A4F0 )
    {
      qword_18004A4F0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_18004A4F0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_18004A490);
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
0x180017700  mov     rax, rsp
0x180017703  mov     [rax+8], rbx
0x180017707  mov     [rax+20h], r9d
0x18001770b  mov     [rax+18h], r8d
0x18001770f  push    rbp
0x180017710  push    rsi
0x180017711  push    rdi
0x180017712  push    r12
0x180017714  push    r13
0x180017716  push    r14
0x180017718  push    r15
0x18001771a  sub     rsp, 50h
0x18001771e  mov     edi, edx
0x180017720  mov     r14, rcx
0x180017723  mov     ebx, [rsp+88h+arg_20]
0x18001772a  mov     r8d, ebx
0x18001772d  mov     rdx, rcx
0x180017730  lea     rcx, [rax-58h]
0x180017734  call    wil_details_FeatureReporting_RecordUsageInCache
0x180017739  mov     r15d, [rax]
0x18001773c  mov     esi, [rax+4]
0x18001773f  mov     r12d, [rax+8]
0x180017743  mov     r13d, [rax+10h]
0x180017747  mov     ebp, 1
0x18001774c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180017753  test    rax, rax
0x180017756  jz      short loc_180017770
0x180017758  test    ebx, ebx
0x18001775a  jz      short loc_180017764
0x18001775c  lea     ecx, [rbx-64h]
0x18001775f  cmp     ecx, 31h ; '1'
0x180017762  ja      short loc_180017770
0x180017764  mov     r8d, ebp
0x180017767  mov     edx, ebx
0x180017769  mov     ecx, edi
0x18001776b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017770  test    r15d, r15d
0x180017773  jz      short loc_180017786
0x180017775  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180017778  mov     edx, edi; unsigned int
0x18001777a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180017781  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180017786  xor     r14d, r14d
0x180017789  test    esi, esi
0x18001778b  jz      short loc_1800177B5
0x18001778d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180017794  test    rax, rax
0x180017797  jnz     short loc_1800177A5
0x180017799  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800177a0  test    rax, rax
0x1800177a3  jz      short loc_1800177B5
0x1800177a5  xor     r9d, r9d
0x1800177a8  mov     r8d, esi
0x1800177ab  mov     edx, r12d
0x1800177ae  mov     ecx, edi
0x1800177b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177b5  test    r13d, r13d
0x1800177b8  jnz     short loc_18001781E
0x1800177ba  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800177c0  test    eax, eax
0x1800177c2  jz      short loc_18001781E
0x1800177c4  lea     rcx, stru_18004A490; SRWLock
0x1800177cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800177d1  cmp     cs:qword_18004A4F0, r14
0x1800177d8  jnz     short loc_180017810
0x1800177da  mov     cs:qword_18004A4F0, r14
0x1800177e1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800177e8  test    rax, rax
0x1800177eb  jnz     short loc_1800177F9
0x1800177ed  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800177f4  test    rax, rax
0x1800177f7  jz      short loc_180017810
0x1800177f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800177fd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180017804  lea     rcx, qword_18004A4F0
0x18001780b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017810  lea     rcx, stru_18004A490; SRWLock
0x180017817  call    cs:__imp_ReleaseSRWLockExclusive
0x18001781d  nop
0x18001781e  cmp     [rsp+88h+arg_10], r14d
0x180017826  jz      short loc_18001785E
0x180017828  mov     edx, ebx
0x18001782a  bts     edx, 1Fh
0x18001782e  cmp     [rsp+88h+arg_18], r14d
0x180017836  cmovz   edx, ebx
0x180017839  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180017840  test    rax, rax
0x180017843  jnz     short loc_180017851
0x180017845  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001784c  test    rax, rax
0x18001784f  jz      short loc_18001785E
0x180017851  xor     r9d, r9d
0x180017854  xor     r8d, r8d
0x180017857  mov     ecx, edi
0x180017859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785e  test    r13d, r13d
0x180017861  jnz     short loc_180017882
0x180017863  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001786a  test    rax, rax
0x18001786d  jz      short loc_180017885
0x18001786f  mov     r8b, [rsp+88h+arg_38]
0x180017877  mov     edx, ebx
0x180017879  mov     ecx, edi
0x18001787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017880  jmp     short loc_180017885
0x180017882  mov     ebp, r14d
0x180017885  mov     eax, ebp
0x180017887  mov     rbx, [rsp+88h+arg_0]
0x18001788f  add     rsp, 50h
0x180017893  pop     r15
0x180017895  pop     r14
0x180017897  pop     r13
0x180017899  pop     r12
0x18001789b  pop     rdi
0x18001789c  pop     rsi
0x18001789d  pop     rbp
0x18001789e  retn
```
