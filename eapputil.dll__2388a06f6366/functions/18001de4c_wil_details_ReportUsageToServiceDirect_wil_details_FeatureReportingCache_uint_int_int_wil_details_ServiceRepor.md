# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001de4c`
- end: `0x18001dff3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001dd0c`
- `0x18001dffc`

## callees

- `0x18001d510`
- `0x18001de4c`
- `0x180024f50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001df1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001df1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
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

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5, a6);
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
    if ( !qword_180043B00 )
    {
      qword_180043B00 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180043B00, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001de4c  mov     rax, rsp
0x18001de4f  mov     [rax+8], rbx
0x18001de53  mov     [rax+20h], r9d
0x18001de57  mov     [rax+18h], r8d
0x18001de5b  push    rbp
0x18001de5c  push    rsi
0x18001de5d  push    rdi
0x18001de5e  push    r12
0x18001de60  push    r13
0x18001de62  push    r14
0x18001de64  push    r15
0x18001de66  sub     rsp, 50h
0x18001de6a  mov     ebx, edx
0x18001de6c  mov     r14, rcx
0x18001de6f  mov     r9d, [rsp+88h+arg_28]
0x18001de77  mov     edi, [rsp+88h+arg_20]
0x18001de7e  mov     r8d, edi
0x18001de81  mov     rdx, rcx
0x18001de84  lea     rcx, [rax-58h]
0x18001de88  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001de8d  mov     r15d, [rax]
0x18001de90  mov     esi, [rax+4]
0x18001de93  mov     r12d, [rax+8]
0x18001de97  mov     r13d, [rax+10h]
0x18001de9b  mov     ebp, 1
0x18001dea0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001dea7  test    rax, rax
0x18001deaa  jz      short loc_18001DEC4
0x18001deac  test    edi, edi
0x18001deae  jz      short loc_18001DEB8
0x18001deb0  lea     ecx, [rdi-64h]
0x18001deb3  cmp     ecx, 31h ; '1'
0x18001deb6  ja      short loc_18001DEC4
0x18001deb8  mov     r8d, ebp
0x18001debb  mov     edx, edi
0x18001debd  mov     ecx, ebx
0x18001debf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dec4  test    r15d, r15d
0x18001dec7  jz      short loc_18001DEDA
0x18001dec9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001decc  mov     edx, ebx; unsigned int
0x18001dece  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001ded5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001deda  xor     r14d, r14d
0x18001dedd  test    esi, esi
0x18001dedf  jz      short loc_18001DF09
0x18001dee1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001dee8  test    rax, rax
0x18001deeb  jnz     short loc_18001DEF9
0x18001deed  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001def4  test    rax, rax
0x18001def7  jz      short loc_18001DF09
0x18001def9  xor     r9d, r9d
0x18001defc  mov     r8d, esi
0x18001deff  mov     edx, r12d
0x18001df02  mov     ecx, ebx
0x18001df04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df09  test    r13d, r13d
0x18001df0c  jnz     short loc_18001DF72
0x18001df0e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001df14  test    eax, eax
0x18001df16  jz      short loc_18001DF72
0x18001df18  lea     rcx, SRWLock; SRWLock
0x18001df1f  call    cs:__imp_AcquireSRWLockExclusive
0x18001df25  cmp     cs:qword_180043B00, r14
0x18001df2c  jnz     short loc_18001DF64
0x18001df2e  mov     cs:qword_180043B00, r14
0x18001df35  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001df3c  test    rax, rax
0x18001df3f  jnz     short loc_18001DF4D
0x18001df41  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001df48  test    rax, rax
0x18001df4b  jz      short loc_18001DF64
0x18001df4d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001df51  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001df58  lea     rcx, qword_180043B00
0x18001df5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df64  lea     rcx, SRWLock; SRWLock
0x18001df6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001df71  nop
0x18001df72  cmp     [rsp+88h+arg_10], r14d
0x18001df7a  jz      short loc_18001DFB2
0x18001df7c  mov     edx, edi
0x18001df7e  bts     edx, 1Fh
0x18001df82  cmp     [rsp+88h+arg_18], r14d
0x18001df8a  cmovz   edx, edi
0x18001df8d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001df94  test    rax, rax
0x18001df97  jnz     short loc_18001DFA5
0x18001df99  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001dfa0  test    rax, rax
0x18001dfa3  jz      short loc_18001DFB2
0x18001dfa5  xor     r9d, r9d
0x18001dfa8  xor     r8d, r8d
0x18001dfab  mov     ecx, ebx
0x18001dfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb2  test    r13d, r13d
0x18001dfb5  jnz     short loc_18001DFD6
0x18001dfb7  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001dfbe  test    rax, rax
0x18001dfc1  jz      short loc_18001DFD9
0x18001dfc3  mov     r8b, [rsp+88h+arg_38]
0x18001dfcb  mov     edx, edi
0x18001dfcd  mov     ecx, ebx
0x18001dfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfd4  jmp     short loc_18001DFD9
0x18001dfd6  mov     ebp, r14d
0x18001dfd9  mov     eax, ebp
0x18001dfdb  mov     rbx, [rsp+88h+arg_0]
0x18001dfe3  add     rsp, 50h
0x18001dfe7  pop     r15
0x18001dfe9  pop     r14
0x18001dfeb  pop     r13
0x18001dfed  pop     r12
0x18001dfef  pop     rdi
0x18001dff0  pop     rsi
0x18001dff1  pop     rbp
0x18001dff2  retn
```
