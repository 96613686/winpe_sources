# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800119b0`
- end: `0x180011b50`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180011920`

## callees

- `0x180010384`
- `0x1800119b0`
- `0x18001c5ac`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011ac9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011ac9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011a77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011a77`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // r12d
  unsigned int v17; // esi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(__int64, __int64, _QWORD, _QWORD); // rax
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  v17 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(57312060, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (char *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v14 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(57312060, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180032920 )
    {
      qword_180032920 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_180032920, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(57312060, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(57312060, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x1800119b0  mov     [rsp+arg_18], r9d
0x1800119b5  push    rbx
0x1800119b6  push    rbp
0x1800119b7  push    rsi
0x1800119b8  push    rdi
0x1800119b9  push    r12
0x1800119bb  push    r13
0x1800119bd  push    r14
0x1800119bf  push    r15
0x1800119c1  sub     rsp, 58h
0x1800119c5  mov     r13d, r8d
0x1800119c8  mov     rbp, rcx
0x1800119cb  mov     ebx, [rsp+98h+arg_20]
0x1800119d2  mov     r8d, ebx
0x1800119d5  mov     rdx, rcx
0x1800119d8  lea     rcx, [rsp+98h+var_68]
0x1800119dd  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800119e2  mov     r14d, [rax]
0x1800119e5  mov     edi, [rax+4]
0x1800119e8  mov     r15d, [rax+8]
0x1800119ec  mov     r12d, [rax+10h]
0x1800119f0  mov     esi, 1
0x1800119f5  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1800119fc  test    rax, rax
0x1800119ff  jz      short loc_180011A1C
0x180011a01  test    ebx, ebx
0x180011a03  jz      short loc_180011A0D
0x180011a05  lea     ecx, [rbx-64h]
0x180011a08  cmp     ecx, 31h ; '1'
0x180011a0b  ja      short loc_180011A1C
0x180011a0d  mov     r8d, esi
0x180011a10  mov     edx, ebx
0x180011a12  mov     ecx, 36A833Ch
0x180011a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a1c  test    r14d, r14d
0x180011a1f  jz      short loc_180011A30
0x180011a21  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x180011a24  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180011a2b  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180011a30  xor     ebp, ebp
0x180011a32  test    edi, edi
0x180011a34  jz      short loc_180011A61
0x180011a36  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180011a3d  test    rax, rax
0x180011a40  jnz     short loc_180011A4E
0x180011a42  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180011a49  test    rax, rax
0x180011a4c  jz      short loc_180011A61
0x180011a4e  xor     r9d, r9d
0x180011a51  mov     r8d, edi
0x180011a54  mov     edx, r15d
0x180011a57  mov     ecx, 36A833Ch
0x180011a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a61  test    r12d, r12d
0x180011a64  jnz     short loc_180011AD6
0x180011a66  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011a6c  test    eax, eax
0x180011a6e  jz      short loc_180011AD6
0x180011a70  lea     rcx, SRWLock; SRWLock
0x180011a77  call    cs:__imp_AcquireSRWLockExclusive
0x180011a7e  nop     dword ptr [rax+rax+00h]
0x180011a83  cmp     cs:qword_180032920, rbp
0x180011a8a  jnz     short loc_180011AC2
0x180011a8c  mov     cs:qword_180032920, rbp
0x180011a93  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180011a9a  test    rax, rax
0x180011a9d  jnz     short loc_180011AAB
0x180011a9f  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180011aa6  test    rax, rax
0x180011aa9  jz      short loc_180011AC2
0x180011aab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011aaf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180011ab6  lea     rcx, qword_180032920
0x180011abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ac2  lea     rcx, SRWLock; SRWLock
0x180011ac9  call    cs:__imp_ReleaseSRWLockExclusive
0x180011ad0  nop     dword ptr [rax+rax+00h]
0x180011ad5  nop
0x180011ad6  test    r13d, r13d
0x180011ad9  jz      short loc_180011B13
0x180011adb  mov     edx, ebx
0x180011add  bts     edx, 1Fh
0x180011ae1  cmp     [rsp+98h+arg_18], ebp
0x180011ae8  cmovz   edx, ebx
0x180011aeb  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180011af2  test    rax, rax
0x180011af5  jnz     short loc_180011B03
0x180011af7  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180011afe  test    rax, rax
0x180011b01  jz      short loc_180011B13
0x180011b03  xor     r9d, r9d
0x180011b06  xor     r8d, r8d
0x180011b09  mov     ecx, 36A833Ch
0x180011b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b13  test    r12d, r12d
0x180011b16  jnz     short loc_180011B3A
0x180011b18  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180011b1f  test    rax, rax
0x180011b22  jz      short loc_180011B3C
0x180011b24  mov     r8b, [rsp+98h+arg_38]
0x180011b2c  mov     edx, ebx
0x180011b2e  mov     ecx, 36A833Ch
0x180011b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b38  jmp     short loc_180011B3C
0x180011b3a  mov     esi, ebp
0x180011b3c  mov     eax, esi
0x180011b3e  add     rsp, 58h
0x180011b42  pop     r15
0x180011b44  pop     r14
0x180011b46  pop     r13
0x180011b48  pop     r12
0x180011b4a  pop     rdi
0x180011b4b  pop     rsi
0x180011b4c  pop     rbp
0x180011b4d  pop     rbx
0x180011b4e  retn
```
