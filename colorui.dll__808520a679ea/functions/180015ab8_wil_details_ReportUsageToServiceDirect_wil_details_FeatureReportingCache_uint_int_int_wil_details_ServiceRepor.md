# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180015ab8`
- end: `0x180015c56`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015980`

## callees

- `0x180015790`
- `0x180015ab8`
- `0x180016244`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015bcf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015bcf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015b83`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015b83`

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
  unsigned int v12; // ebp
  int v13; // r15d
  unsigned int v14; // esi
  unsigned int v15; // r13d
  int v16; // r12d
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = 1;
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v14 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180021508 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180021508 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180021508, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v12;
}

```

## disassembly

```asm
0x180015ab8  mov     rax, rsp
0x180015abb  mov     [rax+8], rbx
0x180015abf  mov     [rax+20h], r9d
0x180015ac3  mov     [rax+18h], r8d
0x180015ac7  push    rbp
0x180015ac8  push    rsi
0x180015ac9  push    rdi
0x180015aca  push    r12
0x180015acc  push    r13
0x180015ace  push    r14
0x180015ad0  push    r15
0x180015ad2  sub     rsp, 50h
0x180015ad6  mov     ebx, [rsp+88h+arg_20]
0x180015add  mov     edi, edx
0x180015adf  mov     rdx, rcx
0x180015ae2  mov     r14, rcx
0x180015ae5  lea     rcx, [rax-58h]
0x180015ae9  mov     r8d, ebx
0x180015aec  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015af1  mov     ebp, 1
0x180015af6  mov     r15d, [rax]
0x180015af9  mov     esi, [rax+4]
0x180015afc  mov     r13d, [rax+8]
0x180015b00  mov     r12d, [rax+10h]
0x180015b04  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015b0b  test    rax, rax
0x180015b0e  jz      short loc_180015B28
0x180015b10  test    ebx, ebx
0x180015b12  jz      short loc_180015B1C
0x180015b14  lea     ecx, [rbx-64h]
0x180015b17  cmp     ecx, 31h ; '1'
0x180015b1a  ja      short loc_180015B28
0x180015b1c  mov     r8d, ebp
0x180015b1f  mov     edx, ebx
0x180015b21  mov     ecx, edi
0x180015b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b28  test    r15d, r15d
0x180015b2b  jz      short loc_180015B3E
0x180015b2d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180015b30  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015b37  mov     edx, edi; unsigned int
0x180015b39  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180015b3e  xor     r14d, r14d
0x180015b41  test    esi, esi
0x180015b43  jz      short loc_180015B6D
0x180015b45  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015b4c  test    rax, rax
0x180015b4f  jnz     short loc_180015B5D
0x180015b51  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015b58  test    rax, rax
0x180015b5b  jz      short loc_180015B6D
0x180015b5d  xor     r9d, r9d
0x180015b60  mov     r8d, esi
0x180015b63  mov     edx, r13d
0x180015b66  mov     ecx, edi
0x180015b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b6d  test    r12d, r12d
0x180015b70  jnz     short loc_180015BD5
0x180015b72  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015b78  test    eax, eax
0x180015b7a  jz      short loc_180015BD5
0x180015b7c  lea     rcx, SRWLock; SRWLock
0x180015b83  call    cs:__imp_AcquireSRWLockExclusive
0x180015b89  cmp     cs:qword_180021508, r14
0x180015b90  jnz     short loc_180015BC8
0x180015b92  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180015b99  mov     cs:qword_180021508, r14
0x180015ba0  test    rax, rax
0x180015ba3  jnz     short loc_180015BB1
0x180015ba5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015bac  test    rax, rax
0x180015baf  jz      short loc_180015BC8
0x180015bb1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015bb5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180015bbc  lea     rcx, qword_180021508
0x180015bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc8  lea     rcx, SRWLock; SRWLock
0x180015bcf  call    cs:__imp_ReleaseSRWLockExclusive
0x180015bd5  cmp     [rsp+88h+arg_10], r14d
0x180015bdd  jz      short loc_180015C15
0x180015bdf  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015be6  mov     edx, ebx
0x180015be8  bts     edx, 1Fh
0x180015bec  cmp     [rsp+88h+arg_18], r14d
0x180015bf4  cmovz   edx, ebx
0x180015bf7  test    rax, rax
0x180015bfa  jnz     short loc_180015C08
0x180015bfc  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015c03  test    rax, rax
0x180015c06  jz      short loc_180015C15
0x180015c08  xor     r9d, r9d
0x180015c0b  xor     r8d, r8d
0x180015c0e  mov     ecx, edi
0x180015c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c15  test    r12d, r12d
0x180015c18  jnz     short loc_180015C39
0x180015c1a  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180015c21  test    rax, rax
0x180015c24  jz      short loc_180015C3C
0x180015c26  mov     r8b, [rsp+88h+arg_38]
0x180015c2e  mov     edx, ebx
0x180015c30  mov     ecx, edi
0x180015c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c37  jmp     short loc_180015C3C
0x180015c39  mov     ebp, r14d
0x180015c3c  mov     rbx, [rsp+88h+arg_0]
0x180015c44  mov     eax, ebp
0x180015c46  add     rsp, 50h
0x180015c4a  pop     r15
0x180015c4c  pop     r14
0x180015c4e  pop     r13
0x180015c50  pop     r12
0x180015c52  pop     rdi
0x180015c53  pop     rsi
0x180015c54  pop     rbp
0x180015c55  retn
```
